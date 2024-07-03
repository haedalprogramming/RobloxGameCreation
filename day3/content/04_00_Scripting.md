# Scripting

## 목차
- [Scripting](#scripting)
  - [목차](#목차)
  - [Luau](#luau)
    - [Luau 기본 사항](#luau-기본-사항)
  - [첫 번째 스크립트](#첫-번째-스크립트)
  - [익숙해지기](#익숙해지기)
  - [두 번째 스크립트](#두-번째-스크립트)
  - [출처](#출처)
  - [다음](#다음)

---

스크립트는 경험에 맞춤형 동적 동작을 추가할 수 있는 텍스트 파일입니다. 스크립트를 사용하여 게임 내 이벤트를 트리거하고, 플레이어 입력에 응답하며, 플레이어 데이터를 저장하고, 리더보드를 생성하고, 적을 생성하고, NPC 동작을 제어하는 등 다양한 작업을 수행할 수 있습니다.

<Alert severity="success">
이 섹션은 Roblox에서 스크립팅에 대해 구체적으로 알고자 하는 코딩 경험이 있는 창작자를 위한 것입니다.

코드를 처음 작성해보는 경우, 변수, 함수, 조건문, 루프 및 배열과 같은 개념을 다루는 코딩 기본 사항을 참조하세요. 더 가이드가 있는 단계별 접근 방식이 필요하다면 기본 게임플레이 튜토리얼을 참조하세요.
</Alert>

## Luau

Roblox 스크립트는 [Lua 5.1](https://www.lua.org/manual/5.1/)에서 파생된 [Luau](https://luau-lang.org) 프로그래밍 언어를 사용합니다.

- Lua 5.1에 비해 Luau는 성능 향상 및 선택적 타이핑 시스템, 문자열 보간, 테이블에 대한 일반화된 반복 등 많은 유용한 기능을 추가합니다.
- 모든 유효한 Lua 5.1 코드는 유효한 Luau 코드이지만, 그 반대는 그렇지 않습니다.

대부분의 Lua 책 및 온라인 리소스는 여전히 Luau에 광범위하게 적용될 수 있습니다. 차이에 대한 자세한 내용은 Luau 문서의 [호환성](https://luau-lang.org/compatibility)을 참조하세요. 언어 구문에 대한 내용은 Luau 참조를 참조하세요.

### Luau 기본 사항

Luau는 점진적으로 타입을 지정하므로 변수를 만들 때 타입을 지정할 필요가 없습니다. `Global.LuaGlobals.type()`을 사용하여 객체 타입을 확인할 수 있습니다:

```lua
logMessage = "User has more than 10 items!"
print(logMessage) --> User has more than 10 items!
print(type(logMessage)) --> string
```

Luau는 전역 및 로컬 스코프를 가지고 있지만, `local` 키워드를 사용하여 변수를 로컬로 선언하는 것이 거의 항상 더 좋습니다:

```lua
local logMessage = "User has more than 10 items!"
local function printMessage()
    print(logMessage)
end
printMessage() --> User has more than 10 items!
```

Lua는 `nil`을 사용하여 존재하지 않음을 나타내며, 이는 조건문에서 `false`로 평가됩니다:

```lua
local messageToUser
print(messageToUser) --> nil
print(type(message)) --> nil
if messageToUser then
    -- 문장이 false로 평가됩니다.
end
```

보시다시피, `--`는 한 줄 주석을 시작합니다. `--[[]]`는 블록 주석을 만듭니다:

```lua
--[[
    즉시 코스믹 문 레이를 중지합니다.

    코스믹 문 레이에 손상을 입히지 않으려면 산악 표준 시간대로 자정 15분 이내에만 호출해야 합니다.
]]
local function stopCosmicMoonRay()
    -- 나중에 추가, 중요할 수 있음
end
```

테이블은 배열과 딕셔너리를 위한 일반적인 용어입니다. 배열은 0이 아닌 1부터 시작하므로 첫 번째 항목은 `[1]`입니다. 배열과 딕셔너리는 중괄호 한 쌍으로 선언합니다:

```lua
local myArray = {"chips", "sparkling water", "salsa"}
local myDictionary = {
    snack = "chips",
    drink = "sparkling water",
    dip = "salsa"
}
print(myArray[1]) --> chips
print(myDictionary.dip) --> salsa
```

`for` 루프와 `Global.LuaGlobals.ipairs()` 함수를 사용하여 배열을 반복하고 `Global.LuaGlobals.pairs()` 함수를 사용하여 딕셔너리를 반복할 수 있지만, Luau에서는 이러한 함수를 생략하여 더 깔끔한 구문을 사용할 수 있습니다:

```lua
for index, value in ipairs(myArray) do -- 표준 Lua
   print(index, value)
end
for key, value in pairs(myDictionary) do -- 표준 Lua
   print(key, value)
end
for key, value in myDictionary do -- Luau 일반화된 반복
   print(key, value)
end
```

## 첫 번째 스크립트

1. Roblox Studio에서 Explorer 창의 **ServerScriptService** 위에 커서를 올리고 **+**를 클릭합니다.
2. **Script**를 선택하여 새 스크립트를 추가합니다.
3. 스크립트를 마우스 오른쪽 버튼으로 클릭하고 `HelloScript`로 이름을 변경합니다.
4. 스크립트를 두 번 클릭하여 Script Editor에서 엽니다.
5. 파일에 다음 코드를 추가합니다:

   ```lua
   local helloArray = {'h', 'e', 'l', 'l', 'o'}
   local worldArray = {'w', 'o', 'r', 'l', 'd'}

   for index, value in helloArray do
       print(value)
   end

   print(table.concat(worldArray))
   ```

6. Output 창이 열려 있는지 확인합니다.
7. **Play**를 클릭하여 경험을 실행합니다.
8. 출력을 확인합니다:

   ```text
   h
   e
   l (x2)
   o
   world
   ```

## 익숙해지기

새로운 개발 환경에 적응하는 큰 부분은 자신의 필요에 맞게 환경을 구성하고 사용할 수 있는 도구를 이해하는 것입니다:

- **Studio Settings**의 **Script Editor** 섹션에서는 글꼴, 색상, 들여쓰기, 자동 완성, 괄호, 툴팁과 같은 편의 기능을 조정할 수 있습니다. 또한 **Studio** 섹션에서 다크 모드를 활성화할 수도 있습니다.
- <kbd>Ctrl</kbd> 또는 <kbd>Command</kbd> 키를 누르고 함수나 변수를 클릭하면 코드베이스 내 선언 위치로 이동하거나 온라인 문서로 이동할 수 있습니다. [Find and Find All]을 사용하여 더 큰 프로젝트를 탐색할 수도 있습니다.
- Output 창은 스크립트 동작을 이해하는 가장 기본적인 도구입니다. **&#x22EF;** 메뉴를 사용하여 **Show Context** 및 **Show Source**를 활성화할 수 있습니다.
- **Script Analysis** 창은 오류와 경고의 요약을 표시하지만, Script Editor가 이미 입력할 때 이러한 문제를 강조 표시하므로 그 유용성이 제한될 수 있습니다.
- 로깅 기능은 최소한으로 제공되며 `DEBUG` 또는 `FATAL`과 같은 로그 레벨 개념이 없습니다. `Global.LuaGlobals.print()` 및 `Global.RobloxGlobals.warn()`을 사용하십시오.

스크립팅을 위한 Studio 설정 구성에 대한 자세한 내용은 Script Editor를 참조하세요. 선호하는 텍스트 편집기와 버전 관리 시스템을 사용하는 방법에 대한 내용은 External Tools를 참조하세요.

## 두 번째 스크립트

1. Roblox Studio에서 Explorer 창의 **ReplicatedStorage**에 스크립트를 추가하고 `OhNo`로 이름을 변경합니다.
2. 파일에 다음 코드를 추가합니다:

   ```lua
   print("Hello script types and locations!")
   ```

3. **Play**를 클릭하여 경험을 실행합니다.
4. 첫 번째 스크립트를 실행했을 때와 출력이 다른지 확인합니다.

스크립트가 실행되지 않은 이유를 이해하려면 `스크립트 유형 및 위치`를 참조하세요.

---
## 출처
 - [Scripting](https://create.roblox.com/docs/ko-kr/scripting)

---
## [다음](./04_01_Script_Types_and_Locations.md)