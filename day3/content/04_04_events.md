# Events

## 목차
- [Events](#events)
  - [목차](#목차)
  - [이벤트에 함수 연결하기](#이벤트에-함수-연결하기)
  - [이벤트에서 함수 연결 해제하기](#이벤트에서-함수-연결-해제하기)
  - [이벤트가 발생할 때까지 기다리기](#이벤트가-발생할-때까지-기다리기)
  - [다른 유형의 이벤트](#다른-유형의-이벤트)
  - [출처](#출처)
  - [다음](#다음)

---

이벤트는 경험 내에서 발생하는 사건으로, 이를 듣고 응답할 수 있습니다. 많은 Roblox 서비스와 객체는 특정 행동이나 변화에 반응하여 자동으로 **발생**하는 내장 이벤트를 가지고 있습니다.

예를 들어, 플레이어의 `Character`가 `BasePart`를 만지면 자동으로 `Touched` 이벤트가 발생합니다. 플레이어가 경험에 참여할 때마다 `Players.PlayerAdded` 이벤트가 발생합니다.

이벤트의 수와 클라이언트-서버 아키텍처로 인해, Roblox 스크립팅은 종종 **이벤트 중심**이라고 불립니다. 이 접근 방식은 많은 다른 게임 엔진이 프레임 단위로 코드를 실행하는 것을 강조하는 것과 다릅니다.

이벤트를 듣거나 이에 반응하기 위한 조치를 취하지 않아도 되지만, 이벤트는 발생하고 사용할 수 있습니다. 이벤트에 응답하고 싶을 때, 함수와 연결합니다.

## 이벤트에 함수 연결하기

이벤트가 발생할 때마다 코드를 실행하기 위해 `Connect()`를 사용하여 함수를 이벤트에 연결합니다. 대부분의 이벤트는 연결된 함수에 인수를 전달합니다. 예를 들어, `BasePart.Touched` 이벤트는 부품을 만진 객체(예: 왼손 또는 자동차 바퀴)를 전달하고, `Players.PlayerAdded` 이벤트는 경험에 참여한 `Player`를 전달합니다.

다음 코드 샘플은 `onPartTouched()`라는 함수를 부품의 `Touched` 이벤트에 연결하는 방법을 보여줍니다:

```lua
-- 스크립트가 부품에 부모로 설정되어 있다고 가정
local part = script.Parent

-- 실행할 함수
local function onPartTouched(object)
    print("부품이", object:GetFullName(), "에 의해 만져졌습니다.")
end

-- 함수를 부품의 Touched 이벤트에 연결
part.Touched:Connect(onPartTouched)
```

부모 범위에서 변수를 사용하고 함수가 다른 곳에서 필요하지 않을 때, 익명 함수를 이벤트에 연결할 수도 있습니다. 예를 들어, 이 코드 샘플은 서비스의 유사한 샘플에서 중간 함수를 피합니다:

```lua
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local SaveManager = require(ReplicatedStorage:WaitForChild("SaveManager"))

local function saveProgress(character)
    local position = character:FindFirstChild("HumanoidRootPart").Position
    SaveManager.saveData(character, position)
end

-- 플레이어가 경험에서 제거될 때 (이 경우 플레이어가 나갈 때) saveProgress()를 호출하는 익명 함수
Players.PlayerAdded:Connect(function(player)
    player.CharacterRemoving:Connect(saveProgress)
end)
```

## 이벤트에서 함수 연결 해제하기

`Connect()` 메서드는 `Datatype.RBXScriptConnection` 객체를 반환합니다. 함수를 이벤트에 연결했지만, 어떤 조건이 충족된 후에는 이벤트가 발생할 때 함수를 호출하지 않으려면 `Datatype.RBXScriptConnection` 객체의 `Disconnect()`를 호출하여 연결을 해제할 수 있습니다.

다음 코드 샘플은 `Part.Touched` 이벤트에서 함수를 연결하고 연결 해제하는 방법을 보여줍니다:

```lua
local part = workspace.Part
local targetPart = workspace.TargetPart

-- 연결에 대한 빈 자리 변수 선언
local connection

local function onPartTouched(otherPart)
    if otherPart == targetPart then
        print("부품이 목표를 맞췄습니다!")
        -- 연결 해제
        connection:Disconnect()
    end
end

-- 위의 함수를 Touched 이벤트에 연결
connection = part.Touched:Connect(onPartTouched)
```

함수를 이벤트에 한 번만 연결하고 싶다면, 즉, 이벤트가 처음 발생할 때만 함수를 실행하려면, 함수 연결 및 연결 해제의 더 편리한 대안으로 `Once()` 메서드를 사용할 수 있습니다.

<Alert severity="info">
Luau가 이벤트의 객체를 파괴할 때, 예를 들어 사용자가 경험을 떠날 때 `Player` 객체가 파괴되는 경우, 모든 연결이 자동으로 해제됩니다.
</Alert>

## 이벤트가 발생할 때까지 기다리기

특정 이벤트가 발생할 때까지 스크립트를 대기하려면 `Wait()` 메서드를 사용합니다. 이 메서드는 이벤트의 인수를 반환하며, 나중에 사용할 변수에 할당할 수 있습니다:

```lua
local part = workspace.Part
local touchedPart = part.Touched:Wait()
print("부품이", touchedPart:GetFullName(), "에 의해 만져졌습니다.")
```

## 다른 유형의 이벤트

- 바인더블 이벤트

  바인더블 이벤트는 클라이언트-서버 경계의 **같은 쪽**에서 스크립트 간 통신을 가능하게 합니다.

- 리모트 이벤트

  리모트 이벤트는 클라이언트-서버 경계를 **가로질러** 통신을 가능하게 합니다.

---
## 출처
 - [Events](https://create.roblox.com/docs/scripting/events)

---
## [다음](./04_05_bindable.md)