# Coding a Question

## 목차
- [Coding a Question](#coding-a-question)
  - [목차](#목차)
  - [변수 생성하기](#변수-생성하기)
  - [변수 설정하기](#변수-설정하기)
  - [질문 입력하기](#질문-입력하기)
  - [출처](#출처)
  - [다음](#다음)

---

이전에 작성한 문장에서 단어를 자리 표시자로 바꾸었던 것을 기억하나요? 이제 플레이어에게 경험에 무언가를 추가할 기회를 줄 시간입니다.

스크립트에서 만든 자리 표시자는 **변수**가 될 것입니다. 코딩에서 변수는 정보를 저장하는 자리 표시자로, 이 경우에는 단어를 저장합니다.

플레이어에게 질문을 하고, 그들이 입력한 답변을 **변수**에 **저장**하게 됩니다.

## 변수 생성하기

변수에는 저장하는 정보를 설명하는 이름이 있습니다. 이번에는 자리 표시자를 위한 `name1`이라는 변수를 만들겠습니다.

1. 대시 라인 아래에 `local name1`을 입력합니다.

   ```lua
   -- GLOBAL VARIABLES
   local storyMaker = require(script:WaitForChild("StoryMaker"))

   -- Code controlling the game
   local playing = true

   while playing do
     storyMaker:Reset()

     -- Code story between the dashes
     -- =============================================
        local name1

     -- =============================================

     -- Add the story variable between the parenthesis below
     storyMaker:Write()

     -- Play again?
     playing = storyMaker:PlayAgain()
   end
   ```

## 변수 설정하기

이제 플레이어가 자리 표시자에 무언가를 입력할 기회를 줘야 합니다. 변수를 변경하려면 **=** 기호를 사용하여 **설정**해야 합니다.

1. `name1` 뒤에 공백을 추가한 후 `=`를 입력합니다.

   ```lua
   while playing do
     storyMaker:Reset()

     -- Code story between the dashes
     -- =============================================
        local name1 =

     -- =============================================

     -- Add the story variable between the parenthesis below
     storyMaker:Write()
   end
   ```

2. 등호 뒤에 `storyMaker:GetInput()`을 입력합니다. 코드는 정확히 입력해야 하며, 대문자도 일치해야 합니다.

   ```lua
   while playing do
     storyMaker:Reset()

     -- Code story between the dashes
     -- =============================================
        local name1 = storyMaker:GetInput()

     -- =============================================

     -- Add the story variable between the parenthesis below
     storyMaker:Write()
   end
   ```

## 질문 입력하기

변수는 작은 숫자, 참 또는 거짓 값, 그리고 문자열 등 다양한 유형의 데이터를 저장할 수 있습니다. **문자열** 유형의 변수는 전체 문장을 저장할 수 있기 때문에 특별합니다. 문자열 변수는 항상 따옴표 안에 있기 때문에 쉽게 구별할 수 있습니다. "이렇게".

플레이어에게 질문할 내용은 문자열 변수로 설정됩니다.

1. `GetInput()`의 괄호 **사이**에 클릭합니다. 괄호 안에 따옴표로 묶인 질문을 입력합니다.

   ```lua
     -- Code story between the dashes
     -- =============================================
        local name1 = storyMaker:GetInput("What is your favorite name?")

     -- =============================================
   end
   ```

---
## 출처
[Start Coding](https://create.roblox.com/docs/ko-kr/education/build-it-play-it-story-games/coding-a-question)

---
## [다음](07_07_Test_and_Save.md)
