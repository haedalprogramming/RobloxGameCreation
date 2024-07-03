# Services

## 목차
- [Services](#services)
  - [목차](#목차)
  - [컨테이너 서비스](#컨테이너-서비스)
  - [스크립팅 서비스](#스크립팅-서비스)
  - [클라우드 서비스](#클라우드-서비스)
  - [출처](#출처)
  - [다음](#다음)

---

코드 재사용에서 `game:GetService()` 메서드의 빈번한 사용을 눈치챘을 것입니다. Roblox 서비스는 엔진의 내장 기능에 액세스할 수 있도록 하여, 경험 내 아이템 판매, 채팅 활성화, 사운드 재생, 객체 애니메이션, 인스턴스 관리 등을 가능하게 합니다.

사실, 서비스는 **Roblox 개발의 가장 기본적이고 일반적인 패턴**의 첫 번째 단계입니다:

1. 서비스 가져오기.
2. 모듈 스크립트 요구.
3. 로컬 함수 추가.
4. 해당 함수를 트리거하는 이벤트 추가.

예를 들어, 경험에서 플레이어가 나갈 때 플레이어의 위치를 저장하려고 할 때:

```lua
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local SaveManager = require(ReplicatedStorage:WaitForChild("SaveManager"))

-- 모듈 스크립트에서 재사용 가능한 함수를 호출하는 로컬 함수.
local function saveProgress(character)
    -- 플레이어 캐릭터의 위치를 가져옵니다.
    local position = character:FindFirstChild("HumanoidRootPart").Position
    -- DataStoreService에 기록하는 모듈 스크립트의 saveData 함수를 사용합니다.
    SaveManager.saveData(character, position)
end

-- 캐릭터가 경험에서 제거될 때 (이 경우 플레이어가 나갈 때) saveProgress()를 호출하는 또 다른 로컬 함수.
local function onPlayerAdded(player)
    player.CharacterRemoving:Connect(saveProgress)
end

-- 플레이어가 처음으로 경험에 연결될 때 onPlayerAdded를 호출합니다.
Players.PlayerAdded:Connect(onPlayerAdded)
```

몇 가지 중요한 세부 사항은 다음과 같습니다:

- 스크립트당 서비스는 한 번만 가져와야 하므로, 관례적으로 변수 이름은 서비스와 동일하게 합니다. 이 관례는 모듈 스크립트에도 적용됩니다.
- 서비스를 가져올 때는 데이터 모델의 루트인 글로벌 변수 `game`을 사용합니다.
- Roblox는 로딩 순서에 대한 보장을 하지 않으며, 인스턴스 스트리밍은 특정 시점에 로드된 것과 로드되지 않은 것을 더욱 복잡하게 만드므로, `Instance:WaitForChild()`의 사용은 중요한 안전 조치입니다.

표준 라이브러리, 글로벌 함수 및 변수, 또는 서드 파티 라이브러리와 비교하는 대신, Roblox 개발의 큰 부분은 많은 서비스 중 어떤 서비스가 원하는 기능을 경험에 추가하는 데 도움이 될 수 있는지를 파악하는 것입니다. 위의 예에서 표준 I/O 라이브러리를 사용하여 디스크에 기록하는 대신, 클라우드 서비스를 사용하여 데이터를 저장합니다.

## 컨테이너 서비스

컨테이너 서비스는 다른 객체를 포함하고 영향을 미칠 수 있습니다. 이러한 컨테이너 서비스는 데이터 모델의 루트에 위치하며 Studio의 Explorer 창에서 볼 수 있습니다. 이 컨테이너 서비스는 데이터 모델의 구조적 계층을 형성하여, Roblox 엔진이 장소를 적절하게 해석하고 렌더링할 수 있게 합니다. 다음 표는 몇 가지 일반적인 컨테이너 서비스를 포함합니다.

서비스 | 설명
:--- | :---
`Workspace` | 파트 및 지형과 같은 3D 세계에서 렌더링되는 모든 객체를 포함합니다.
`Lighting` | `Atmosphere` 및 `Sky`와 같은 보편적인 조명 효과를 설정하는 객체를 포함합니다.
`ReplicatedStorage` 및 `ReplicatedFirst` | 서버와 클라이언트 간에 복제되는 콘텐츠와 로직을 포함합니다.

데이터 모델을 더 자세히 조사하려면 다음 메서드를 사용할 수 있습니다:

- `game:FindService()`는 지정된 서비스의 인스턴스를 검색합니다.
- `game:GetChildren()`는 데이터 모델의 모든 루트 자식을 배열로 반환합니다. 이들은 최상위 컨테이너 서비스입니다.
- `game:GetDescendants()`는 데이터 모델의 모든 후손, 즉 모든 컨테이너 서비스와 그 자식을 배열로 반환합니다.

컨테이너 서비스에 대한 자세한 내용은 `데이터 모델` 문서를 참조하십시오.

## 스크립팅 서비스

스크립팅 서비스는 Roblox 엔진의 표준 기능을 제공하며, 스크립트 내에서 호출할 수 있습니다. 다음 표는 몇 가지 일반적인 스크립팅 서비스를 포함합니다.

서비스 | 설명
:--- | :---
`TweenService` | 시작 값에서 끝 값까지 다른 인스턴스의 수치 속성을 보간하는 데 사용되며, 이징 방향 및 스타일, 반복 및 지연 옵션을 포함합니다.
`MarketplaceService` | 경험 내 트랜잭션을 담당하는 서비스로, 플레이어에게 개발자 제품, 구독, 게임 패스 구매를 요청하거나 Roblox Premium으로 업그레이드하는 등의 기능을 제공합니다.
`ContextActionService` | 키 누름, 화면 터치, 컨트롤러 버튼 누름과 같은 사용자 입력을 바인딩하여, 사용자가 자동차에 탑승하거나 내릴 때 제어를 수정하는 등의 컨텍스트 작업에 할당할 수 있습니다.
`RunService` | 프레임별 시간 관리 및 경험이 실행되는 컨텍스트(서버, 클라이언트, Studio 모드)를 확인하는 메서드 및 이벤트를 포함합니다. 런타임 프레임마다 프로세스나 업데이트를 실행하는 데 유용합니다.
`SoundService` | 도플러 스케일 및 볼륨 오디오와 같은 경험에서 오디오가 재생되는 다양한 전역 측면을 제어합니다. 여러 오디오 신호의 볼륨 및 동적 효과 속성을 한 번에 제어하는 사운드 그룹도 포함할 수 있습니다.
`CollectionService` | 태그가 붙은 인스턴스 그룹을 관리하여 서버에서 클라이언트로 복제되며, 관련된 인스턴스 그룹을 더 쉽게 할당하고 작업할 수 있게 합니다.

## 클라우드 서비스

Roblox에는 Roblox 클라우드에서 발생하는 작업 및 프로세스를 처리하기 위한 특수 클라우드 서비스도 있습니다. 다음 표는 몇 가지 일반적인 클라우드 서비스를 포함합니다.

서비스 | 설명
:--- | :---
`DataStoreService` | 세션 간 지속 데이터를 저장합니다.
`MemoryStoreService` | 빠르게 변하는 빈번하고 일시적인 데이터를 저장합니다.
`MessagingService` | 라이브 세션 중 여러 서버 간 통신을 제공합니다.

클라우드 서비스에는 해당 웹 API도 있습니다. 외부 스크립트나 도구에서 액세스할 수 있습니다. 자세한 내용은 `Open Cloud`를 참조하십시오.

---
## 출처
 - [Services](https://create.roblox.com/docs/scripting/services)

---
## [다음](./04_04_events.md)