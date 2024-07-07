# Bindable Events and Callbacks

## 목차
- [Bindable Events and Callbacks](#bindable-events-and-callbacks)
  - [목차](#목차)
  - [바인더블 이벤트](#바인더블-이벤트)
  - [커스텀 콜백](#커스텀-콜백)
  - [인수 제한](#인수-제한)
    - [비문자열 인덱스](#비문자열-인덱스)
    - [테이블 인덱싱](#테이블-인덱싱)
    - [테이블 정체성](#테이블-정체성)
    - [메타테이블](#메타테이블)
  - [출처](#출처)
  - [다음](#다음)

---

`BindableEvent`와 `BindableFunction` 객체를 사용하면 서버 또는 클라이언트 **동일한 측면**에서 스크립트 간의 경계를 넘어 행동을 연결하고, 경험 내에서 원하는 결과를 구체적으로 전달할 수 있습니다.

바인더블 이벤트의 가장 일반적인 사용 사례는 라운드 기반 구조를 가진 경험입니다. 예를 들어, 다른 스크립트가 타이머를 시작하고 리더보드를 표시할 수 있도록 하는 "경기 시작" 이벤트와, 다른 스크립트가 플레이어를 로비로 이동시키고 우승자를 표시할 수 있도록 하는 "경기 종료" 이벤트가 있습니다.

바인더블 이벤트는 스크립트 간의 활동을 조정하기 때문에 일반적으로 서버에서 사용되지만, 클라이언트에서도 사용할 수 있습니다.

경험의 작동 방식에 따라 바인더블 이벤트는 코드 모듈화를 도울 수 있지만, 모듈 스크립트는 스크립트 간에 데이터를 공유해야 하는 상황에서 더 나은 대안이 될 수 있습니다. 또한 커스텀 이벤트에서 언급한 대로, 더 깔끔한 구문을 위해 모듈 스크립트와 함께 바인더블 이벤트를 사용할 수도 있습니다.

<Alert severity="info">
클라이언트-서버 경계를 **넘어** 스크립트 간 통신을 위해서는 리모트 이벤트를 참조하세요.
</Alert>

## 바인더블 이벤트

`BindableEvent` 객체는 스크립트 간 비동기 단방향 통신을 통해 커스텀 이벤트를 가능하게 합니다.

`BindableEvent:Fire()|Fire()` 메서드를 통해 `BindableEvent`를 발생시키면, 발생시키는 스크립트는 **멈추지 않으며**, 대상 함수는 특정 제한 사항과 함께 전달된 인수를 받습니다. 모든 이벤트와 마찬가지로, `BindableEvents`는 각 연결된 함수의 스레드를 생성하므로, 하나가 오류가 발생해도 다른 스레드는 계속 실행됩니다.

Explorer 창을 사용하여 새 `BindableEvent`를 생성하려면 다음 단계를 따르세요:

1. `BindableEvent`를 삽입할 컨테이너 위에 마우스를 올립니다. 서버 스크립트 간 통신을 위해서는 `ServerScriptService`를, 클라이언트 스크립트 간 통신을 위해서는 `ReplicatedStorage`를 사용하는 것이 좋습니다.
2. 컨테이너 이름 오른쪽에 나타나는 **&CirclePlus;** 버튼을 클릭하고 **BindableEvent** 인스턴스를 삽입합니다.
3. 인스턴스 이름을 `TestBindableEvent`로 변경합니다.

`BindableEvent`를 생성한 후, 한 스크립트에서 그 이벤트의 `Event` 이벤트에 함수를 연결하고, 다른 스크립트에서 그 이벤트를 `Fire()`합니다.

```lua title="이벤트 연결"
local ServerScriptService = game:GetService("ServerScriptService")

-- 바인더블 이벤트 인스턴스 참조 얻기
local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

-- 익명 함수를 이벤트에 연결
bindableEvent.Event:Connect(function(data)
    print(data)  --> 라운드 시작!
end)
```

```lua title="이벤트 발생"
local ServerScriptService = game:GetService("ServerScriptService")

-- 바인더블 이벤트 인스턴스 참조 얻기
local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

-- 바인더블 이벤트 발생
bindableEvent:Fire("라운드 시작!")
```

<Alert severity="warning">
여러 함수를 동일한 `BindableEvent`에 연결할 수 있지만, Luau는 이를 예측할 수 없는 순서로 실행합니다. 특정 순서로 함수가 실행되도록 보장하려면 함수를 하나의 함수로 결합하고 이벤트에 연결하세요.
</Alert>

## 커스텀 콜백

`BindableFunction` 객체는 스크립트 간 동기, 양방향 통신을 가능하게 합니다. 이를 사용하여 커스텀 콜백 함수를 정의하고 `BindableFunction:Invoke()`를 호출하여 수동으로 호출할 수 있습니다. 함수를 호출하는 코드는 **멈추며**, 콜백이 발견될 때까지 기다립니다. 콜백은 `Invoke()`에 전달된 인수를 받습니다. 콜백이 설정되지 않은 경우, 이를 호출한 스크립트는 실행을 재개하지 않습니다.

Explorer 창을 사용하여 새 `BindableFunction`을 생성하려면 다음 단계를 따르세요:

1. `BindableFunction`를 삽입할 컨테이너 위에 마우스를 올립니다. 서버 스크립트 간 통신을 위해서는 `ServerScriptService`를, 클라이언트 스크립트 간 통신을 위해서는 `ReplicatedStorage`를 사용하는 것이 좋습니다.
2. 컨테이너 이름 오른쪽에 나타나는 **&CirclePlus;** 버튼을 클릭하고 **BindableFunction** 인스턴스를 삽입합니다.
3. 인스턴스 이름을 `TestBindableFunction`으로 변경합니다.

`BindableFunction`을 생성한 후, 한 스크립트에서 그 함수의 `OnInvoke` 콜백에 연결하고, 다른 스크립트에서 그 콜백 함수를 `Invoke()`합니다.

```lua title="콜백 연결"
local ServerScriptService = game:GetService("ServerScriptService")

-- 바인더블 함수 참조 얻기
local bindableFunction = ServerScriptService:WaitForChild("TestBindableFunction")

-- 콜백 함수
local function addTwoNumbers(a, b)
    return a + b
end

-- 함수를 바인더블 함수의 콜백으로 설정
bindableFunction.OnInvoke = addTwoNumbers
```

```lua title="이벤트 호출"
local ServerScriptService = game:GetService("ServerScriptService")

-- 바인더블 함수 참조 얻기
local bindableFunction = ServerScriptService:WaitForChild("TestBindableFunction")

-- 콜백 함수 호출 및 반환 값 출력
local sum = bindableFunction:Invoke(2, 4)
print(sum)  --> 6
```

<Alert severity="warning">
각 `BindableFunction`은 하나의 `OnInvoke` 콜백만 사용할 수 있습니다. 여러 정의를 만들면, 마지막에 할당된 것만 실행됩니다. 또한, `OnInvoke` 콜백에 `return` 문이 없으면 호출은 `nil`을 반환합니다.
</Alert>

## 인수 제한

`BindableEvent`를 발생시키거나 `BindableFunction`을 호출할 때, 이벤트 또는 콜백 함수에 전달된 모든 인수를 전달합니다. Roblox 객체(`Datatype.Enum`, `Instance` 등)뿐만 아니라 숫자, 문자열, 부울과 같은 Luau 타입을 전달할 수 있지만, 다음 제한 사항을 주의 깊게 고려해야 합니다.

### 비문자열 인덱스

전달된 테이블의 **인덱스**가 `Instance`, userdata, 또는 function과 같은 비문자열 타입인 경우, Roblox는 해당 인덱스를 자동으로 문자열로 변환합니다.

```lua title="이벤트 연결"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

local function onEventFire(passedTable)
    for k, v in passedTable do
        print(typeof(k))  --> string
    end
end

-- 함수를 이벤트에 연결
bindableEvent.Event:Connect(onEventFire)
```

```lua title="이벤트 발생"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

-- 작업 공간 인스턴스를 키로 가지는 테이블과 함께 이벤트 발생
bindableEvent:Fire({
    [workspace.Baseplate] = true
})
```

### 테이블 인덱싱

데이터 테이블을 전달할 때, 숫자 키와 문자열 키가 혼합된 테이블을 전달하지 마세요. 대신, **키-값 쌍**(사전) 또는 **숫자 인덱스**(배열)로 구성된 테이블을 전달하세요.

<Alert severity="warning">
사전 테이블 **또는** 숫자 인덱스 테이블을 전달할 때, 어떤 인덱스에도 `nil` 값을 사용하지 마세요.
</Alert>

```lua title="이벤트 연결"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

local function onEventFire(passedTable)
   

 for k, v in passedTable do
        print(k .. " = " .. v)
        --> 1 = Sword
        --> 2 = Bow
        --> CharName = Diva Dragonslayer
        --> CharClass = Rogue
    end
end

-- 함수를 이벤트에 연결
bindableEvent.Event:Connect(onEventFire)
```

```lua title="이벤트 발생"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

-- 숫자 인덱스 테이블
local inventoryData = {
    "Sword", "Bow"
}
-- 사전 테이블
local characterData = {
    CharName = "Diva Dragonslayer",
    CharClass = "Rogue"
}

-- 일관된 인덱스의 테이블로 이벤트 발생
bindableEvent:Fire(inventoryData)
bindableEvent:Fire(characterData)
```

### 테이블 정체성

바인더블 이벤트 및 콜백에 인수로 전달된 테이블은 복사되므로, 이벤트 발생 또는 콜백 호출 시 제공된 테이블과 정확히 동일하지 않습니다. 반환된 테이블도 제공된 것과 정확히 동일하지 않습니다. 다음 스크립트를 `BindableFunction`에 실행하고 테이블 정체성이 어떻게 다른지 관찰하여 이를 확인할 수 있습니다.

```lua title="콜백 연결"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableFunction = ServerScriptService:WaitForChild("TestBindableFunction")

-- 콜백 함수
local function returnTable(passedTable)
    -- 호출 시 테이블 정체성 출력
    print(tostring(passedTable))  --> table: 0x48eb7aead27563d9
    return passedTable
end

-- 함수를 바인더블 함수의 콜백으로 설정
bindableFunction.OnInvoke = returnTable
```

```lua title="이벤트 호출"
local ServerScriptService = game:GetService("ServerScriptService")

local bindableFunction = ServerScriptService:WaitForChild("TestBindableFunction")

local inventoryData = {
    "Sword", "Bow"
}
-- 원래 테이블 정체성 출력
print(tostring(inventoryData))  --> table: 0x059bcdbb2b576549

local invokeReturn = bindableFunction:Invoke(inventoryData)

-- 반환 시 테이블 정체성 출력
print(tostring(invokeReturn))  --> table: 0x9fcae7919563a0e9
```

### 메타테이블

테이블에 메타테이블이 있는 경우, 모든 메타테이블 정보는 전송 중에 손실됩니다. 다음 코드 샘플에서 `NumWheels` 속성은 `Car` 메타테이블의 일부입니다. 서버가 다음 테이블을 받으면, `truck` 테이블은 `Name` 속성을 가지고 있지만 **`NumWheels` 속성은 없습니다**.

```lua title='이벤트 연결'
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

local function onEvent(param)
    print(param)  --> {["Name"] = "MyTruck"}
end

-- 함수를 이벤트에 연결
bindableEvent.Event:Connect(onEvent)
```

```lua title='이벤트 발생'
local ServerScriptService = game:GetService("ServerScriptService")

local bindableEvent = ServerScriptService:WaitForChild("TestBindableEvent")

local Car = {}
Car.NumWheels = 4
Car.__index = Car

local truck = {}
truck.Name = "MyTruck"
setmetatable(truck, Car)

-- 메타테이블이 포함된 테이블과 함께 이벤트 발생
bindableEvent:Fire(truck)
```

---
## 출처
 - [Bindable Events and Callbacks](https://create.roblox.com/docs/scripting/events/bindable)

---
## [다음](./04_06_remote.md)