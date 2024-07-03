# Users and Players

## 목차
- [Users and Players](#users-and-players)
  - [목차](#목차)
  - [생명주기](#생명주기)
    - [사용자 참여](#사용자-참여)
      - [참여 시 사용자 데이터 로드](#참여-시-사용자-데이터-로드)
    - [사용자 퇴장](#사용자-퇴장)
      - [퇴장 시 사용자 데이터 저장](#퇴장-시-사용자-데이터-저장)
    - [캐릭터 생성](#캐릭터-생성)
    - [캐릭터 제거](#캐릭터-제거)
      - [플레이어 사망 카운트](#플레이어-사망-카운트)
  - [사용자 차단](#사용자-차단)
    - [차단 지침](#차단-지침)
    - [메시지 지침](#메시지-지침)
  - [컨테이너](#컨테이너)
    - [Backpack](#backpack)
    - [StarterGear](#startergear)
    - [PlayerGui](#playergui)
    - [PlayerScripts](#playerscripts)
  - [출처](#출처)
  - [다음](#다음)

---

사용자가 경험에 참여할 때, Roblox는 데이터를 모델링하여 그들을 **플레이어**로 나타냅니다. `Player` 객체에는 사용자 이름, 친구 목록, 저장된 아바타 캐릭터, Roblox 멤버십 유형 등의 정보와 사용자의 경험에서의 생명주기에 영향을 미치는 속성, 메서드 및 이벤트가 포함됩니다.

`Players` 서비스에는 경험 내의 모든 `Player` 인스턴스가 포함됩니다. 각 `Player` 객체는 경험 내의 사용자를 나타내며, 사용자의 경험을 커스터마이징하는 데 사용할 수 있는 네 가지 중요한 컨테이너인 `Backpack`, `StarterGear`, `PlayerGui`, `PlayerScripts`를 부모로 설정합니다.

## 생명주기

클라이언트 및 서버 측 스크립트는 `Players.PlayerAdded` 및 `Players.PlayerRemoved` 이벤트에 연결하여 `Player` 객체의 생명주기에 따라 작업을 수행할 수 있습니다. 또한 `Player.CharacterAdded`, `Player.CharacterRemoving`, 및 `Humanoid.Died` 이벤트에 연결하여 캐릭터가 생성, 삭제, 사망할 때 게임 관련 작업을 수행할 수 있습니다.

사용자가 접속하거나 떠날 때 데이터를 검색하고 저장하기 위해 데이터 저장소와 같은 서버 관련 서비스를 접근하려면 스크립트를 사용하세요. 클라이언트가 새 사용자와 연결된 게임 플레이 인스턴스를 생성 및 제거해야 하는 경우에는 LocalScripts를 사용하세요.

### 사용자 참여

클라이언트가 경험에 연결되면 해당 클라이언트와 연결된 `Player` 객체가 `Players` 서비스에 복제됩니다. `Players.PlayerAdded` 이벤트는 사용자가 경험에 참여하는 것을 나타냅니다. 예를 들어 사용자 데이터를 로드하거나 팀을 할당하고 사용자 캐릭터의 의상을 변경하는 등의 작업을 수행할 수 있습니다. `Players.PlayerAdded` 이벤트는 참여하는 사용자의 `Player` 객체를 전달하며, 이를 다른 함수(예: 데이터 저장소 및 `RemoteEvent` 객체) 호출에 사용할 수 있습니다.

#### 참여 시 사용자 데이터 로드

사용자가 경험에 참여할 때 사용자 데이터를 로드하려면 `Script`에서 `Players.PlayerAdded` 이벤트를 사용하세요. 다음 예제 `Script`는 이벤트를 수신하고 사용자 ID를 데이터 저장소 키로 사용하여 사용자 데이터를 검색하려고 시도합니다. 사용자 데이터를 성공적으로 검색한 후에는 이를 사용하여 사용자의 진행 상황과 통계를 로드할 수 있습니다.

```lua Script in ServerScriptService
local DataStoreService = game:GetService("DataStoreService")
local playerDataStore = DataStoreService:GetDataStore("PlayerData")

game:GetService("Players").PlayerAdded:Connect(function(player)
	local userId = player.UserId

	-- Read data store key
	local getSuccess, currentData = pcall(function()
		return playerDataStore:GetAsync(userId)
	end)

	if getSuccess then
		print(currentData)
	end

	-- Do further actions with currentData
end)
```

<Alert severity = 'info'>
`Player` 객체의 `Instance.Name`은 사용자의 이름입니다. 데이터 저장소에 대한 정보를 저장하려면 사용자 이름 대신 `Player.UserId`를 사용하세요. 사용자 이름은 변경될 수 있지만 UserId는 변경되지 않습니다.
</Alert>

### 사용자 퇴장

클라이언트가 경험에서 연결 해제될 때, 서버는 `Players` 서비스에서 해당 클라이언트와 연결된 `Player` 객체를 제거합니다. `Players.PlayerRemoving` 이벤트는 사용자가 경험을 떠나는 것을 나타냅니다. 예를 들어 사용자 데이터를 저장하거나 점수판에서 사용자의 통계를 제거하고 사용자의 모델(예: 집)을 제거하는 등의 작업을 수행할 수 있습니다. `Players.PlayerRemoving` 이벤트는 떠나는 사용자의 `Player` 객체를 전달하며, 이를 다른 함수(예: 데이터 저장소 및 `RemoteEvent` 객체) 호출에 사용할 수 있습니다.

이 이벤트는 `Player.PlayerRemoved`가 아니라 `Player.PlayerRemoving`이라고 불립니다. "removed"는 `Player` 객체가 이미 제거되어 스크립트에서 접근할 수 없음을 의미하기 때문입니다.

#### 퇴장 시 사용자 데이터 저장

사용자가 경험을 떠날 때 사용자 데이터를 저장하려면 `Script`에서 `Players.PlayerRemoving` 이벤트를 사용하세요. 다음 예제 `Script`는 이벤트를 수신하고 사용자 ID를 데이터 저장소 키로 사용하여 사용자 데이터를 저장하려고 시도합니다.

```lua title='Script in ServerScriptService'
local DataStoreService = game:GetService("DataStoreService")
local playerDataStore = DataStoreService:GetDataStore("PlayerData")

game:GetService("Players").PlayerRemoving:Connect(function(player)
	local userId = player.UserId

	-- Get the player's data state in the game
	local currentData = getCurrentData(player)

	-- Save to data store
	local setSuccess, errorMessage = pcall(function()
	    playerDataStore:SetAsync(userId, currentData)
	end)

	if not setSuccess then
	    warn(errorMessage)
	end
end)
```

### 캐릭터 생성

사용자의 `Player.Character` 모델은 아바타를 나타냅니다. 기본적으로 `Player.CharacterAutoLoads`는 true로 설정되어 있으며 사용자가 경험에 참여하면 사용자 캐릭터 모델이 자동으로 생성됩니다. `Player.CharacterAutoLoads`가 false로 설정된 경우 `Player:LoadCharacter()`를 호출하여 수동으로 캐릭터를 생성해야 합니다.

사용자의 `Player.Character`가 생성되면 `StarterCharacterScripts`에 있는 스크립트와 LocalScripts가 캐릭터 모델로 복제되고 `Player.CharacterAdded` 이벤트가 발생합니다. `Player.CharacterAdded` 이벤트는 새로운 캐릭터 모델을 이벤트 리스너에 전달하며, 이를 사용하여 캐릭터의 `Humanoid` 객체를 찾아 그 동작을 수정할 수 있습니다. 예를 들어 `Humanoid:ApplyDescription()`을 사용하여 아바타의 의상을 변경하고 `Humanoid.WalkSpeed` 또는 `Humanoid.JumpHeight`를 사용하여 아바타의 이동을 수정할 수 있습니다.

### 캐릭터 제거

사용자의 `Humanoid`가 사망하면 몸의 부품이 땅에 떨어지고 `Humanoid.Died` 이벤트가 발생합니다. 서버는 `Players.Respawntime` 속성에 의해 결정된 시간이 지난 후 캐릭터 모델과 내부 스크립트를 자동으로 제거합니다. `Player.CharacterRemoving` 이벤트를 사용하여 캐릭터와 관련된 다른 객체를 재설정할 수 있습니다. 예를 들어, 사용자가 운전하던 차량의 네트워크 소유권을 재설정할 수 있습니다.

#### 플레이어 사망 카운트

`Humanoid.Died` 이벤트를 사용하여 킬을 위한 점수를 처리하거나 사용자 정의 래그돌 모델을 생성할 수 있습니다. 다음 `Script`는 각 사용자의 캐릭터 모델을 검색하기 위해 `Player.CharacterAdded`에 연결한 후 캐릭터의 `Humanoid` 객체에 연결합니다. `Humanoid.Died` 이벤트가 발생하면 스크립트는 사용자 `Humanoid`가 사망한 횟수를 증가시키고 해당 횟수를 출력합니다.

```lua title='Script in ServerScriptService'
game:GetService("Players").PlayerAdded:Connect(function(player)
	local deaths = 0
	player.CharacterAdded:Connect(function(character)
		local humanoid = character:WaitForChild("Humanoid")
		humanoid.Died:Connect(function()
			deaths += 1
			print(player.Name .. " death count: " .. deaths)
		end)
	end)
end)
```

## 사용자 차단

경험에서 규칙과 커뮤니티 지침을 위반하는 사용자를 차단하여 공정한 플레이를 보장할 수 있습니다. 차단 기간, 차단 메시지를 수정하고 잠재적 부계정에도 차단을 적용할 수 있습니다. 이 기능을 사용할 때는 차단 지침 및 메시지 지침을 따라야 합니다.

구현 및 사용 방법에 대한 자세한 내용은 `Players.BanAsync`를 참조하세요.

### 차단 지침

경험에서 차단을 구현할 때는 다음 지침을 준수하세요:

- 경험 규칙은 Roblox의 [커뮤니티 표준](https://en.help.roblox.com/hc/en-us/articles/203313410-Roblox-Community-Standards) 및 [이용 약관](https://en.help.roblox.com/hc/en-us/articles/115004647846-Roblox-Terms-of-Use)과 모순되지 않아야 합니다.
  - 예를 들어, 특정 성별을 이유로 누군가를 제외하는 경험 규칙을 만들 수 없습니다. 이는 [Roblox의 차별, 모욕 및 증오 발언 정책](https://en.help.roblox.com/hc/en-us/articles/203313410-Roblox-Community-Standards#discrimination-slurs-and-hate-speech)을 위반합니다.
- 제작자는 모든 사용자가 접근할 수 있는 곳에 경험 규칙을 명확히 명시해야 합니다.
- 제작자는 특정 사용자를 임의로 목표로 삼지 않고 경험 규칙을 공정하게 적용해야 합니다.
- 사용자는 차단이 잘못되었다고 생각할 경우 제작자에게 직접 항소할 수 있습니다.
  - Roblox는 제작자의 경험 규칙이나 규칙 시행이 [커뮤니티 표준](https://en.help.roblox.com/hc/en-us/articles/203313410-Roblox-Community-Standards)을 위반한다고 사용자가 생각하는 경우를 제외하고는 이러한 항소를 중재하지 않습니다.
- Roblox는 제작자의 경험 규칙이나 규칙 시행이 [커뮤니티 표준](https://en.help.roblox.com/hc/en-us/articles/203313410-Roblox-Community-Standards)을 위반할 이유가 있다고 판단되는 경우 경험을 중재할 수 있습니다.

### 메시지 지침

사용자가 차단되면 차단 기간 및 이유와 같은 정보를 표시하는 오류 모달을 받습니다. 텍스트 필터링된 메시지에는 Roblox의 [커뮤니티 표준](https://en.help.roblox.com/hc/en-us/articles/203313410-Roblox-Community-Standards)을 준수하는 한 항소 또는 연락처 정보와 같은 추가 정보를 포함할 수 있습니다.

예를 들어, 차단 메시지에서 브랜드 이름 및 플랫폼을 참조할 수 있습니다:

- "내 그룹/경험 페이지의 Discord를 방문하세요"
- "Twitter 또는 X에서 나에게 메시지를 보내세요"

이 메시지 필드에서는 개인 정보나 직접 링크를 언급할 수 없습니다. 여기에는 특정 사용자 이름이나 핸들을 게시하거나 Discord 서버나 X 계정에 대한 직접 링크를 제공하는 것이 포함됩니다.

## 컨테이너

`Player` 객체는 몇 가지 중요한 컨테이너를 저장합니다:

- [Backpack](#backpack)
- [StarterGear](#startergear)
- [PlayerGui](#playergui)
- [PlayerScripts](#playerscripts)

### Backpack

`Player.Backpack` 컨테이너는 사용자의 인벤토리를 저장합니다. 사용자의 `Backpack`에 있는 `Tool` 객체는 화면 하단의 인벤토리에 표시됩니다. 사용자가 인벤토리에서 `Tool`을 선택하면 이를 장착하여 `Player.Backpack`에서 `Player.Character`로 이동합니다.

사용자의 `Player.Character`가 생성되면 `StarterPack` 서비스와 `Player.StarterGear`의 내용이 `Player.Backpack`으로 복제됩니다. 캐릭터가 사망하면 클라이언트는 `Backpack`을 제거하고 새로운 것을 대체합니다.

`Backpack`은 클라이언트와 서버가 모두 접근할 수 있는 `Script` 및 `LocalScript`를 저장하고 실행합니다.

Roblox는 플레이어가 화면 하단의 `Backpack` 및 인벤토리에 접근할 수 있는 인터페이스를 제공합니다. 기본 Roblox 배낭 GUI를 비활성화하고 자신의 GUI로 교체하려면 LocalScript에서 `StarterGui:SetCoreGuiEnabled()`를 호출하세요. 자세한 내용은 `StarterGui`를 참조하세요.

### StarterGear

`StarterGear` 컨테이너는 캐릭터가 생성될 때 사용자의 `Player.Backpack`으로 내용을 복제합니다. 또한, 장소에서 장비를 허용하고 사용자가 장비를 소유하고 있는 경우, 장비의 `Tool` 객체는 생성될 때 `Player.StarterGear`로 복제됩니다.

`StarterPack`과 달리 `Player.StarterGear`는 서비스가 아니라 각 `Player` 객체의 자식이므로 그 내용은 사용자별로 다릅니다. 각 사용자는 `Player.StarterGear` 내에서 서로 다른 `Tool` 객체를 가질 수 있습니다. `Player.StarterGear`를 사용하려면 경험의 설정 페이지에서 **Permissions** 아래의 장비를 활성화하세요. 권한 페이지에서 장비 유형별로 활성화할 수 있습니다. 장비를 비활성화하려면 해당 유형을 선택 해제하세요.

게임에 장비를 추가한 후에는 사용자가 이를 쉽게 악용할 수 없는지 확인하기 위해 게임을 테스트하세요. 장비에는 `Script` 객체가 포함되어 있으며 플레이어가 예상하지 못한 동작을 수행할 수 있습니다. 예를 들어, 네비게이션 장비는 플레이어가 접근하기 원하지 않는 지도 일부에 접근할 수 있게 할 수 있습니다. 무기는 장비를 가진 플레이어가 다른 플레이어를 공격할 수 있게 하여 보복이나 반격 없이 피해를 줄 수 있습니다.

### PlayerGui

`PlayerGui` 컨테이너는 플레이어의 GUI를 생성하는 객체를 저장합니다. `ScreenGui`가 `PlayerGui`의 자식이면 `ScreenGui` 내의 모든 `GuiObject`가 플레이어의 화면에 표시됩니다. 모든 `LocalScript`는 `PlayerGui`로 복제될 때 실행됩니다. 플레이어의 `Player.Character`가 처음 생성될 때 `StarterGui`의 모든 내용이 자동으로 플레이어의 `PlayerGui`로 복사됩니다.

`Players.CharacterAutoLoads`가 false로 설정된 경우 캐릭터가 생성되지 않으며, `StarterGui`의 내용은 `Player:LoadCharacter()`가 호출될 때까지 복사되지 않습니다. `StarterGui.ResetPlayerGuiOnSpawn`이 true로 설정된 경우, 플레이어의 캐릭터가 리스폰될 때마다 해당 플레이어의 `PlayerGui`의 모든 내용이 삭제되고 `StarterGui`의 내용으로 대체됩니다.

### PlayerScripts

사용자가 경험에 참여할 때 `StarterPlayer.StarterPlayerScripts` 컨테이너의 내용이 `PlayerScripts`로 복제됩니다. 모든 LocalScripts 및 ModuleScripts는 복제될 때 실행됩니다.

`Backpack` 및 `PlayerGui` 컨테이너와 달리 `PlayerScripts` 컨테이너는 서버에 접근할 수 없으며, 사용자의 `PlayerScripts` 컨테이너는 캐릭터가 사망하고 리스폰될 때 재설정되지 않습니다. 서버 측 `Script` 객체도 `PlayerScripts`에 부모로 설정될 때 실행되지 않습니다. `PlayerScripts` 컨테이너는 일반 채팅 시스템 또는 플레이어 입력 컨트롤과 같이 사용자의 캐릭터 생명주기와 관련되지 않은 스크립트에 유용합니다.

---
## 출처
 - [Users and Players](https://create.roblox.com/docs/ko-kr/players)

---
## [다음](./08_Input_and_Camera.md)