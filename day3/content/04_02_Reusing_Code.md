# Reusing Code

## 목차
- [Reusing Code](#reusing-code)
  - [목차](#목차)
  - [모듈 스크립트 생성](#모듈-스크립트-생성)
  - [모듈 스크립트의 구조](#모듈-스크립트의-구조)
  - [모듈 스크립트 요구](#모듈-스크립트-요구)
  - [패턴](#패턴)
    - [데이터 공유](#데이터-공유)
    - [커스텀 이벤트](#커스텀-이벤트)
    - [캡슐화](#캡슐화)
  - [출처](#출처)
  - [다음](#다음)

---

몇 개의 스크립트를 작성한 후에는 스크립트 간에 코드를 재사용하고 싶어집니다. 위치에 따라 `ModuleScripts`를 사용하면 클라이언트-서버 경계를 넘나드는 스크립트 간 또는 동일한 경계 내에서 코드를 재사용할 수 있습니다.

## 모듈 스크립트 생성

모듈 스크립트는 스크립트를 배치할 수 있는 모든 곳에 배치할 수 있지만, `ReplicatedStorage`는 인기 있는 위치입니다. 모듈 스크립트를 여기 저장하면 서버와 클라이언트 간에 코드를 재사용할 수 있습니다.

1. Roblox Studio에서 Explorer 창의 **ReplicatedStorage** 위에 마우스를 올리고 **+**를 클릭합니다.
2. **ModuleScript**를 선택하여 새 모듈 스크립트를 추가합니다.
3. 스크립트를 마우스 오른쪽 버튼으로 클릭하고 이름을 `PickupManager`로 변경합니다.
4. 스크립트를 두 번 클릭하여 스크립트 편집기에서 엽니다.

## 모듈 스크립트의 구조

각 `ModuleScript`는 다음 코드로 시작합니다:

```lua
local module = {}

return module
```

이 코드는 빈 Luau 테이블을 생성하고 모듈 스크립트를 요구하는 모든 스크립트에 반환합니다.

반환 값은 `nil`을 제외한 모든 데이터 유형이 될 수 있지만, 대부분의 모듈 스크립트는 함수, 테이블 또는 함수의 테이블을 반환합니다. 반환 값을 생성하기 위해 모듈 스크립트는 물론 다른 모듈 스크립트를 요구하는 임의의 코드를 실행할 수 있습니다.

<Alert severity="info">
모듈 스크립트가 순환적으로 서로를 요구하지 않도록 주의하십시오. 그렇지 않으면 `Requested module was required recursively` 오류가 발생합니다.
</Alert>

다음 예제는 `getPickupBonus`라는 단일 함수를 가진 테이블을 반환합니다. 이를 새 모듈 스크립트에 붙여넣으세요:

```lua
-- ReplicatedStorage에 있는 ModuleScript
local PickupManager = {}

local defaultMultiplier = 1.25
local rarityMultipliers = {
  common = 10,
  uncommon = 20,
  rare = 50,
  legendary = 100
}

-- getPickupBonus 함수를 PickupManager 테이블에 추가
PickupManager.getPickupBonus = function(rarity)
  local bonus = rarityMultipliers[rarity] * defaultMultiplier
  return bonus
end

return PickupManager
```

함수를 테이블에 추가하는 것은 필수적이지 않지만, 이는 좋은 패턴입니다. 다른 스크립트에서 함수를 호출할 때 이해하기 쉬운 구문을 제공하고 시간이 지남에 따라 모듈 스크립트에 더 많은 함수를 쉽게 추가할 수 있습니다.

## 모듈 스크립트 요구

모듈 스크립트를 로드하려면 `Global.RobloxGlobals.require()` 함수를 호출합니다. `ReplicatedStorage`에 새 스크립트를 추가하고 `RunContext`를 `Client`로 변경합니다. 그런 다음 다음 코드를 추가하여 `PickupManager.getPickupBonus` 함수를 호출합니다:

```lua title="ReplicatedStorage에 있는 클라이언트 스크립트"
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- ModuleScript에서 반환된 값 가져오기
local PickupManager = require(ReplicatedStorage:WaitForChild("PickupManager"))

-- ModuleScript 함수 호출
local bonus = PickupManager.getPickupBonus("legendary")
print(bonus)  --> 125
```

다음 코드를 사용하여 `ServerScriptService`에서도 스크립트를 요구할 수 있습니다:

```lua title="ServerScriptStorage에 있는 스크립트"
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- "PickupManager"라는 ModuleScript의 반환 값 가져오기
local PickupManager = require(ReplicatedStorage:WaitForChild("PickupManager"))
```

<Alert severity="info">
`Instance:WaitForChild()` 패턴은 경험을 로드하는 데 걸리는 시간과 로딩 순서에 대한 Roblox의 보장이 부족하기 때문에 중요한 안전 조치입니다. 모든 것이 로드되었다는 보장이 있다면 `require(ReplicatedStorage.PickupManager)`를 호출할 수 있지만, `WaitForChild()`가 더 안전합니다.
</Alert>

`Global.RobloxGlobals.require()`를 `ModuleScript`에서 호출하면 한 번 실행되고 참조로 단일 항목을 반환합니다. `Global.RobloxGlobals.require()`를 다시 호출하면 정확히 동일한 참조가 반환되며, 반환된 테이블 또는 `Instance`를 수정하면 이후의 `Global.RobloxGlobals.require()` 호출은 수정된 참조를 반환합니다. 모듈 자체는 여러 번 실행되지 않습니다.

클라이언트-서버 경계 양쪽에서 `ModuleScript`를 요구하면, `ModuleScript`는 각 측에 대해 고유한 참조를 반환합니다.

## 패턴

모듈 스크립트는 경험이 크기와 복잡도가 증가함에 따라 코드를 단순화하고 함정을 피할 수 있는 몇 가지 일반적인 패턴을 가지고 있습니다.

<Alert severity="success">
이러한 패턴의 대부분은 이벤트에 대한 이해를 요구합니다. 이벤트에 익숙하지 않은 경우 이벤트를 참조하세요.
</Alert>

### 데이터 공유

개별 객체와 데이터를 연관시키기 위해 속성을 할당하거나 `StringValue` 또는 `IntValue`와 같은 값 객체가 있는 `Configuration` 폴더를 생성할 수 있습니다. 그러나 이러한 접근 방식은 수십 개의 객체 또는 데이터 값을 추가하거나 수정하려는 경우 문제가 될 수 있습니다. 또한 테이블이나 함수를 저장하지 않습니다.

동일한 객체의 여러 복사본에 대해 동일한 데이터를 수정하거나 다른 객체에 동일한 데이터를 재사용하려는 경우, 데이터를 `ModuleScripts`에 저장하십시오. 다른 스크립트에서 데이터를 재사용하는 더 쉬운 방법이며, 테이블과 함수를 저장할 수 있습니다.

다음 예제 `ModuleScript`는 `ReplicatedStorage`에 있으며, 일반적인 총기의 구성 값을 저장합니다:

```lua title="ReplicatedStorage에 있는 ModuleScript"
local GunConfig = {}

GunConfig.MagazineSize = 20
GunConfig.AmmoCount = 100
GunConfig.Firerate = 600
GunConfig.Damage = {
  ["Head"] = 50;
  ["Torso"] = 40;
  ["Body"] = 25;
}

return GunConfig
```

### 커스텀 이벤트

커스텀 이벤트는 스크립트가 서로 통신할 수 있게 하지만 개별 `BindableEvent` 객체에 대한 참조를 추적하는 것은 코드를 복잡하게 만들 수 있습니다.

`ModuleScripts`를 사용하여 `BindableEvents`를 저장하고 `ModuleScript`의 메서드에 직접 연결된 커스텀 이벤트 핸들러를 제공할 수 있습니다.

다음 `ModuleScript`는 `ReplicatedStorage`에 있으며, 스위치 상태가 변경될 때 발생하는 커스텀 이벤트가 있습니다:

```lua title="ReplicatedStorage에 있는 ModuleScript"
local Switch = {}

-- 스위치가 변경될 때 모든 스크립트가 들을 수 있도록 바인더블 이벤트 생성
local bindableEvent = Instance.new("BindableEvent")
Switch.Changed = bindableEvent.Event

local state = false
function Switch.flip()
  state = not state
  bindableEvent:Fire(state)
end

return Switch
```

다음 클라이언트 스크립트는 `ReplicatedStorage`에 있으며, `Switch.Changed` 이벤트가 발생할 때 호출할 함수를 연결합니다.

```lua title="ReplicatedStorage에 있는 스크립트"
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Switch = require(ReplicatedStorage:WaitForChild("Switch"))

Switch.Changed:Connect(function(newState)
  print("스위치 상태가 이제", newState, "입니다")
end)

-- 스위치 상태를 몇 번 테스트하기
task.wait(1)
Switch.flip()
task.wait(1)
Switch.flip()
```

### 캡슐화

캡슐화는 객체나 스크립팅 로직 주위에 추상화 계층을 생성하여 복잡성을 숨기는 것입니다. `ModuleScripts`를 사용하여 Roblox 객체를 사용자 지정 Lua 함수로 캡슐화하여 코드를 단순화할 수 있습니다.

예를 들어, 캡슐화를 사용하여 다음을 수행할 수 있습니다:

- 단일 `RemoteEvent` 객체로 네트워크 간 통신 단순화.
- `DataStoreService`와 같은 민감한 서비스 주위에 오류 처리 코드 래핑.
- Roblox 객체 기능을 제어하거나 확장하기 위한 사용자 지정 메서드 정의.

게임에서 네트워킹을 구현하기 위해 수십 개의

 개별 `RemoteEvent` 객체를 추적하는 것은 어렵습니다. 이 문제를 단순화하는 데 도움이 되도록 단일 `RemoteEvent`를 캡슐화하는 `ModuleScript`를 사용할 수 있습니다. 고유한 `id` 인수를 포함하여 여러 네트워크 메시지를 보낼 수 있지만, 단일 `RemoteEvent`만 사용합니다.

아래 예제에서 `ModuleScript`는 `ReplicatedFirst`에 있으며, `RemoteEvent:FireServer()` 메서드를 캡슐화하여 이 추가 `id` 인수를 포함합니다. 또한 이 `ModuleScript`는 다른 코드 부분에서 참조할 필요가 없도록 `RemoteEvent` 객체 자체를 참조합니다. 네트워크 메시지를 보내기 위해 이 `ModuleScript`를 요구하기만 하면 되고, 코드베이스의 나머지 부분에서는 `RemoteEvent` 객체를 다룰 필요가 없습니다.

다음 `ModuleScript`는 `ReplicatedFirst`에 있으며, 클라이언트 스크립트에서 네트워크 메시지를 보내는 데 사용할 수 있는 캡슐화된 함수를 제공합니다:

```lua title="네트워크 모듈"
-- ReplicatedFirst에 있는 ModuleScript, 이름은 NetworkManagerClient
local NetworkManagerClient = {}

local ReplicatedStorage = game:GetService("ReplicatedStorage")

local remoteEvent = ReplicatedStorage:WaitForChild("RemoteEvent")

-- 원격 객체의 FireServer 함수를 캡슐화
function NetworkManagerClient.FireServer(id, ...)
  remoteEvent:FireServer(id, ...)
end

return NetworkManagerClient
```

다음 `ModuleScript`는 `ServerScriptService`에 있으며, 각 스크립트가 특정 ID에 연결할 수 있는 `BindableEvents`를 사용합니다. 클라이언트가 네트워크 메시지를 보내면, 지정된 ID와 관련된 각 `BindableEvent`가 발생합니다.

```lua
-- ServerScriptService에 있는 ModuleScript, 이름은 NetworkManagerServer
local NetworkManagerServer = {}

local networkSignalList = {}
function NetworkManagerServer.GetServerEventSignal(id)
  local bindableEvent = Instance.new("BindableEvent")
  -- 새로운 BindableEvent를 id에 연결
  table.insert(networkSignalList, {
    id = id;
    bindableEvent = bindableEvent;
  })
  return bindableEvent.Event
end

-- 연결
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local remoteEvent = ReplicatedStorage:WaitForChild("RemoteEvent")
remoteEvent.OnServerEvent:Connect(function(player, id, ...)
  -- 수신된 원격 이벤트의 id와 일치하는 모든 바인더블 이벤트 찾기
  for _, signal in next, networkSignalList do
    if signal.id == id then
      signal.bindableEvent:Fire(player, ...)
    end
  end
end)

return NetworkManagerServer
```

다음 `LocalScript`는 `RequestA`라는 ID와 선택적 `Hello` 인수를 포함한 메시지를 보냅니다.

```lua
-- ReplicatedFirst에 있는 LocalScript
local ReplicatedFirst = game:GetService("ReplicatedFirst")

local NetworkManagerClient = require(ReplicatedFirst:WaitForChild("NetworkManagerClient"))
NetworkManagerClient.FireServer("RequestA", "Hello")
```

다음 `Script`는 `RequestA` 네트워크 메시지 ID에 연결되며, 요청을 받을 때 추가 매개 변수가 포함된 문구를 출력합니다.

```lua
-- ServerScriptService에 있는 스크립트
local ServerScriptService = game:GetService("ServerScriptService")

local NetworkManagerServer = require(ServerScriptService:WaitForChild("NetworkManagerServer"))
NetworkManagerServer.GetServerEventSignal("RequestA"):Connect(function(player, ...)
  print("Received RequestA from", player, ...)
end)
```

---
## 출처
 - [Reusing Code](https://create.roblox.com/docs/scripting/module)

---
## [다음](./04_03_Services.md)