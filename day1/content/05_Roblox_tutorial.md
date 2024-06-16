# Roblox tutorial

## 목차
- [Roblox tutorial](#roblox-tutorial)
  - [목차](#목차)
  - [Core](#core)
    - [Core Curriculum](#core-curriculum)
    - [Chapter 1 - Build a Greybox](#chapter-1---build-a-greybox)
      - [Create a Project](#create-a-project)
      - [Create an Environment with Terrain](#create-an-environment-with-terrain)
        - [섬 만들기](#섬-만들기)
        - [섬 모양 만들기](#섬-모양-만들기)
        - [물 만들기](#물-만들기)
        - [재료 적용](#재료-적용)
        - [플레이테스트](#플레이테스트)
      - [Greybox a Playable Area](#greybox-a-playable-area)
        - [플레이 가능한 영역 계획하기](#플레이-가능한-영역-계획하기)
        - [플랫폼 추가하기](#플랫폼-추가하기)
        - [조직 구조 만들기](#조직-구조-만들기)
        - [파트 삽입](#파트-삽입)
        - [파트 정렬](#파트-정렬)
        - [속이 빈 터널 만들기](#속이-빈-터널-만들기)
        - [플레이테스트](#플레이테스트-1)
    - [Chapter 2 - Script the Gameplay](#chapter-2---script-the-gameplay)
      - [Create a Coin Collection Mechanic](#create-a-coin-collection-mechanic)
        - [코인 만들기](#코인-만들기)
        - [스크립트 만들기](#스크립트-만들기)
        - [Code Explanation](#code-explanation)
          - [서비스 및 변수 초기화](#서비스-및-변수-초기화)
          - [이벤트 핸들러 정의](#이벤트-핸들러-정의)
          - [이벤트 핸들러 연결](#이벤트-핸들러-연결)
        - [메커니즘 플레이테스트](#메커니즘-플레이테스트)
      - [Record and Display Player Data](#record-and-display-player-data)
        - [코인 수집을 기록하는 모듈 스크립트 만들기](#코인-수집을-기록하는-모듈-스크립트-만들기)
        - [리더보드 구현](#리더보드-구현)
        - [모듈 스크립트 통합](#모듈-스크립트-통합)
        - [플레이테스트](#플레이테스트-2)
      - [Create Player Hazards](#create-player-hazards)
        - [기본적인 물 위험 요소 생성하기](#기본적인-물-위험-요소-생성하기)
        - [플레이어 생명 주기와 연결하기](#플레이어-생명-주기와-연결하기)
        - [플레이 테스트](#플레이-테스트)
      - [Script an Upgrade Button](#script-an-upgrade-button)
        - [업그레이드 버튼 생성하기](#업그레이드-버튼-생성하기)
        - [점프 파워 데이터 정의하기](#점프-파워-데이터-정의하기)
        - [점프 파워 데이터 업데이트하기](#점프-파워-데이터-업데이트하기)
        - [플레이어 GUI에 버튼 추가하기](#플레이어-gui에-버튼-추가하기)
      - [플레이 테스트](#플레이-테스트-1)
    - [Chapter 3 - Polish the Experience](#chapter-3---polish-the-experience)
      - [Create Basic Visual Effects](#create-basic-visual-effects)
        - [플레어 만들기](#플레어-만들기)
        - [플레어 구성하기](#플레어-구성하기)
          - [입자 이미지](#입자-이미지)
          - [기본 속성](#기본-속성)
          - [수명 및 NumberSequence 값](#수명-및-numbersequence-값)
        - [PointLight 추가하기](#pointlight-추가하기)
        - [먼지 입자 만들기](#먼지-입자-만들기)
          - [먼지 입자 구성하기](#먼지-입자-구성하기)
      - [Customize Global Lighting](#customize-global-lighting)
        - [조명 속성 설정](#조명-속성-설정)
          - [조명의 색상 조정](#조명의-색상-조정)
          - [그림자 경화](#그림자-경화)
          - [미래 조명 시스템 활성화](#미래-조명-시스템-활성화)
          - [태양 위치 변경](#태양-위치-변경)
        - [대기 속성](#대기-속성)
          - [공기 입자 밀도 증가](#공기-입자-밀도-증가)
          - [먼 물체 블렌딩](#먼-물체-블렌딩)
      - [Apply Polished Assets](#apply-polished-assets)
        - [자산 라이브러리 가져오기](#자산-라이브러리-가져오기)
        - [조직 구조 계속하기](#조직-구조-계속하기)
        - [자산 라이브러리 적용하기](#자산-라이브러리-적용하기)
          - [Platforms](#platforms)
          - [Sea Stacks](#sea-stacks)
          - [Coins](#coins)
          - [Mountains](#mountains)
        - [Playtest](#playtest)
  - [Environmental Art Curriculum](#environmental-art-curriculum)
    - [Chapter 1 - Greybox Your Environment](#chapter-1---greybox-your-environment)
      - [세 개의 레인 맵 레이아웃](#세-개의-레인-맵-레이아웃)
        - [스폰 존](#스폰-존)
        - [주요 레인](#주요-레인)
        - [교차 레인](#교차-레인)
      - [플레이 가능한 영역 만들기](#플레이-가능한-영역-만들기)
        - [바닥 지오메트리](#바닥-지오메트리)
        - [주변 벽 지오메트리](#주변-벽-지오메트리)
        - [스폰 존 지오메트리](#스폰-존-지오메트리)
        - [전투 포켓 지오메트리](#전투-포켓-지오메트리)
        - [외부 지오메트리](#외부-지오메트리)
      - [플레이스홀더 재료 적용](#플레이스홀더-재료-적용)
      - [레이아웃 테스트](#레이아웃-테스트)
    - [Chapter 2 - Develop Polished Assets](#chapter-2---develop-polished-assets)
    - [Chapter 3 - Assemble an Asset Library](#chapter-3---assemble-an-asset-library)
    - [Chapter 4 - Construct Your World](#chapter-4---construct-your-world)
    - [Chapter 5 - Optimize Your Experience](#chapter-5---optimize-your-experience)
  - [출처](#출처)
  - [다음](#다음)

---
## Core

여기에 Studio에서 창작하는 것에 대한 포괄적인 소개를 시작하세요! 처음부터 간단하지만 완성도 높은 경험을 만드는 데 필요한 모든 것을 다룹니다.

### Core Curriculum

핵심 커리큘럼은 기술 및 창의적 분야 전반에 걸쳐 Studio의 많은 필수 기능을 배우는 데 도움을 줍니다.

플레이어가 점프 파워를 교환하기 위해 코인을 수집하는 간단한 3D 플랫폼 게임 경험을 재창조하는 방법을 배울 수 있습니다. 플레이어는 점점 더 높은 플랫폼을 점프하여 최종적으로 가장 높은 플랫폼에 있는 신호탄에 도달합니다.

이 과정은 일반적인 코딩 개념에 익숙하지만 Roblox에 처음인 독자를 대상으로 합니다. 코딩을 배우는 데 도움이 필요하다면 Studio 작업의 기본 사항과 코딩 기본 개념을 시도해보세요.

코스 내용

 - 핵심 커리큘럼은 세 개의 챕터로 나뉘며, 각 챕터는 해당 장소 파일과 함께 제공됩니다. 각 챕터의 단계를 따라가거나 챕터의 최종 결과를 보고 싶다면 장소 파일을 검사할 수 있습니다.

 -  챕터 1 - 그레이박스 구축
    - 프로젝트 만들기 - Roblox 플랫폼에서 경험을 나타내는 .rbxl 파일을 만드는 방법을 배우세요.
    - 지형으로 환경 만들기 - Studio의 지형 도구를 사용하여 플레이어가 스폰되는 섬을 만드는 방법을 배우세요.
    - 플레이 가능 영역 그레이박스 - 솔리드 모델링 도구를 사용하여 플랫폼의 기본 형태를 계획하는 방법을 배우세요.

 - 챕터 2 - 게임플레이 스크립트 작성
   - 코인 수집 메커니즘 만들기 - 플레이어의 코인 수집을 추적하고 저장하는 방법을 배우세요.
   - 플레이어 데이터 기록 및 표시 - 개별 플레이어 데이터를 시각적으로 리더보드를 통해 저장, 검색 및 표시하는 방법을 배우세요.
   - 플레이어 위험 요소 만들기 - 플레이어 행동을 수정하고 플레이어 생명 주기를 만들어 물에서 위험 요소를 만드는 방법을 배우세요.
   - 업그레이드 버튼 스크립트 작성 - Roblox 서버와 통신하고 GUI 상호작용을 처리하여 플레이어 점프 파워를 업그레이드하는 방법을 배우세요.

 - 챕터 3 - 경험 다듬기
   - 기본 시각 효과 만들기 - 파티클 방출기를 사용하여 두 가지 다른 유형의 시각 효과를 만드는 방법을 배우세요.
   - 글로벌 조명 사용자 지정 - 글로벌 조명 설정을 사용하여 경험의 외관과 느낌을 개선하는 방법을 배우세요.
   - 정교한 자산 적용 - 간단한 부분을 복잡하고 가져온 모델로 교체하여 장면을 마무리하는 방법을 배우세요.

### Chapter 1 - Build a Greybox

#### Create a Project

Island Jump 3D 플랫폼 경험을 재현하기 위해서는 Roblox Studio 내에서 프로젝트를 만들어야 합니다. 프로젝트는 장소, 자산, 설정 및 기타 리소스의 모음으로, 함께 경험을 나타냅니다. 프로젝트는 처음부터 시작할 수도 있고, Studio의 템플릿 중 하나를 사용하여 환경과 게임 메커니즘의 기초를 제공할 수도 있습니다. 예를 들면 다음과 같습니다:

Baseplate 템플릿 — Baseplate와 SpawnLocation 객체를 포함합니다.
Modern City 템플릿 — 고품질의 도시 샘플과 모듈식 자산 키트를 포함합니다.
Mansion of Wonder 템플릿 — 1인칭 슈터 경험을 위한 자산과 스크립트를 포함합니다.

Baseplate 템플릿으로 프로젝트를 만들려면:

1. Roblox Studio를 엽니다.
2. 세로 탐색 바에서 새 탭을 선택합니다. 모든 템플릿이 표시됩니다.
3. Baseplate 템플릿을 선택합니다. Studio가 새로운 경험을 엽니다.<br>![](../img/05_Roblox_tutorial/Templates-Baseplate.jpg.webp)
4. Explorer 창에서 Baseplate 객체를 마우스 오른쪽 버튼으로 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
5. 삭제를 선택합니다. 뷰포트에는 중앙에 스폰 위치가 있는 빈 세계가 표시됩니다.<br>![](../img/05_Roblox_tutorial/Baseplate-Deleted.jpg.webp)

다음 튜토리얼 섹션에서는 스폰 위치 주변에 섬 환경을 만들기 위해 지형 편집기를 사용하는 방법을 배우게 됩니다.

#### Create an Environment with Terrain

지형을 사용하여 환경을 만드는 것은 3D 공간 내에서 실제 자연 재료처럼 보이고 작동하는 유기적 재료를 생성하고 사용자 정의할 수 있게 해줍니다. Terrain Editor 내의 도구를 사용하여 이 튜토리얼 섹션에서는 플레이어가 스폰하고 경험의 첫 번째 몇 개의 플랫폼으로 이동할 수 있는 작은 섬을 위해 지형을 생성하고 조각하는 방법을 가르칩니다.

시작하기 전에 지형을 조각하는 것은 예술 형식이며, 브러쉬 스트로크와 미세한 재료 편집을 정확하게 재현하는 것은 어렵다는 점을 유념하십시오. 지형이 여러분의 경험 요구에 부합하는 한, 여러분의 환경이 샘플 Island Jump 경험과 다르게 보이고 느껴지는 것은 정상이며 예상되는 일입니다.

##### 섬 만들기

환경을 만드는 첫 번째 단계는 플레이어가 경험을 시작할 때와 플랫폼에서 떨어져 건강이 0이 되었을 때 스폰될 작은 섬을 만드는 것입니다. Terrain Editor의 Draw 도구를 사용하여 뷰포트 내 어디에서나 클릭하고 드래그하여 섬을 시작할 큰 구체를 생성할 수 있으며, 나중에 넓은 표면적을 위해 모양을 만들고 평평하게 할 수 있습니다.

섬을 만들려면:

1. 메뉴 바에서 홈 탭으로 이동한 다음 Terrain Editor 버튼을 클릭합니다. Terrain Editor 창이 표시됩니다.<br>![](../img/05_Roblox_tutorial/Home-Tab-Terrain-Editor.png.webp)
2. Terrain Editor 창에서 Edit 탭을 클릭한 다음 Draw 버튼을 클릭합니다.<br>![](../img/05_Roblox_tutorial/Edit-Tab-Draw.png.webp)
3. 브러쉬 설정 및 재료 설정 섹션에서 다음을 제외한 모든 기본 설정을 유지합니다:<br>![](../img/05_Roblox_tutorial/Terrain-Editor-Draw-Settings.png.webp)
    - 기본 크기를 32로 설정합니다.
    - 재료를 모래로 설정합니다.
4. 뷰포트에서 스폰 위치 근처를 클릭합니다. 모래 재료의 구체가 표시됩니다.

<video src="../img/05_Roblox_tutorial/Terrain-Adding-First-Sphere.mp4" width="320" height="240" controls></video>

구체가 보이지 않으면 카메라를 줌 아웃하여 스폰 위치가 작아질 때까지 시도하십시오.

##### 섬 모양 만들기

현재 모양의 섬을 유지하면 플레이어가 섬에서 떨어지지 않고 탐색하기 어려울 것입니다. Terrain Editor의 Flatten 도구를 사용하여 고정 평면에서 지형을 균일하게 평평하게 만들고 플레이어가 경험을 시작할 때 상대적으로 평평한 표면을 제공할 수 있습니다. 이 모양이 처음에는 자연스럽지 않아 보이지만, Terrain Editor의 Sculpt 도구를 사용하여 섬의 가장자리를 다듬어 보다 유기적이고 현실적으로 보이게 할 수 있습니다.

섬 모양을 만들려면:

1. Terrain Editor 창에서 Flatten 버튼을 클릭합니다.<br>![](../img/05_Roblox_tutorial/Edit-Tab-Flatten.png.webp)
2. 브러쉬 설정 섹션에서 다음을 제외한 모든 기본 설정을 유지합니다:<br>![](../img/05_Roblox_tutorial/Terrain-Editor-Flatten-Settings.png.webp)
    - 기본 크기를 18로 설정합니다.
    - 고정 평면을 활성화합니다. 새로운 설정이 표시됩니다.
    - 평면 위치를 0으로 설정합니다.
3. 뷰포트에서 마우스를 클릭하고 드래그하여 구체의 상단이 완전히 평평해질 때까지 이동합니다.
<video src="../img/05_Roblox_tutorial/Terrain-Flattening-Sphere.mp4" width="320" height="240" controls></video>

4. 다시 Terrain Editor 창으로 이동하여 Sculpt 버튼을 클릭합니다.<br>![](../img/05_Roblox_tutorial/Edit-Tab-Sculpt.png.webp)
5. 브러쉬 설정 및 재료 설정 섹션에서 재료를 모래로 설정하고 다른 모든 기본 설정을 유지합니다.<br>![](../img/05_Roblox_tutorial/Terrain-Editor-Sculpt-Settings.png.webp)
6. 뷰포트에서 마우스를 클릭하고 드래그하여 섬의 가장자리와 물 아래 라인을 따라 이동하여 섬이 보다 자연스럽게 보이도록 합니다.

<video src="../img/05_Roblox_tutorial/Terrain-Sculpting-Edges.mp4" width="320" height="240" controls></video>

Draw 도구는 브러쉬 위치에 따라 재료를 추가하거나 빼지만, Sculpt 도구는 기존 지형을 성장시키거나 침식시키기만 합니다.

##### 물 만들기

큰 수역을 생성하는 방법은 여러 가지가 있지만, 다음 지침에서는 Terrain Editor의 Fill 도구를 사용합니다. 이 방법을 사용하면 특정 영역의 모든 재료를 다른 재료(공기 포함)로 교체할 수 있습니다.

섬 주변에 물을 만들려면:

1. Terrain Editor 창에서 Fill 버튼을 클릭합니다.<br>![](../img/05_Roblox_tutorial/Edit-Tab-Fill.png.webp)
2. 선택 설정 섹션에서,
    1. 위치를 0, -15, 0으로 설정하여 섬 상단 아래에 물이 채워지도록 합니다.
    2. 크기를 1800, 5, 1800으로 설정하여 경험의 지평선까지 물이 채워지도록 합니다.
3. 재료 설정 섹션에서 도구를 다음 설정으로 구성합니다:<br>![](../img/05_Roblox_tutorial/Terrain-Editor-Fill-Settings.png.webp)
    - 재료 모드를 대체로 설정합니다.
    - 원본 재료를 공기로 설정합니다.
    - 대상 재료를 물로 설정합니다.
4. 적용 버튼을 클릭합니다. 섬 주변에 물이 생성됩니다.
<video src="../img/05_Roblox_tutorial/Terrain-Filling-Water.mp4" width="320" height="240" controls></video>

##### 재료 적용

이제 섬의 기초가 마련되었으므로 다양한 재료로 외관을 사용자 정의할 수 있습니다. Terrain Editor의 Paint 도구를 사용하여 클릭하고 드래그하여 섬 표면의 중간 부분에 풀과 풀잎을 적용할 수 있습니다.

섬에 재료를 적용하려면:
1. Terrain Editor에서 Paint 버튼을 클릭합니다.<br>![](../img/05_Roblox_tutorial/Edit-Tab-Paint.png.webp)
2. 브러쉬 설정 및 재료 설정 섹션에서 다음을 제외한 모든 기본 설정을 유지합니다:
    <br>![](../img/05_Roblox_tutorial/Terrain-Editor-Paint-Settings.png.webp)
    - 재료 모드를 페인트로 설정합니다.
    - 재료를 잎이 많은 풀로 설정합니다.
3. 뷰포트에서 섬의 중간을 클릭하고 드래그하여 잎이 많은 풀 재료를 적용합니다.
<video src="../img/05_Roblox_tutorial/Terrain-Painting-Grass.mp4" width="320" height="240" controls></video>

4. 다시 Terrain Editor 창으로 이동하여 브러쉬 설정 및 재료 설정 섹션에서
    - 기본 크기를 3으로 설정합니다.
    - 재료를 풀로 설정합니다.
5. 뷰포트에서 섬 가장자리를 따라 드래그하여 풀잎을 적용하고, 섬의 중간에 스폰 위치와 초기 플랫폼을 위한 공간을 남깁니다.
6. Explorer 창에서 SpawnLocation 객체를 선택합니다.
7. 홈 탭에서 이동 도구를 선택합니다.
8. 뷰포트에서 스폰 위치를 섬 가장자리 쪽으로 이동하여 첫 번째 플랫폼을 위한 공간을 만듭니다. 샘플 Island Jump - Building .rbxl 파일은 위치를 -127, -3, 9로 사용합니다.

<video src="../img/05_Roblox_tutorial/create-an-environment-with-terrain-spawn.mp4" width="320" height="240" controls></video>

재료 오버라이드를 사용하여 사용자 정의 텍스처 자산을 제공하여 기본 지형 텍스처를 대체하는 완전히 사용자 정의된 재료 외관을 만들 수 있습니다.

##### 플레이테스트

섬의 외관에 만족하면 플레이테스트를 통해 섬의 규모와 3D 세계에서의 느낌을 확인할 수 있습니다.

경험을 플레이테스트하려면:
1. 메뉴 바에서 재생 버튼을 클릭합니다. Studio가 플레이테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. 섬을 걸어 다니며 플레이 중에 어떻게 보이는지 확인합니다. 완료되면 메뉴 바로 돌아가서 정지 버튼을 클릭합니다. Studio가 플레이테스트 모드를 종료합니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Stop.png.webp)

스폰 시 캐릭터가 예상과 다른 방향을 향하고 있다면, 예를 들어 섬의 중앙이 아닌 바다를 향하고 있다면 SpawnLocation 객체를 회전시키고 다시 플레이테스트하여 캐릭터가 적절한 방향으로 스폰될 때까지 과정을 반복합니다.

<video src="../img/05_Roblox_tutorial/create-an-environment-with-terrain-walking.mp4" width="320" height="240" controls></video>

다음 튜토리얼 섹션에서는 플레이어가 가장 높은 플랫폼에 도달할 수 있는 플레이 가능한 영역을 만드는 방법을 배웁니다.

#### Greybox a Playable Area

환경의 그레이박싱(Greyboxing), 또는 환경을 대략적으로 배치하는 과정은 스크립팅이나 복잡한 자산을 만들기 전에 사용자가 게임플레이를 어떻게 경험할지 알아보기 위해 3D 공간에 간단한 모양을 추가하는 과정입니다. 이 과정은 레이아웃의 문제를 찾는 데 많은 시간을 절약할 수 있으며, Studio에 고품질 메시를 가져오는 것보다 기본 부품을 조정하는 것이 훨씬 쉽습니다.

기본 부품과 고체 모델링 작업을 사용하여 이 튜토리얼 섹션에서는 경험의 플레이 가능한 영역을 구성하는 해상 암초 플랫폼을 그레이박싱하는 방법을 가르칩니다. 환경을 완료한 후에는 Luau 스크립트를 사용하여 경험의 게임플레이를 만드는 방법을 배우게 됩니다.

##### 플레이 가능한 영역 계획하기

경험의 최종 버전에서는 플레이어가 섬과 해상 암초 플랫폼에서 동전을 모아 점프력을 업그레이드하고 더 높은 플랫폼에 도달해야 합니다. 다음 튜토리얼 섹션에서는 이 동작을 추가하도록 스크립트를 구성하겠지만, 환경을 그레이박싱할 때 플랫폼 간의 높이 차이를 계획하는 것이 중요합니다. 예를 들어, 각 높이 수준마다 플랫폼 간의 높이 차이가 점차 증가하여 플레이어가 동전을 모아 레벨을 진행하도록 유도해야 합니다.

가이드로서, 샘플 Island Jump - Building .rbxl 파일에는 7개의 다른 높이 수준이 포함되어 있으며, 첫 번째 수준은 섬에 잠기도록 하여 몇 개의 스터드 높이만 노출됩니다. 이는 플레이어가 경험 초기에 몇 개의 동전만 모으면 다음 플랫폼으로 진행할 수 있도록 합니다. 각 수준 간의 후속 높이 차이는 8, 20, 35, 55, 81 및 110 스터드로 증가하여 플레이어가 경험을 진행하면서 성취감을 느낄 수 있습니다.

스터드는 Studio의 주요 길이 단위이며, 28cm에 해당합니다.

![](../img/05_Roblox_tutorial/Platform-Levels.jpg.webp)
샘플 Island Jump 경험의 그레이박스 지오메트리의 먼 뷰. 각 해상 암초 간의 높이 차이가 강조 표시되어 있습니다.

샘플의 단순한 디자인을 넘어 세계를 확장하려면, 점프 업그레이드를 필요로 하는 각 새로운 높이 수준이 이전 수준보다 적어도 30 스터드 이상 높아지도록 해야 합니다.

##### 플랫폼 추가하기

이제 플랫폼 간의 높이 차이에 대한 계획이 마련되었으므로, 해상 암초 플랫폼을 나타내는 자리 표시자 `Part` 객체를 추가할 차례입니다. Part는 모양, 크기, 색상 등의 물리적 외관을 사용자 정의할 수 있는 Roblox의 기본 빌딩 블록입니다.

해상 암초 플랫폼을 나타내기 위해 거의 모든 파트 모양을 사용할 수 있지만, 플랫폼 간 점프를 플레이테스트할 때 착지할 수 있는 평평한 표면을 제공하고 튜토리얼의 최종 섹션에서 사용할 해상 암초 메시와 유사하기 때문에 실린더 파트로 환경을 그레이박싱하는 것이 좋습니다.

샘플 Island Jump 경험의 그레이박스와 최종 지오메트리 비교

![](../img/05_Roblox_tutorial/Add-Platforms-Greybox.jpg.webp)
샘플 Island Jump 경험의 그레이박스 지오메트리.

![](../img/05_Roblox_tutorial/Add-Platforms-Final.jpg.webp)
샘플 Island Jump 경험의 최종 지오메트리.

##### 조직 구조 만들기
3D 공간에 자리 표시자 파트를 삽입하기 전에, Workspace의 자산에 대한 조직 구조를 만드는 것이 중요합니다. 이 과정은 특히 관리해야 할 자산이 많은 경험을 만드는 과정에서 Workspace가 조직되고 쉽게 스캔되도록 보장합니다.

자산을 함께 그룹화할 수 있는 컨테이너 유형에는 Folder와 Model 객체 두 가지가 있습니다. 폴더는 다양한 유형의 많은 객체를 저장하는 데 유용하고, 모델은 파트의 기하학적 그룹을 저장하는 데 유용합니다. 다음 지침에서는 3D 세계의 모든 자산을 저장하는 데 두 가지 컨테이너 객체를 사용하는 방법을 가르칩니다.

조직 구조를 만들려면:
1. Explorer 창에서 Workspace 위로 마우스를 올리고 ⊕ 아이콘을 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
2. 컨텍스트 메뉴에서 Folder 객체를 삽입합니다. 3D 세계의 모든 자산을 포함할 폴더 객체가 표시됩니다.
<br>![](../img/05_Roblox_tutorial/Explorer-Add-Folder.png.webp)
<br>Explorer 창에서 Workspace의 플러스 아이콘과 폴더 객체가 강조 표시된 모습.

3. 새 폴더 이름을 World로 변경합니다.
    1. 폴더 객체를 마우스 오른쪽 버튼으로 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
    2. 컨텍스트 메뉴에서 이름 변경을 클릭하고 폴더의 이름을 World로 입력합니다.
    이름이 올바르게 철자가 맞고 대소문자가 올바른지 확인합니다. Roblox에서 작성한 스크립트는 대소문자를 구분하며, 나중에 이 폴더에 접근하기 위해 하나의 스크립트를 작성할 것입니다.
4. World 폴더 위로 마우스를 올리고 ⊕ 아이콘을 클릭합니다.
5. 컨텍스트 메뉴에서 Model을 삽입합니다.<br>![](../img/05_Roblox_tutorial/Explorer-Add-Model.png.webp)<br>Explorer 창에서 World 폴더의 플러스 아이콘과 Model 객체가 강조 표시된 모습.
6. 모델 이름을 Blockout_Parts로 변경합니다.<br>![](../img/05_Roblox_tutorial/Explorer-Model-Renamed.png.webp)<br>Explorer 창에서 World 폴더 아래에 있는 새 Blockout_Parts 모델이 강조 표시된 모습.

##### 파트 삽입

```
다음 지침에서는 두 가지 다른 교육 경로를 제공합니다. 고유한 환경에 파트를 삽입하거나 샘플 Island Jump - Building 내의 그레이박스 환경을 정확하게 재현할 수 있습니다.
```

이제 자산을 포함할 조직 구조가 마련되었으므로, 3D 공간에 해상 암초 플랫폼을 나타내는 파트를 삽입할 수 있습니다.

첫 번째 플랫폼을 위한 실린더 파트를 삽입하려면:
1. 메뉴 바에서 홈 탭을 선택합니다.
2. 삽입 섹션에서 파트 드롭다운 화살표를 클릭한 다음 실린더를 선택합니다. 실린더 파트가 뷰포트에 표시됩니다.<br>![](../img/05_Roblox_tutorial/Home-Tab-Part-Menu-Cylinder.png.webp)
3. Explorer 창에서 새 Part를 클릭하고 Blockout_Parts 모델로 드래그합니다. 파트가 모델의 자식이 됩니다.<br>![](../img/05_Roblox_tutorial/New-Part-As-Child-Of-Model.png.webp)<br>Explorer 창에서 Blockout_Parts 모델 객체 아래에 새 Part가 강조 표시된 모습.
4. 다시 홈 탭으로 이동하여 이동, 크기 조정 및 회전 도구를 사용하여 실린더를 섬의 중앙에 큰 평평한 표면이 되도록 위치, 크기 조정 및 회전합니다. 이 도구에 대한 자세한 내용은 파트 조작을 참조하십시오.<br>![](../img/05_Roblox_tutorial/Home-Tab-Move.png.webp)<br>![](../img/05_Roblox_tutorial/Home-Tab-Scale.png.webp)<br>![](../img/05_Roblox_tutorial/Home-Tab-Rotate.png.webp)<br>![](../img/05_Roblox_tutorial/First-Platform.jpg.webp)
5. 같은 과정을 사용하여 높이가 증가하는 적어도 7개의 해상 암초 플랫폼을 Blockout_Parts 모델에 추가하고 구성합니다.<br>![](../img/05_Roblox_tutorial/Final-Platforms.jpg.webp)
6. Explorer 창에서 Block_Out 모델을 선택합니다.
7. 홈 탭에서 편집 섹션으로 이동하여 앵커 아이콘을 클릭합니다. 이는 경험이 시작될 때 물리 시스템이 파트를 이동시키지 않도록 보장합니다.<br>![](../img/05_Roblox_tutorial/Home-Tab-Anchor.png.webp)

##### 파트 정렬
해상 암초 플랫폼을 삽입할 때 샘플 Island Jump - Building 경험 값을 사용한 경우 이 단계를 건너뛸 수 있습니다.

섬 외부에 더 많은 해상 암초 자리 표시자 파트를 추가할 때, 이러한 파트의 높이 차이를 서로 다른 위치 대신 다양한 크기를 사용하여 관리하는 것이 더 쉽습니다. 이를 통해 각 플랫폼의 기반을 정렬하여 모든 수직 크기 차이가 다른 높이로 반영되도록 하고, 같은 크기의 파트는 동일한 수준에 있도록 할 수 있습니다.

`Align Tool`은 특정 축에 따라 최소, 중앙 또는 최대 가장자리에 파트를 정렬합니다. 이 경험의 목적을 위해 Y 축에서 아래 가장자리를 정렬하여 모든 파트가 물에 부분적으로 잠기도록 해야 합니다.

파트를 정렬하려면:
1. Explorer 창에서 모든 플랫폼을 선택합니다.
2. 메뉴 바에서 모델 탭으로 이동한 다음 Align Tool을 클릭합니다. Align Tool 창이 표시됩니다.<br>![](../img/05_Roblox_tutorial/Model-Tab-Align-Tool.png.webp)
3. Align Tool 창에서,
    1. 모드를 Min으로 설정합니다.
    2. 정렬 대상을 World, Y로 설정합니다.
    3. Relative To를 Selection Bounds로 유지합니다.
4. Align 버튼을 클릭합니다. 모든 파트가 가장 낮은 Y Part.Position 값을 가진 파트에 따라 Y 축에서 정렬됩니다.
![](../img/05_Roblox_tutorial/Platforms-Aligned-Underwater.jpg.webp)
모든 플랫폼이 아래 가장자리를 정렬합니다.

##### 속이 빈 터널 만들기

플레이 가능한 영역을 차단하는 데 파트를 그대로 사용하는 것 외에도 고체 모델링 작업을 적용하여 파트를 독특한 방식으로 결합하여 속이 빈 터널과 같은 더 복잡한 모양을 만들 수 있습니다. 이 기술은 플레이어가 환경과 상호 작용하는 방식에 시각적 흥미와 변화를 제공합니다.

고체 모델링 도구에는 네 가지가 있습니다:

 - Union – 두 개 이상의 파트를 결합하여 하나의 고체 유니언을 만듭니다.
 - Intersect – 겹치는 파트를 하나의 고체 교차로 교차합니다.
 - Negate – 파트를 제거하여 구멍과 함몰부를 만드는 데 유용합니다.
 - Separate – 유니언이나 교차를 개별 파트로 다시 분리합니다.

속이 빈 터널을 만드는 목적을 위해 Union과 Negate 도구만 사용하면 됩니다. 모든 도구에 대한 전체 분석은 고체 모델링을 참조하십시오.

![](../img/05_Roblox_tutorial/Model-Tab-Solid-Modeling.png.webp)
모델 탭에서 고체 모델링 도구가 강조 표시된 모습.

속이 빈 터널을 만들려면:
1. 해상 암초 플랫폼 위에 실린더 파트를 삽입하고 위치를 지정합니다. 샘플 Island Jump - Building 경험은 다음 값으로 Level_4b 플랫폼 위에 이 파트를 위치시킵니다:<br>
    | 이름 |	크기 |	CFrame.Position |	CFrame.Orientation |
    |---|---|---|---|
    |Tunnel |	24, 65, 69	| 137, 77, 69	| 0, 0, 90 |
2. 실린더 파트 안에 속이 빈 부분을 나타내는 블록 파트를 삽입하고 위치를 지정하여 플레이어가 통과할 수 있을 정도로 높고 적절한 너비를 가집니다. 샘플 Island Jump - Building 경험은 다음 값으로 이전 실린더 안에 이 파트를 위치시킵니다:<br>
    | 이름 |	크기 |	CFrame.Position |	CFrame.Orientation |
    |---|---|---|---|
    |Hollow_Part |	24.5, 72, 22	| 134.5, 77, 71	| 0, 135, 90 |
    <br>![](../img/05_Roblox_tutorial/HollowTunnel-Start.jpg.webp)
3. Explorer 창에서 블록 파트를 선택합니다.
4. 모델 탭에서 고체 모델링 섹션으로 이동한 다음 Negate 버튼을 클릭합니다. 파트가 반투명해집니다.<br>![](../img/05_Roblox_tutorial/HollowTunnel-Negate.jpg.webp)
5. Explorer 창에서 반투명 파트와 실린더 터널 파트를 모두 선택합니다.
6. 모델 탭에서 고체 모델링 섹션으로 돌아가서 Union 버튼을 클릭합니다. 반투명 파트가 겹치는 터널 실린더에서 잘립니다.<br>![](../img/05_Roblox_tutorial/HollowTunnel-Union.jpg.webp)
7. 새 유니언의 이름을 높이 수준과 위치를 반영하도록 Level_4b_Union과 같이 변경합니다.
8. 새 유니언 아래에 해상 암초 플랫폼을 복제하고 터널 위에 위치시킵니다. 샘플 Island Jump - Building 경험은 다음 값으로 유니언 위에 복제된 Level_4b 플랫폼을 위치시킵니다:<br>
    | 이름 |	크기 |	CFrame.Position |	CFrame.Orientation |
    |---|---|---|---|
    |Level_4b_Top |	74, 65, 69	| 137, 126, 69	| 0, 0, 90 |
    <br>![](../img/05_Roblox_tutorial/HollowTunnel-Final.jpg.webp)

##### 플레이테스트

플레이 가능한 영역을 그레이박싱한 후에는 환경의 레이아웃을 플레이테스트하여 경험이 재미있고 기능적이며, 개발 과정이 진행됨에 따라 작은 문제가 더 큰 프로젝트로 변하기 전에 잡을 수 있도록 해야 합니다. 예를 들어, 경험의 게임플레이는 플레이어가 수집한 동전 수에 따라 점프력을 점진적으로 업그레이드해야 하므로, 플레이어가 다양한 플랫폼 높이 수준에서 기대하는 Humanoid.JumpPower에 따라 플랫폼 간 점프할 수 있는지 확인하는 것이 중요합니다.

다음 단계별 지침은 다양한 Humanoid.JumpPower 값으로 경험을 플레이테스트하는 방법을 가르칩니다. 플레이테스트를 할 때 다음 질문을 스스로에게 던져 보세요:

 - 플레이어가 각 플랫폼으로 성공적으로 점프할 수 있나요?
 - 플랫폼 간의 높이 차이가 점차 증가하여 플레이어가 진행하도록 유도하나요?
 - 레이아웃이나 게임플레이에서 무엇을 즐기고 있거나 좌절하고 있나요?

경험을 플레이테스트하려면:
1. 메뉴 바에서 재생 버튼을 클릭합니다. Studio가 플레이테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. Explorer 창에서 Roblox 사용자 이름을 표시하는 캐릭터 모델 옆의 화살표를 선택합니다. 모든 캐릭터 모델의 자식 객체가 표시됩니다.
3. Humanoid를 선택합니다.<br>![](../img/05_Roblox_tutorial/Explorer-Character-Humanoid.png.webp)
4. 속성 창에서 점프 설정 섹션으로 이동한 다음 UseJumpPower를 활성화합니다 JumpPower 속성이 기본값 50으로 표시됩니다.
5. JumpPower를 0으로 설정합니다. 이는 캐릭터가 점프할 수 없도록 하여 게임플레이를 스크립트한 후 플레이어의 시작 상태와 동일하게 만듭니다.<br>![](../img/05_Roblox_tutorial/Humanoid-Jump-Settings.png.webp)<br>속성 창이 보이지 않으면 보기 탭을 열고 표시 섹션에서 속성이 선택되어 있는지 확인하십시오.
6. 새 수준에 도달하면 JumpPower를 30의 배수로 설정하여 점프 업그레이드를 시뮬레이션합니다.

<video src="../img/05_Roblox_tutorial/playable-area-walk.mp4" width="320" height="240" controls></video>

튜토리얼의 다음 섹션에서는 경험의 전체 게임플레이를 스크립트하는 방법을 배우게 됩니다.

### Chapter 2 - Script the Gameplay
#### Create a Coin Collection Mechanic

이제 3D 세계가 마련되었으므로, 이 튜토리얼 섹션에서는 코인 수집 메커니즘을 정의하는 첫 번째 스크립트를 추가하는 방법을 가르칩니다. 이 메커니즘은 플레이어가 코인을 수집할 수 있게 하며, 최근에 수집된 코인의 수집을 비활성화합니다.

##### 코인 만들기

스크립트를 작성하기 전에, 코인으로 사용할 자리 표시자 객체를 세계에 추가해야 합니다. 이전 섹션에서 만든 해상 암초 플랫폼처럼, 코인도 간단한 Part 객체일 수 있습니다.

코인을 만들려면:
1. Explorer 창에서 World 폴더에 새 폴더를 추가한 다음 이름을 Coins로 변경합니다.
2. Coins 폴더에 실린더 파트를 삽입한 다음 파트 이름을 Coin으로 변경합니다.<br>![](../img/05_Roblox_tutorial/New-Single-Coin.png.webp)
3. 파트를 선택한 다음 속성 창에서,
    - BrickColor를 Gold로 설정합니다.
    - 재료를 Metal로 설정합니다.
    - 크기를 0.6, 8, 4로 설정합니다.
    - CanCollide를 비활성화합니다. 이는 다른 파트가 코인을 통과할 수 있음을 엔진에 알리며, 플레이어가 코인을 수집하기 위해 코인을 통과할 수 있음을 의미합니다.
    - Anchored를 활성화합니다. 이는 물리 관련 시뮬레이션으로 인해 코인의 위치가 변경되지 않도록 엔진에 알리며, 플레이어가 코인에 닿아도 위치에 영향을 미치지 않음을 의미합니다.
    <br>![](../img/05_Roblox_tutorial/Single-Coin-In-Viewport.jpg.webp)
4. 몇 개의 코인을 복제하여 테스트 목적으로 지도 주변에 배치합니다.<br>![](../img/05_Roblox_tutorial/Duplicated-Coins.png.webp)

![](../img/05_Roblox_tutorial/Multiple-Coins-In-Level.jpg.webp)

이제 실린더 파트가 코인처럼 보이고 물리 시뮬레이션을 방지하지만, 플레이어가 코인을 수집할 수 있도록 논리를 추가해야 합니다.

##### 스크립트 만들기

코인을 수집 가능하게 하려면 플레이어가 코인에 닿을 때 반응해야 합니다. Roblox 엔진은 코인에 무언가가 닿을 때 알려줄 수 있지만, 이를 스크립트에서 선언해야 합니다. 

스크립트를 만들려면:
1. Explorer 창에서 ServerScriptService 위로 마우스를 올리고 ⊕ 버튼을 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
2. 컨텍스트 메뉴에서 스크립트를 선택합니다. ServerScriptService 아래에 새 스크립트가 표시되며, 이는 엔진에 스크립트를 서버에서 실행하고 클라이언트가 코드에 액세스하지 못하도록 합니다.<br>![](../img/05_Roblox_tutorial/Insert-Script.png.webp)
3. 스크립트 이름을 CoinService로 변경합니다.<br>![](../img/05_Roblox_tutorial/Rename-New-Script.png.webp)
4. 기본 코드를 다음 코드로 바꿉니다:<br>
    ```lua
    -- 서비스 및 변수 초기화
    local Workspace = game:GetService("Workspace")
    local Players = game:GetService("Players")

    local coinsFolder = Workspace.World.Coins
    local coins = coinsFolder:GetChildren()

    local COOLDOWN = 10

    -- 이벤트 핸들러 정의
    local function onCoinTouched(otherPart, coin)
        if coin:GetAttribute("Enabled") then
            local character = otherPart.Parent
            local player = Players:GetPlayerFromCharacter(character)
            if player then
                -- 플레이어가 코인에 닿음
                coin.Transparency = 1
                coin:SetAttribute("Enabled", false)
                print("Player collected coin")
                task.wait(COOLDOWN)
                coin.Transparency = 0
                coin:SetAttribute("Enabled", true)
            end
        end
    end

    -- 이벤트 리스너 설정
    for _, coin in coins do
        coin:SetAttribute("Enabled", true)
        coin.Touched:Connect(function(otherPart)
            onCoinTouched(otherPart, coin)
        end)
    end
    ```

이제 플레이어가 코인에 닿을 때마다 코인이 10초 동안 사라지고, 출력 로그에 "Player collected coin"이 표시됩니다.

##### Code Explanation

다음 섹션에서는 스크립트가 작동하는 방식을 자세히 설명합니다.

###### 서비스 및 변수 초기화

다른 언어에서 작성한 많은 코드와 마찬가지로, 나중에 필요할 변수를 스크립트 상단에 정의합니다. 우리의 코드는 다음을 수행합니다:
 - 서비스 인스턴스 가져오기 - Roblox 서비스는 일반 기능에 대한 내장 기능을 제공합니다. 스크립트는 먼저 3D 세계의 모든 객체를 포함하는 Workspace 서비스와 경험에 연결된 모든 플레이어를 관리하고 포함하는 Player 서비스를 가져옵니다.
 - 모든 코인 참조 가져오기 - 스크립트는 GetChildren() 메서드를 사용하여 3D 워크스페이스에서 코인 객체에 대한 모든 참조를 쿼리합니다. 이 메서드는 이 경우 생성한 Workspace.World.Coins 폴더에 연결된 모든 것을 포함하는 배열을 반환합니다.
 - 전역 변수 정의 - COOLDOWN 변수는 코인이 수집된 후 비활성화되는 시간을 정의하는 데 사용됩니다.

서비스 및 변수 초기화
```lua
local Workspace = game:GetService("Workspace")
local Players = game:GetService("Players")

local coinsFolder = Workspace.World.Coins
local coins = coinsFolder:GetChildren()

local COOLDOWN = 10
```

###### 이벤트 핸들러 정의

Roblox 엔진은 3D 세계를 물리적으로 시뮬레이션하고 렌더링, 물리 및 네트워킹과 관련된 이벤트를 처리하는 논리의 많은 부분을 처리합니다. 이러한 이벤트 중 일부에서 사용자 정의 논리를 스크립팅하려는 경우, 이벤트를 청취하고 처리할 수 있으며, 엔진이 나머지를 처리하게 할 수 있습니다. 이 경우, 코인이 닿는 것과 관련된 이벤트를 청취하고 처리합니다. 스크립트는 onCoinTouched() 메서드에서 이 이벤트를 처리하는 논리를 정의하며, 다음을 수행합니다:
 - 코인이 활성화되었는지 감지 - 모든 Instance에는 객체가 3D 세계에 존재하는지 여부를 정의하는 Enabled 부울 속성이 있습니다. GetAttribute() 메서드를 사용하여 인스턴스 속성을 가져올 수 있습니다.
 - 플레이어가 코인에 닿았는지 감지 - 코인이 활성화된 경우, 메서드는 플레이어 서비스로 코인에 닿은 객체가 실제로 플레이어인지 확인합니다. 터치 이벤트가 발생하면 Roblox 엔진은 코인에 닿은 객체를 otherPart 매개변수로 전달합니다. 스크립트는 otherPart의 부모가 플레이어에 속하는지 확인합니다.
 - 플레이어가 코인에 닿았을 때 코인을 비활성화하고 10초 후에 다시 활성화 - 마지막으로, 플레이어가 코인에 닿았을 경우, 메서드는 코인을 비활성화하고 10초 동안 기다렸다가 코인을 다시 수집할 수 있도록 활성화합니다. task.wait()은 wait() 대신 사용되며, 코드 실행을 완전히 중지하지 않고 다른 스레드의 작업을 동시에 실행할 수 있도록 하여 성능을 향상시킵니다.

이벤트 핸들러 정의
```lua
local function onCoinTouched(otherPart, coin)
   if coin:GetAttribute("Enabled") then
      local character = otherPart.Parent
      local player = Players:GetPlayerFromCharacter(character)
      if player then
         -- 플레이어가 코인에 닿음
         coin.Transparency = 1
         coin:SetAttribute("Enabled", false)
         print("Player collected coin")
         task.wait(COOLDOWN)
         coin.Transparency = 0
         coin:SetAttribute("Enabled", true)
      end
   end
end
```

###### 이벤트 핸들러 연결

모든 시뮬레이션된 3D 객체는 BasePart를 상속받아 Touched() 이벤트를 가집니다. 다음 루프는 일반 반복을 사용하여 각 코인을 반복하고 코인이 기본적으로 활성화되도록 하여 코인이 3D 세계에서 보이도록 하고, onCoinTouched() 핸들러 메서드를 코인의 Touched 이벤트에 연결하여 이벤트가 발생할 때마다 실행되도록 합니다. 엔진이 터치를 감지하면, 다른 객체를 otherPart 매개변수로 전달합니다.

이벤트 핸들러 연결
```lua
for _, coin in coins do
   coin:SetAttribute("Enabled", true)
   coin.Touched:Connect(function(otherPart)
      onCoinTouched(otherPart, coin)
   end)
end
```

##### 메커니즘 플레이테스트
코인 수집 메커니즘이 의도한 대로 작동하는지 확인할 시간입니다. 경험을 플레이테스트하려면:
1. 메뉴 바에서 재생 버튼을 클릭합니다. Studio가 플레이테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. 캐릭터를 이동하여 코인에 닿게 합니다. 스크립트가 제대로 작동하면 출력 창에 "Player collected coin"이 표시되고, 코인이 10초 동안 사라졌다가 다시 나타납니다.<br>![](../img/05_Roblox_tutorial/Output-Collect-Coin.png.webp)

출력 창이 보이지 않으면 보기 탭으로 이동한 다음 출력이 선택되어 있는지 확인하십시오.

<video src="../img/05_Roblox_tutorial/script-game-behavior-coin-collection.mp4" width="320" height="240" controls></video>

#### Record and Display Player Data

이제 플레이어가 코인을 수집했을 때 이를 감지할 수 있으므로, 이 튜토리얼 섹션에서는 플레이어가 수집한 코인의 수를 세고, 그 수를 리더보드에 표시하는 방법을 배웁니다.

##### 코인 수집을 기록하는 모듈 스크립트 만들기

각 플레이어의 코인 수집 데이터를 저장하고 관리하려면, 모든 플레이어의 코인 수집 데이터에 접근하는 데이터 구조와 함수를 포함한 `ModuleScript` 객체를 만들어야 합니다. 모듈 스크립트는 다른 스크립트에서 요구할 수 있는 재사용 가능한 코드입니다. 이 경우, `CoinService`는 플레이어가 코인을 터치할 때 코인 수집 데이터를 업데이트할 수 있도록 이 모듈 스크립트를 요구합니다.

모듈 스크립트를 만들려면:
1. Explorer 창에서 ServerStorage 위로 마우스를 올리고 ⊕ 버튼을 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
2. 컨텍스트 메뉴에서 ModuleScript를 선택합니다. ServerStorage 아래에 새 모듈 스크립트가 표시됩니다. 코인 수집 로직을 서버에서 관리하기 때문에 모듈 스크립트를 ServerStorage에 배치합니다.<br> ![](../img/05_Roblox_tutorial/Insert-ModuleScript.png.webp)
3. 모듈 스크립트의 이름을 PlayerData로 변경합니다.<br>![](../img/05_Roblox_tutorial/ModuleScript-Renamed-PlayerData.png.webp)
4. 기본 코드를 다음 코드로 바꿉니다:
  ```lua
  local PlayerData = {}
  PlayerData.COIN_KEY_NAME = "Coins"

  local playerData = {
    --[[
      [userId: string] = {
        ["Coins"] = coinAmount: number
      }
    ]]
  }

  local DEFAULT_PLAYER_DATA = {
    [PlayerData.COIN_KEY_NAME] = 0
  }

  local function getData(player)
    local data = playerData[tostring(player.UserId)] or DEFAULT_PLAYER_DATA
    playerData[tostring(player.UserId)] = data
    return data
  end

  function PlayerData.getValue(player, key)
    return getData(player)[key]
  end

  function PlayerData.updateValue(player, key, updateFunction)
    local data = getData(player)
    local oldValue = data[key]
    local newValue = updateFunction(oldValue)

    data[key] = newValue
    return newValue
  end

  return PlayerData
  ```

**Code Explanation**

모듈 스크립트는 플레이어의 코인 수집 데이터를 나타내는 zero 또는 많은 `playerData` 테이블을 포함하는 `PlayerData` 테이블을 정의합니다. 이 모듈 스크립트를 요구하는 모든 스크립트는 `PlayerData` 테이블의 동일한 복사본을 받으므로 여러 스크립트가 코인 수집 데이터를 수정하고 공유할 수 있습니다.

**데이터 구조 선언**

모듈 스크립트는 빈 테이블 `PlayerData` 선언으로 시작하며, 스크립트 끝에서 반환됩니다. 또한 테이블의 값을 가져오고 설정하는 접근자 메서드를 포함합니다.

`playerData` 테이블에는 테이블의 구조를 설명하는 주석이 포함되어 있어 코드를 이해하기 쉽게 합니다. 이 경우, `playerData` 테이블에는 `userId`와 그 플레이어의 수집된 코인 수를 나타내는 `Coins`라는 필드가 포함됩니다.

```lua
local PlayerData = {}
PlayerData.COIN_KEY_NAME = "Coins"

local playerData = {
  --[[
    [userId: string] = {
        ["Coins"] = coinAmount: number
    }
  ]]
}
...
return PlayerData
```

**로컬 데이터 접근자 정의**
`getData()`는 특정 `playerData` 테이블에 대한 데이터를 가져오는 로컬 함수입니다. 플레이어가 코인을 수집하지 않았다면, 이 함수는 DEFAULT_PLAYER_DATA 테이블을 반환하여 모든 플레이어에게 일부 데이터가 연결되도록 보장합니다. 일반적인 관례는 간단하고 공개된 함수를 만들어 실제 작업을 로컬 범위의 함수에 맡기는 것입니다.

```lua
local DEFAULT_PLAYER_DATA = {
 [PlayerData.COIN_KEY_NAME] = 0
}

local function getData(player)
  local data = playerData[tostring(player.UserId)] or DEFAULT_PLAYER_DATA
  playerData[tostring(player.UserId)] = data
  return data
end
```

**공개 데이터 접근자 정의**
`getValue()`와 `updateValue()`는 이 모듈 스크립트를 요구하는 다른 스크립트가 호출할 수 있는 공개된 함수입니다. 이 경우, `CoinService`는 플레이어가 코인을 터치할 때 플레이어의 코인 수집 데이터를 업데이트하는 데 이 함수를 사용합니다.

```lua
function PlayerData.getValue(player, key)
 return getData(player)[key]
end

function PlayerData.updateValue(player, key, updateFunction)
  local data = getData(player)
  const oldValue = data[key]
  local newValue = updateFunction(oldValue)

  data[key] = newValue
  return newValue
end
```

##### 리더보드 구현
코인 수집 데이터를 화면에 표시되는 리더보드로 시각적으로 표현할 수 있습니다. Roblox는 기본 UI를 사용하여 자동으로 리더보드를 생성하는 내장 시스템을 포함합니다.

리더보드를 만들려면:

1. Explorer 창에서 ServerStorage에 ModuleScript를 생성한 다음 모듈 스크립트의 이름을 Leaderboard로 변경합니다.<br>![](../img/05_Roblox_tutorial/ModuleScript-Renamed-Leaderboard.png.webp)

2. 기본 코드를 다음 코드로 바꿉니다:

  ```lua
  local Leaderboard = {}

  -- 새로운 리더보드 생성
  local function setupLeaderboard(player)
    local leaderstats = Instance.new("Folder")
    -- 'leaderstats'는 리더보드를 생성하기 위해 Roblox에서 인식하는 예약된 이름입니다.
    leaderstats.Name = "leaderstats"
    leaderstats.Parent = player
    return leaderstats
  end

  -- 새로운 리더보드 통계 값 생성
  local function setupStat(leaderstats, statName)
    local stat = Instance.new("IntValue")
    stat.Name = statName
    stat.Value = 0
    stat.Parent = leaderstats
    return stat
  end

  -- 플레이어의 통계 값 업데이트
  function Leaderboard.setStat(player, statName, value)
    local leaderstats = player:FindFirstChild("leaderstats")
    if not leaderstats then
      leaderstats = setupLeaderboard(player)
    end

    local stat = leaderstats:FindFirstChild(statName)
    if not stat then
      stat = setupStat(leaderstats, statName)
    end

    stat.Value = value
  end

  return Leaderboard
  ```

**Code Explanation**

다음 섹션에서는 리더보드가 작동하는 방식을 자세히 설명합니다.

**리더보드 생성**

setupLeaderboard() 함수는 leaderstats라는 이름의 새 폴더 인스턴스를 생성하고 이를 지정된 플레이어의 자식으로 설정합니다. Roblox는 leaderstats라는 이름의 폴더를 통계의 컨테이너로 인식하고 통계를 표시하기 위한 UI 요소를 생성합니다. leaderstats의 값은 "값" 객체(예: StringValue, IntValue 또는 NumberValue)로 저장되어야 합니다.

```lua
-- 새로운 리더보드 생성
local function setupLeaderboard(player)
  local leaderstats = Instance.new("Folder")
  -- 'leaderstats'는 리더보드를 생성하기 위해 Roblox에서 인식하는 예약된 이름입니다.
  leaderstats.Name = "leaderstats"
  leaderstats.Parent = player
  return leaderstats
end

-- 새로운 리더보드 통계 값 생성
local function setupStat(leaderstats, statName)
  local stat = Instance.new("IntValue")
  stat.Name = statName
  stat.Value = 0
  stat.Parent = leaderstats
  return stat
end
```

**플레이어 통계 업데이트**
setStat()는 Leaderboard 모듈에서 유일한 공개 함수입니다. 이 함수는 지정된 플레이어나 리더보드 자체에 대해 통계 값을 생성합니다.

FindFirstChild()는 객체의 이름을 받아 객체가 존재하면 반환하고, 그렇지 않으면 nil을 반환합니다. 이는 객체가 존재하는지 확인하기 전에 사용하는 일반적이고 안전한 방법입니다.

```lua
-- 플레이어의 통계 값 업데이트
function Leaderboard.setStat(player, statName, value)
  local leaderstats = player:FindFirstChild("leaderstats")
  if not leaderstats then
    leaderstats = setupLeaderboard(player)
  end

  local stat = leaderstats:FindFirstChild(statName)
  if not stat then
    stat = setupStat(leaderstats, statName)
  end

  stat.Value = value
end
```

##### 모듈 스크립트 통합

PlayerData 및 Leaderboard 모듈 스크립트가 완료되면, CoinService 스크립트에서 이를 요구하여 플레이어 코인 데이터를 관리하고 표시합니다. CoinService를 업데이트하려면:

Explorer 창에서 CoinService 스크립트를 엽니다.

기존 코드를 다음 코드로 바꿉니다:

```lua
-- 서비스 및 변수 초기화
local Workspace = game:GetService("Workspace")
local Players = game:GetService("Players")
local ServerStorage = game:GetService("ServerStorage")

-- 모듈
local Leaderboard = require(ServerStorage.Leaderboard)
local PlayerData = require(ServerStorage.PlayerData)

local coinsFolder = Workspace.World.Coins
local coins = coins

Folder:GetChildren()

local COIN_KEY_NAME = PlayerData.COIN_KEY_NAME
local COOLDOWN = 10
local COIN_AMOUNT_TO_ADD = 1

local function updatePlayerCoins(player, updateFunction)
  -- 코인 테이블 업데이트
  local newCoinAmount = PlayerData.updateValue(player, COIN_KEY_NAME, updateFunction)

  -- 코인 리더보드 업데이트
  Leaderboard.setStat(player, COIN_KEY_NAME, newCoinAmount)
end

-- 이벤트 핸들러 정의
local function onCoinTouched(otherPart, coin)
  if coin:GetAttribute("Enabled") then
    local character = otherPart.Parent
    local player = Players:GetPlayerFromCharacter(character)
    if player then
      -- 플레이어가 코인에 닿음
      coin.Transparency = 1
      coin:SetAttribute("Enabled", false)
      updatePlayerCoins(player, function(oldCoinAmount)
        oldCoinAmount = oldCoinAmount or 0
        return oldCoinAmount + COIN_AMOUNT_TO_ADD
      end)

      task.wait(COOLDOWN)
      coin.Transparency = 0
      coin:SetAttribute("Enabled", true)
    end
  end
end

-- 이벤트 리스너 설정
for _, coin in coins do
  coin:SetAttribute("Enabled", true)
  coin.Touched:Connect(function(otherPart)
    onCoinTouched(otherPart, coin)
  end)
end
```

**Code Explanation**

원래 CoinService 스크립트의 변경 사항은 다음을 포함합니다:

 - require() 함수를 사용하여 PlayerData 및 Leaderboard 모듈을 가져옵니다.
 - 플레이어가 코인을 수집할 때 추가할 코인의 수를 COIN_AMOUNT_TO_ADD로 선언하고, PlayerData에서 정의한 키 이름을 COIN_KEY_NAME으로 선언합니다.
 = 플레이어의 코인 수와 관련 리더보드 통계를 업데이트하는 도우미 함수 updatePlayerCoins()를 생성합니다.
 - onCoinTouched()에서 플레이어가 코인에 닿았을 때 호출되는 print() 문을 updatePlayerCoins() 호출로 대체합니다.

##### 플레이테스트

코인 수집이 의도한 대로 작동하는지 확인할 시간입니다. 게임에서 코인을 터치하고 수집할 때, 리더보드 UI에 수집한 코인의 수가 표시되어야 합니다. 

경험을 플레이테스트하려면:

1. 메뉴 바에서 재생 버튼을 클릭합니다. Studio가 플레이테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. 캐릭터를 이동하여 코인에 닿게 합니다. 스크립트가 제대로 작동하면 리더보드 UI가 표시되고 코인을 더 많이 수집할수록 코인 수가 증가합니다.

<video src="../img/05_Roblox_tutorial/record-and-display-player-data-example.mp4" width="320" height="240" controls></video>

#### Create Player Hazards

위험 요소는 플레이어가 접촉할 때 체력을 감소시킵니다. 이 튜토리얼 섹션에서는 물과 같은 높이에 있는 큰 보이지 않는 파트를 생성하여 플레이어가 위험에 빠지면 체력이 0으로 변하고 게임의 시작 지점으로 다시 이동하도록 하는 방법을 배웁니다.

##### 기본적인 물 위험 요소 생성하기
기본적인 물 위험 요소를 생성하려면 다음 단계를 따르세요:
1. Explorer 창에서 World 폴더에 새 폴더를 추가하고, 이름을 Hazards로 변경합니다. 대소문자를 정확히 입력하지 않으면 코드가 작동하지 않습니다.
2. Hazards 폴더에 블록 파트를 추가하고 이름을 Hazard로 변경합니다.<br>![](../img/05_Roblox_tutorial/New-Hazard-Part.png.webp)
3. 파트를 이동하고 크기를 조정하여 섬과 플랫폼 주위의 물 라인을 덮습니다. 예를 들어, 샘플 Island Jump - Scripting 경험에서는 Size를 825, 1, 576으로 설정하고 CFrame.Position을 174, -6.5, 38로 설정합니다.<br>![](../img/05_Roblox_tutorial/Hazard-Part-On-Water.jpg.webp)
4. 파트를 선택한 다음 Properties 창에서 다음 속성을 구성하여 위험 요소를 보이지 않게 하고 플레이어가 통과할 수 있도록 합니다:
   - Transparency를 1로 설정합니다. 이렇게 하면 위험 요소가 보이지 않게 되어 실제 물이 위험 요소처럼 보이게 됩니다.
   - CanCollide를 비활성화합니다. 이렇게 하면 다른 파트가 위험 요소를 방해 없이 통과할 수 있어 플레이어가 위험 요소를 통과할 수 있습니다.
   - Anchored를 활성화합니다. 이렇게 하면 물리적 시뮬레이션으로 인해 위험 요소의 위치가 변경되지 않도록 하여 플레이어가 위험 요소를 만져도 위치에 영향을 주지 않습니다.
5. ServerScriptService에 스크립트를 생성하고 이름을 HazardService로 변경합니다.
6. 기본 코드를 다음 코드로 교체합니다:
  ```lua
  local Players = game:GetService("Players")
  local Workspace = game:GetService("Workspace")

  local hazardsFolder = Workspace.World.Hazards
  local hazards = hazardsFolder:GetChildren()

  local function onHazardTouched(otherPart)
    local character = otherPart.Parent
    local player = Players:GetPlayerFromCharacter(character)
    if player then
      local humanoid = character:FindFirstChildWhichIsA("Humanoid")
      if humanoid then
        humanoid.Health = 0
      end
    end
  end

  for _, hazard in hazards do
    hazard.Touched:Connect(onHazardTouched)
  end
  ```

**Code Explanation**
HazardService는 CoinService와 많은 유사점을 가지고 있습니다. 그러나 코인을 수집하는 대신 플레이어가 위험 요소를 만질 때 체력이 0으로 설정됩니다.

위험 요소를 수정, 추가 또는 제거하여 고유한 장애물을 만들 수 있습니다. Hazards 폴더에 포함되어 있는 한, 코드 루프는 이벤트 핸들러를 모든 위험 요소에 연결합니다.

##### 플레이어 생명 주기와 연결하기

플레이어 생명 주기는 플레이어가 게임에 참여, 떠나거나 다시 스폰되는 등의 이벤트를 나타냅니다. 각 주요 생명 주기 이벤트에 대한 논리를 적절히 실행하기 위해 이러한 이벤트에 핸들러를 연결해야 합니다. CoinService 스크립트에서 다음 코드를 스크립트 하단에 복사하여 붙여넣습니다:
```lua
local function onPlayerAdded(player)
  -- 플레이어 코인을 0으로 초기화
  updatePlayerCoins(player, function(_)
    return 0
  end)

  player.CharacterAdded:Connect(function(character)
    -- WaitForChild는 플레이어 루프를 멈추므로 아래는 별도의 스레드에서 수행되어야 합니다.
    task.spawn(function()
      -- 플레이어가 죽을 때
      character:WaitForChild("Humanoid").Died:Connect(function()
        -- 플레이어 코인을 0으로 초기화
        updatePlayerCoins(player, function(_)
          return 0
        end)
      end)
    end)
  end)
end

-- PlayerAdded 이벤트에 연결하기 전에 추가된 플레이어 초기화
for _, player in Players:GetPlayers() do
  onPlayerAdded(player)
end

local function onPlayerRemoved(player)
  updatePlayerCoins(player, function(_)
    return nil
  end)
end

Players.PlayerAdded:Connect(onPlayerAdded)
Players.PlayerRemoving:Connect(onPlayerRemoved)
```

**Code Explanation**

이 코드는 적절한 생명 주기 이벤트 동안 코인 수를 초기화하는 함수를 정의합니다:

   - Player.PlayerAdded는 플레이어가 게임에 참가할 때 발생하며, 코인 수를 0으로 설정합니다.
   - Player.CharacterAdded는 플레이어의 캐릭터 모델이 월드에 추가될 때 발생합니다. 이는 PlayerAdded 이후와 플레이어가 다시 스폰될 때 발생합니다.
   - Humanoid.Died는 플레이어가 죽을 때 발생하며, 코인 수를 0으로 설정합니다. task.spawn()은 이를 처리하기 위해 별도의 스레드를 생성하여 플레이어 생명 주기의 다른 측면이 실행될 수 있도록 합니다.
   - Player.PlayerRemoved는 플레이어가 게임을 떠날 때 발생하여 플레이어 상태를 정리합니다.
   - 이 코드는 플레이어가 Players.PlayerAdded 이벤트가 실행되기 전에 코인을 수집하고 나서 코인 수가 0으로 재설정되는 잠재적 문제를 포함합니다. 이 문제를 완화하려면 코드 스케줄링 또는 초기화가 완료될 때까지 플레이어의 캐릭터를 동결하는 등의 해결책을 고려하십시오. 그러나 이러한 해결책은 이 튜토리얼의 범위를 벗어난 더 복잡한 스크립팅 개념을 포함합니다.

##### 플레이 테스트
이제 플레이어 위험 요소가 의도한 대로 작동하는지 확인할 시간입니다. 물에 닿으면 캐릭터가 죽고 코인을 잃어야 합니다. 
게임을 테스트하려면:
1. 메뉴 바에서 Play 버튼을 클릭합니다. Studio가 플레이 테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. 캐릭터를 이동하여 코인을 몇 개 수집한 다음 물로 뛰어드세요. 스크립트가 올바르게 작동하면 캐릭터가 죽고 리더보드의 코인 수가 0으로 초기화됩니다.
<video src="../img/05_Roblox_tutorial/player-hazards-example.mp4" width="320" height="240" controls></video>

#### Script an Upgrade Button

플레이어가 이제 코인을 수집하고 죽을 때 잃을 수 있지만, 코인은 아무 역할도 하지 않으며, 매우 높이 점프할 수 있는 능력 없이는 게임의 대부분이 접근할 수 없습니다. 이 튜토리얼 섹션에서는 코인을 소비하여 점프 능력을 높이는 화면 버튼을 추가하여 경험의 논리를 완성하는 방법을 배웁니다.

##### 업그레이드 버튼 생성하기
Roblox에서 2D 인터페이스는 일반적으로 GUI 컨테이너 내부의 GUI 구성 요소 모음으로 구성됩니다. 이 경우, 화면 GUI 컨테이너 안에 'Upgrade Jump (5 Coins)'라고 적힌 TextButton 구성 요소만 필요합니다.

GUI를 생성하려면:

1. Explorer 창에서 ReplicatedStorage에 새 폴더를 추가한 후, 폴더 이름을 Instances로 변경합니다. ReplicatedStorage에 있는 모든 객체는 각 플레이어의 Roblox 클라이언트에서 접근할 수 있으며, 이는 GUI가 표시되는 위치입니다.
2. Instances 폴더에 ScreenGui 객체를 추가합니다.
3. ScreenGui 객체를 선택한 다음 Properties 창에서 다음을 설정합니다:
   - Name을 JumpPurchaseGui로 설정합니다.
   - ResetOnSpawn을 비활성화하여 플레이어가 다시 스폰될 때 GUI가 플레이어에게 유지되도록 합니다.
4. Explorer 창에서 JumpPurchaseGui 컨테이너에 TextButton을 삽입한 후, 텍스트 버튼 이름을 JumpButton으로 변경합니다.
5. (선택 사항) 버튼의 외형과 위치를 구성하여 사용자 지정합니다. 간단한 제안은 다음과 같습니다:
   - Text 속성을 'Upgrade Jump (5 Coins)'로 설정합니다.
   - TextSize 속성을 25로 설정합니다.
   - AnchorPoint를 1, 1로 설정하고 Position을 0,0으로 설정하여 버튼을 오른쪽 하단 모서리로 이동합니다.

이 튜토리얼의 나중 부분에서 버튼을 플레이어의 GUI에 추가하지만, 그 전에 버튼이 작동하는 데 필요한 모든 논리와 데이터를 정의해야 합니다.

##### 점프 파워 데이터 정의하기
현재 PlayerData 모듈 스크립트에는 각 플레이어의 코인 수만 저장되어 있습니다. 동일한 방식으로 점프 파워를 저장하고 업데이트해야 합니다. PlayerData의 함수는 변경되는 데이터에 구체적이지 않기 때문에, 플레이어 점프 파워를 저장하기 위해 필요한 것은 Jump 키를 추가하고 DEFAULT_PLAYER_DATA에 초기 값을 초기화하는 것입니다.

점프 파워를 저장하려면 PlayerData 모듈 스크립트를 업데이트하십시오:

1. Explorer 창에서 ServerStorage에 있는 PlayerData 모듈 스크립트를 엽니다.

2. 스크립트의 코드를 다음 샘플로 교체하여 각 플레이어에 대해 기존의 Coins 값과 함께 Jump 값을 초기화합니다:
```lua
local PlayerData = {}

PlayerData.COIN_KEY_NAME = "Coins"
PlayerData.JUMP_KEY_NAME = "Jump"

local playerData = {
	--[[
		[userId: string] = {
			["Coins"] = coinAmount: number,
			["Jump"] = jumpPower: number
		}
	--]]
}

local DEFAULT_PLAYER_DATA = {
	[PlayerData.COIN_KEY_NAME] = 0,
	[PlayerData.JUMP_KEY_NAME] = 0,
}

local function getData(player)
	local data = playerData[tostring(player.UserId)] or DEFAULT_PLAYER_DATA
	playerData[tostring(player.UserId)] = data
	return data
end

function PlayerData.getValue(player, key)
	return getData(player)[key]
end

function PlayerData.updateValue(player, key, updateFunction)
	local data = getData(player)
	local oldValue = data[key]
	local newValue = updateFunction(oldValue)

	data[key] = newValue
	return newValue
end

return PlayerData
```

##### 점프 파워 데이터 업데이트하기
이제 PlayerData가 점프 파워를 추적할 수 있으므로, 플레이어의 클라이언트 요청에서 점프 파워를 업그레이드하는 논리를 서버에 구현해야 합니다.

서버와 클라이언트는 Remote Events 또는 Remote Functions를 통해 통신할 수 있습니다. Remote Events는 발사되었을 때 대기하지 않으며 단방향 통신에 적합합니다. Remote Functions는 응답을 받을 때까지 대기하여 양방향 통신을 가능하게 합니다. 이 경우, 클라이언트는 서버가 플레이어의 점프 파워를 성공적으로 업그레이드했는지 여부를 알아야 하므로 Remote Function이 이상적입니다.

점프 업그레이드를 구현하려면:

1. Explorer 창에서 ReplicatedStorage의 Instances 폴더를 엽니다.
2. Instances 폴더에 RemoteFunction을 삽입한 후, RemoteFunction의 이름을 IncreaseJumpPowerFunction으로 변경합니다. 클라이언트와 서버가 모두 접근할 수 있어야 하기 때문에 Remote Functions는 항상 ReplicatedStorage에 생성합니다.<br>![](../img/05_Roblox_tutorial/Insert-RemoteFunction.png.webp)
3. Explorer 창에서 StarterPlayer를 선택합니다.
4. Properties 창에서 CharacterUseJumpPower 속성을 활성화합니다. 기본적으로 캐릭터의 점프 파워 값은 캐릭터가 점프하는 양을 정의하지 않으므로 이를 활성화해야 합니다.
5. Explorer 창에서 ServerScriptService에 새 스크립트를 삽입한 후, 스크립트 이름을 JumpService로 변경합니다. 이 스크립트에는 점프 업그레이드 논리가 포함됩니다.
6. 기본 코드를 다음 코드로 교체합니다:
```lua
-- Services
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local ServerStorage = game:GetService("ServerStorage")
local Players = game:GetService("Players")

-- Modules
local Leaderboard = require(ServerStorage.Leaderboard)
local PlayerData = require(ServerStorage.PlayerData)

-- Events
local IncreaseJumpPowerFunction = ReplicatedStorage.Instances.IncreaseJumpPowerFunction

local JUMP_KEY_NAME = PlayerData.JUMP_KEY_NAME
local COIN_KEY_NAME = PlayerData.COIN_KEY_NAME
local JUMP_POWER_INCREMENT = 30
local JUMP_COIN_COST = 5

local function updateJumpPower(player, updateFunction)
	-- Update the jump power table
	local newJumpPower = PlayerData.updateValue(player, JUMP_KEY_NAME, updateFunction)

	-- Update the players jump power
	local character = player.Character or player.CharacterAdded:Wait()
	local humanoid = character:FindFirstChild("Humanoid")
	if humanoid then
		humanoid.JumpPower = newJumpPower

		-- Update the jump leaderboard
		Leaderboard.setStat(player, JUMP_KEY_NAME, newJumpPower)
	end
end

local function onPurchaseJumpIncrease(player)
	local coinAmount = PlayerData.getValue(player, COIN_KEY_NAME)
	if coinAmount < JUMP_COIN_COST then
		return false
	end

	-- Increase player's jump power
	updateJumpPower(player, function(oldJumpPower)
		oldJumpPower = oldJumpPower or 0
		return oldJumpPower + JUMP_POWER_INCREMENT
	end)
	-- Update the coin table
	local newCoinAmount = PlayerData.updateValue(player, COIN_KEY_NAME, function(oldCoinAmount)
		return oldCoinAmount - JUMP_COIN_COST
	end)
	-- Update the coin leaderboard
	Leaderboard.setStat(player, COIN_KEY_NAME, newCoinAmount)
	return true
end

local function onCharacterAdded(player)
	-- Reset player's jump power when the character is added
	updateJumpPower(player, function(_)
		return 0
	end)
end

-- Initialize any players added before connecting to PlayerAdded event
for _, player in Players:GetPlayers() do
	onCharacterAdded(player)
end

-- Normal initialization of players from PlayerAdded event
local function onPlayerAdded(player)
	player.CharacterAdded:Connect(function()
		onCharacterAdded(player)
	end)
end

local function onPlayerRemoved(player)
	updateJumpPower(player, function(_)
		return nil
	end)
end

IncreaseJumpPowerFunction.OnServerInvoke = onPurchaseJumpIncrease
Players.PlayerAdded:Connect(onPlayerAdded)
Players.PlayerRemoving:Connect(onPlayerRemoved)
```
**Code Explanation**

다음 섹션에서는 코드를 더 자세히 설명합니다.

   - 점프 파워 데이터 업데이트하기 - `updateJumpPower()`는 플레이어의 점프 파워와 리더보드를 업데이트하여 시각적 피드백을 제공합니다. 이 함수는 Create Player Hazards에서 플레이어를 손상시키는 코드와 유사합니다. Character 모델과 Humanoid가 업그레이드되는 플레이어에게 존재하는 경우, 함수는 PlayerData에 저장된 새 값으로 JumpPower 속성을 업데이트하여 30만큼 증가시킵니다. 게임을 더 오래 지속시키고 싶다면 이 숫자를 줄일 수 있습니다.
   - 서버 요청 검증하기 - `onPurchaseJumpIncrease()`는 먼저 플레이어가 업그레이드를 구매하는 데 필요한 코인 수를 실제로 가지고 있는지 확인합니다. 클라이언트에서 서버로의 모든 요청은 부정 행위자가 잘못된 요청을 제출하여 경험을 악용하지 않도록 검증해야 합니다.

##### 플레이어 GUI에 버튼 추가하기
ScreenGui 객체는 플레이어의 PlayerGui 객체에 상속되어야 화면에 표시됩니다. 기본적으로 이는 채팅 창과 같은 시스템 GUI를 포함합니다. 이제 ReplicatedStorage에 스크립트를 만들어 업그레이드 버튼을 각 플레이어의 GUI에 복사하고 버튼이 눌렸을

 때의 동작을 구현해야 합니다.

플레이어가 참가할 때 버튼을 GUI에 추가하려면:

1. Explorer 창에서 ReplicatedStorage에 Script를 생성합니다.
2. 스크립트를 선택한 다음 Properties 창에서 다음을 설정합니다:
   - Name을 JumpButtonClickHandler로 설정합니다.
   - RunContext를 Client로 설정합니다. 이는 엔진이 항상 이 스크립트를 클라이언트에서 실행하여 네트워크 통신을 최적화하도록 지시합니다.
3. 열린 스크립트에서 기본 코드를 다음 코드로 교체합니다:
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local player = Players.LocalPlayer
local playerGui = player.PlayerGui

local IncreaseJumpPowerFunction = ReplicatedStorage.Instances.IncreaseJumpPowerFunction
local jumpPurchaseGui = ReplicatedStorage.Instances.JumpPurchaseGui
local jumpButton = jumpPurchaseGui.JumpButton

local function onButtonClicked()
	local success, purchased = pcall(IncreaseJumpPowerFunction.InvokeServer, IncreaseJumpPowerFunction)
	if not success then
		-- purchased will be the error message if success is false
		error(purchased)
	elseif success and not purchased then
		warn("Not enough coins!")
	end
end

jumpButton.Activated:Connect(onButtonClicked)

-- Add the JumpPurchaseGui to the player's Gui
jumpPurchaseGui.Parent = playerGui
```

**Code Explanation**

다음 섹션에서는 코드를 더 자세히 설명합니다.

   - GUI 및 서버 함수에 대한 참조 가져오기 - 변수 `IncreaseJumpPowerFunction`, `jumpPurchaseGui` 및 `jumpButton`은 나중에 필요할 함수 및 GUI에 대한 참조를 포함합니다.
   - 이벤트 핸들러 정의 - `onButtonClicked()`는 사용자가 업그레이드 버튼을 클릭할 때의 논리를 정의합니다. 이는 pcall() (보호 호출)을 사용하여 RemoteFunction을 호출합니다. 이와 같은 모든 클라이언트-서버 통신은 오류 또는 연결 문제를 처리하기 위해 pcall()을 필요로 합니다.
   - 핸들러를 버튼에 연결하기 - `Activated` 이벤트는 마우스, 터치스크린 또는 게임패드 컨텍스트를 포함한 모든 플랫폼에서 호환됩니다. 클릭, 터치 또는 게임패드 버튼이 해제될 때 트리거됩니다.

#### 플레이 테스트
이제 업그레이드 버튼을 사용하여 코인을 사용하여 점프 업그레이드를 구매할 수 있어야 합니다. 프로젝트를 테스트하려면:

1. 메뉴 바에서 Play 버튼을 클릭합니다. Studio가 플레이 테스트 모드로 전환됩니다.<br>![](../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp)
2. 스크립트가 올바르게 작동하면 점프 파워를 구매하는 버튼이 화면에 나타납니다. 코인을 수집하기 전에 버튼을 클릭하여 추가 점프 파워가 부여되지 않는지 확인한 다음, 코인을 몇 개 수집하고 다시 클릭하여 업그레이드가 작동하는지 확인하세요.
<video src="../img/05_Roblox_tutorial/script-an-upgrade-button-example.mp4" width="320" height="240" controls></video>

이제 코드가 완성되었으므로, 코인의 양과 위치를 통해 게임의 균형을 맞춰보세요. 게임이 너무 느리게 느껴지면 더 많은 코인을 추가하고, 너무 빠르고 쉽게 느껴지면 코인을 줄이고 도전적인 장소에 배치하세요.

### Chapter 3 - Polish the Experience
#### Create Basic Visual Effects

경험에 기본적인 특수 효과를 추가하면 환경에 동적인 움직임을 더하여 세계가 더 생동감 있고 현실감 있게 느껴집니다. 또한, 특수 효과의 시각적 흥미와 움직임은 종종 플레이어의 관심을 끌어, 경험에서 플레이어를 원하는 방향으로 유도하는 유용한 장치가 됩니다.

이 튜토리얼 섹션에서는 부모 객체와 설정을 구성하는 방법에 따라 2D 이미지 또는 입자를 독특한 방식으로 방출하는 특수 효과인 **입자 방출기**를 사용하는 방법을 배웁니다. 샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험에서 예제를 사용하여 플레이어를 끌어들이는 빛나는 플레어와 공기 중에 질감을 더하는 떠다니는 먼지 입자와 같은 강력하고 미묘한 효과를 만드는 방법을 배우게 됩니다.

##### 플레어 만들기

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample)에서 경험에 동적인 움직임을 추가하기 위해 사용하는 첫 번째 유형의 입자 방출기는 가장 높은 바다 스택 플랫폼 꼭대기의 거대한 플레어입니다. 나머지 환경이 정적이기 때문에 이 효과는 3D 공간의 중심점이 되어 플레이어가 경험의 마지막 플랫폼에 도달할 수 있도록 환경을 진행하도록 유도합니다.

플레어를 만들려면:

1. **Explorer** 창에서 **World** 폴더에 새 폴더를 추가한 다음, 새 폴더 이름을 **VFX**로 변경합니다.
2. **VFX** 폴더에 **블록** 파트를 추가한 다음, 파트를 가장 높은 바다 스택 플랫폼 위 약 10 스터드에 위치시킵니다. 샘플 **Island Jump - Final** 경험은 이 파트를 **Level_7** 플랫폼 위에 다음 값으로 위치시킵니다:
   <table>
      <thead>
      <tr>
      <th>크기</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`20, 20, 20`</td>
      <td>`400, 331, 79`</td>
      <td>`0, 0, 0`</td>
      </tr>
      </tbody>
   </table>
3. 이 블록 파트를 선택한 다음 **Properties** 창에서,
   1. **Name**을 **VFX_Flare**로 설정합니다.
   1. 파트를 보이지 않게 하기 위해 **Transparency**를 **1**로 설정합니다.
   1. 물리 시스템이 경험이 시작될 때 파트를 이동시키지 않도록 **Anchored**를 활성화합니다.
4. 이 파트에 부착물을 추가합니다.
   1. **Explorer** 창에서 블록 파트 위로 마우스를 가져가 **⊕** 버튼을 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
   1. 컨텍스트 메뉴에서 **Attachment**를 삽입합니다. 부착물은 파트의 중심에서 양의 Y축 방향으로 표시됩니다.
5. 이 부착물에 입자 방출기를 추가하고 입자 방출기 이름을 **Emitter_Flare**로 변경합니다. 입자 방출기는 부착물의 방향으로 즉시 입자를 방출합니다.

<video controls src="../img/05_Roblox_tutorial/Flare-1.mp4" width="80%"></video>

##### 플레어 구성하기

이제 경험에 입자 방출기가 있으므로 플레이어가 경험을 시작할 때 마주하는 빛나는 플레어를 방출하도록 속성을 사용자 지정할 수 있습니다. 각 속성이 결과 시각 효과에 어떻게 영향을 미치는지 자세히 알아보려면 `ParticleEmitter` 및 [입자 사용자 지정](https://create.roblox.com/docs/ko-kr/effects/particle-emitters#customizing-particles)을 참조하세요.

###### 입자 이미지

각 입자는 `Texture` 속성에 의해 설정된 이미지를 표시합니다. 자신만의 이미지를 사용하려면 이미지를 Roblox에 업로드하고 자산 ID를 얻어야 합니다. 이 프로세스 및 직접 수행하는 방법에 대한 자세한 내용은 [Assets](https://create.roblox.com/docs/ko-kr/projects/assets)을 참조하세요.

입자 방출기의 `Texture`에 Roblox의 미리 만들어진 플레어 이미지를 사용할 수 있습니다. Roblox의 미리 만들어진 자산을 사용하려면:

1. **Explorer** 창에서 **Emitter_Flare**를 선택합니다.
2. **Properties** 창에서 **Texture**를 `rbxassetid://8983307836`으로 설정합니다.

###### 기본 속성

`ParticleEmitter.Rate`는 초당 방출되는 입자의 양을 결정합니다. `5`의 속도는 입자가 매 `1/5 = 0.2`초마다 방출됨을 의미합니다. `ParticleEmitter.ZOffset`의 값이 클수록 입자가 다른 객체 앞에 렌더링되고, 음수 값은 다른 객체 뒤에 렌더링됨을 의미합니다.

`ParticleEmitter.LightEmission`은 텍스처의 색상과 배경의 색상이 혼합되는 방식을 결정합니다. `0`에서는 텍스처가 정상적으로 혼합되지만, `1`에서는 입자가 겹칠 때 색상이 더 밝아지도록 추가적으로 혼합됩니다. 제공된 텍스처는 이 속성을 `1`로 설정하여 사용하도록 설계되었습니다.

`ParticleEmitter.Lifetime`과 같은 속성은 최소값과 최대값이 필요하며, Roblox는 입자가 방출될 때마다 최소값과 최대값 사이의 임의의 지속 시간을 선택합니다. 이 경우, 입자는 변동 없이 모두 10초 동안 지속되어야 하므로 두 값 모두 `10`으로 설정합니다.

입자 방출기의 기본 속성을 구성하려면:

1. **Explorer** 창에서 **Emitter_Flare**를 선택합니다.
2. **Properties** 창에서,
   1. **Color**를 **127, 84, 59**로 설정하거나 플레어에 선호하는 색상으로 설정합니다.
   2. **LightEmission**을 **1**로 설정하여 추가 혼합을 사용합니다.
   3. **ZOffset**을 **1**로 설정하여 카메라와의 관계에서 예상대로 나타나도록 합니다.
   4. **Lifetime**을 **10, 10**으로 설정합니다.
   5. **Rate**를 **0.45**로 설정합니다.
   6. **RotSpeed**를 **20**으로 설정하여 각 입자가 초당 20도 회전하도록 합니다.
   7. **Speed**를 **0**으로 설정하여 입자가 움직이지 않도록 합니다.

###### 수명 및 NumberSequence 값

`ParticleEmitter.Size` 및 `ParticleEmitter.Transparency`와 같은 속성은 `Datatype.NumberSequence`를 사용하여 입자의 `Lifetime` 동안 속성 값의 변화를 자동화합니다. 예를 들어, 플레어의 `Size`와 `Transparency`의 시퀀스는 입자가 방출될 때마다 맥동 효과를 만듭니다.

`ParticleEmitter.Size` 및 `ParticleEmitter.Transparency`의 시퀀스를 구성하려면:

1. **Explorer** 창에서 **Emitter_Flare**를 선택합니다.
2. **Properties** 창에서 **Size** 값 옆의 **…**를 클릭하여 `Datatype.NumberSequence`를 엽니다.
3. 시퀀스에 점을 추가하려면 시퀀스를 클릭한 다음, 창이 다음 예제와 유사해질 때까지 이동합니다:<br>![](../img/05_Roblox_tutorial/Flare-NumberSequence-Size.png.webp)<br>Y축은 각 입자의 크기를 나타내고 X축은 각 입자의 수명을 나타냅니다. 크기는 0에서 시작하여 수명의 초기에 천천히 성장한 후, 빠르게 크기 10으로 성장하여 수명 동안 10을 유지합니다.
4. 시퀀스를 열려면 **Transparency** 값 옆의 **…**를 클릭합니다.
5. 시퀀스에 점을 추가하려면 시퀀스를 클릭한 다음, 창이 다음 예제와 유사해질 때까지 이동합니다:

   <figure>
   <img src="../img/05_Roblox_tutorial/Flare-NumberSequence-Transparency.png.webp" alt="A number sequence window where the particle is visible (equal or close to 0) for the majority of its lifetime. As the particle approaches the end of its lifetime, its transparency value bounces up and down at different values, settling at 1 at the very end." width="888" />
   <figcaption>입자는 수명의 대부분 동안 보입니다(0 또는 가까운 값). 입자가 수명의 끝에 가까워질 때, 투명도 값이 여러 값에서 위아래로 뛰며, 끝에서는 1로 설정됩니다.</figcaption>
   </figure>

<img src="../img/05_Roblox_tutorial/Final-Flare.jpg.webp" alt="The final version of the flare against a bright blue sky." width="80%" />

##### PointLight 추가하기

플레어를 더 눈에 띄게 하기 위해 플레어에 빛을 넣을 수 있습니다. 사용할 수 있는 세 가지 다른 빛 객체가 있습니다:

- `PointLight`는 단일 지점에서 구형으로 빛을 방출합니다.
- `SpotLight`는 주어진 방향으로 원뿔 모양으로 빛을 방출합니다.
- `SurfaceLight`는 `BasePart`의 한 면에서 빛을 방출합니다.

`PointLight`는 입자 효과의 위치에서 구형으로 빛을 방출하기 위해 가장 적합합니다. 파트에 광원을 생성하려면:

1. **Emitter_Flare**에 **PointLight**를 추가합니다.
2. **PointLight** 객체를 선택한 다음 **Properties** 창에서,
   1. **Brightness**를 **2**로 설정하여 빛을 더 밝게 만듭니다.
   1. **Range**를 **36**으로 설정하여 빛의 범위를 늘립니다.

<img src="../img/05_Roblox_tutorial/Flare-With-PointLight.jpg.webp" alt="The final version of the flare hovering over a gray cylinder sea stack. The flare emits a gentle glow over the sea stack." width="80%" />

##### 먼지 입자 만들기

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample)에서 경험에 동적인 움직임을 추가하기 위해 사용하는 두 번째 유형의 입자 방출기는 대기 중의 먼지 입자입니다. 이 입자는 플레이어 주변에 떠다니며 공기 자체에 질감과 깊이를 더합니다.

먼지 입자를 만들려면:

1. **VFX** 폴더에 **블록** 파트를 삽입한 후, 전체 플레이 가능한 영역을 포함하도록 스케일을 조정합니다. 샘플 **Island Jump - Final** 경험은 이 파트를 다음 값으로 위치시키고 스케일을 조정합니다:
   <table>
   <thead>
   <tr>
   <th>크기</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`645, 355, 275`</td>
   <td>`198, 168, 26`</td>
   <td>`0, 0, 0`</td>
   </tr>
   </tbody>
   </table>
2. 이 블록 파트를 선택한 다음 **Properties** 창에서,
   1. **Name**을 **VFX_DustMotes**로 설정합니다.
   1. 파트를 보이지 않게 하기 위해 **Transparency**를 **1**로 설정합니다.
   1. 플레이어가 이동할 때 파트와 충돌하지 않도록 **CanCollide**를 비활성화합니다.
   1. 물리 시스템이 경험이 시작될 때 파트를 이동시키지 않도록 **Anchored**를 활성화합니다.
3. 이 파트에 입자 방출기를 추가한 다음 입자 방출기 이름을 **Emitter_DustMotes**로 변경합니다. 입자 방출기는 파트의 영역 내에서 즉시 입자를 방출합니다.

<video controls src="../img/05_Roblox_tutorial/DustParticles-1.mp4" width="80%"></video>

###### 먼지 입자 구성하기

먼지 입자 방출기는 변경할 몇 가지 새로운 속성이 필요합니다. `ParticleEmitter.Acceleration`은 입자의 `ParticleEmitter.Speed`가 수명 동안 어떻게 변하는지를 결정합니다. 가속도는 종종 음의 `Y` 값을 가진 입자에 중력 효과를 적용하는 데 사용됩니다.

`ParticleEmitter.Rotation`은 방출된 입자의 회전 범위를 도 단위로 정의하며, 양수 값은 시계 방향을 의미합니다. 각 먼지 입자의 회전에 무작위성을 더하기 위해 각도를 선택할 범위를 만들 수 있습니다.

`NumberSequence`의 각 점에 대해 창 하단의 숫자 입력을 사용하여 _엔벨로프_를 설정할 수 있습니다. 엔벨로프는 입자가 방출될 때마다 스튜디오가 점 값보다 높거나 낮은 임의의 값을 선택하는 범위를 설정합니다. 엔벨로프의 크기는 임의 선택의 범위를 결정합니다. `ParticleEmitter.Transparency`의 시퀀스에는 엔벨로프가 포함되어 각 입자의 가시성이 예측 불가능하게 됩니다.

다음은 이전에 설명한 모든 속성의 값입니다. 이러한 설명은 [플레어 구성하기](#configure-the-flare)를 다시 참조하세요.

1. **Explorer** 창에서 **Emitter_DustMotes**를 선택합니다.
2. **Properties** 창에서,
   1. **Color**를 **192, 241, 255**로 설정합니다.
   2. **Size**를 다음 `NumberSequence`로 설정합니다:

      <figure>
      <img src="../img/05_Roblox_tutorial/DustMotes-NumberSequence-Size.png.webp" alt="A number sequence window where the size rises to 0.25 shortly after creation, then fades down gradually to 0." width="888" />
      <figcaption>크기는 생성 직후 0.25로 증가한 다음 점차적으로 0으로 감소합니다.</figcaption>
      </figure>

   3. **Texture**를 **rbxassetid://14302399641**로 설정합니다.
   4. **Transparency**를 다음 `NumberSequence`로 설정합니다:

      <figure>
      <img src="../img/05_Roblox_tutorial/DustMotes-NumberSequence-Transparency.png.webp" alt="A number sequence window where the particle begins fully transparent, becomes randomly more opaque with an envelope of 0.1, then slowly fades out." width="888" />
      <figcaption>입자는 완전히 투명하게 시작하여 엔벨로프 0.1로 무작위로 더 불투명해진 다음 천천히 사라집니다.</figcaption>
      </figure>

   5. **ZOffset**을 **-5**로 설정하여 플레이어와 다른 객체 뒤에 나타나도록 합니다.
   6. **Lifetime**을 **1, 10**으로 설정합니다.
   7. **Rate**를 **50000**으로 설정합니다. 이는 빠른 속도이지만, 입자 방출기의 부모 파트의 부피가 너무 커서 희박하게 나타납니다.
   8. **Rotation**을 **-45, 45**로 설정합니다.
   9. **RotSpeed**를 **-60**으로 설정합니다.
   10. **Speed**를 **1, 5**로 설정합니다.
   11. 입자가 부드럽게 위로 떠오르도록 **Acceleration**을 **1, -1, 1**로 설정합니다.

<figure>
<img src="../img/05_Roblox_tutorial/Dust-Motes-Sky.jpg.webp" alt="The final version of the dust particles against a bright blue sky." />
<figcaption>플랫폼에서 하늘을 올려다보며 공기 중에 희미한 먼지 입자</figcaption>
</figure>

#### Customize Global Lighting


**글로벌 조명**은 환경에서 태양이나 달로부터 나오는 광휘를 의미합니다. `Lighting` 서비스와 Studio의 기본 자식 객체의 몇 가지 주요 기본 속성을 사용자 지정하여 경험에서 글로벌 조명이 어떻게 보이고 느껴지는지, 그리고 3D 공간에 배치한 다른 객체와의 상호 작용 방식을 크게 변경할 수 있습니다.

Studio의 기본 조명 설정에 몇 가지 수정만으로 이 튜토리얼 섹션에서는 태양의 위치와 빛의 색상을 변경하고, 극적인 그림자를 만들고, 대기를 두껍게 하는 등 글로벌 조명을 사용자 지정하는 방법을 배웁니다.

```
경험에서 글로벌 조명에 영향을 미칠 수 있는 추가 조명 객체를 사용자 지정할 수 있습니다. Studio에서 사용 가능한 모든 조명 객체 개요는 [조명 및 효과]를 참조하세요.
```

##### 조명 속성 설정

`Lighting` 서비스는 경험에서 글로벌 조명을 사용자 지정하기 위해 조정할 수 있는 다섯 가지 상위 범주의 속성을 포함합니다:

- **Color** - 환경 내 색조를 구성합니다.
- **Intensity** - 카메라에 닿는 빛의 양을 구성합니다.
- **Shadows** - 환경 내에서 그림자가 렌더링되는 방식을 구성합니다.
- **Environment** - 시간대와 지리적 위도와 같은 환경 조건을 구성합니다.
- **Technology** - 조명과 그림자를 렌더링하는 데 Studio가 사용하는 조명 기술을 구성합니다.

다음 지침에서는 주변 및 반사 조명의 색상을 변경하고, 그림자의 가장자리를 더 선명하게 만들고, 가장 고급 조명 기술을 활용하며, 샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 설정에 맞게 태양과 세계의 위치를 수정하는 방법을 보여줍니다.

###### 조명의 색상 조정

샘플 **Island Jump - Final** 경험의 `Lighting` 서비스 속성에 맞추는 첫 번째 단계는 환경에서 주변 및 반사 조명의 색상을 조정하는 것입니다. 주변 조명의 색상을 제어하는 두 가지 조명 서비스 속성이 있습니다:

- `Lighting.Ambient`는 실내 공간이나 야외 덮개 아래와 같이 하늘로부터 가려진 부분의 주변 조명의 색상을 제어합니다.
- `Lighting.OutdoorAmbient`는 하늘이 보이는 부분의 주변 조명의 색상을 제어합니다.

또한, `Lighting.ColorShift_Top` 속성은 태양이나 달을 향한 표면에서 반사되는 빛의 색상을 제어합니다. 기본적으로 이 세 가지 속성은 세계 전체에 어두운 회색 톤을 생성하도록 설정되어 있지만, 최종 샘플의 해양 환경을 보완하기 위해 이 속성을 조정하여 주변 및 반사 조명이 전통적인 해양 팔레트의 미묘한 **파란색-회색** 톤을 갖도록 만들 수 있습니다.

<div><b>샘플 Island Jump 경험의 기본 및 사용자 지정 주변 조명 비교</b></div>
<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Default-Color.jpg.webp" alt="The sample Island Jump experience with default ambient lighting visuals." />
    <figcaption>기본 속성</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-Color.jpg.webp" alt="The sample Island Jump experience with custom ambient lighting visuals." />
    <figcaption>사용자 지정 속성</figcaption>
  </figure>
</GridContainer>

환경에서 주변 조명의 색상을 조정하려면:

1. **Explorer** 창에서 **Lighting**을 선택합니다.
2. **Properties** 창에서,
   1. **Ambient**를 **16, 16, 16**으로 설정합니다. 전체 환경이 미묘하게 어두워집니다.
   1. **ColorShift_Top**을 **196, 222, 255**로 설정합니다. 태양을 향한 표면에서 반사되는 색조가 밝아집니다.
   1. **OutdoorAmbient**를 **134, 158, 190**으로 설정합니다. 터널을 제외한 모든 영역이 파란색-회색 색조로 표시됩니다.

###### 그림자 경화

샘플 **Island Jump - Final** 경험의 `Lighting` 서비스 속성에 맞추는 두 번째 단계는 환경에서 그림자를 경화하는 것입니다. 이는 플레이어가 경험의 야외와 덮개가 있는 영역을 탐색할 때 더 극적인 효과를 만듭니다.

<div><b>샘플 Island Jump 경험의 기본 및 사용자 지정 그림자 비교</b></div>
<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Default-Shadows.jpg.webp" alt="The sample Island Jump experience with default shadow visuals that produce fuzzy shadows." />
    <figcaption>기본 그림자</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-Shadows.jpg.webp" alt="The sample Island Jump experience with custom shadow visuals that produce sharp shadows."/>
    <figcaption>사용자 지정 그림자</figcaption>
  </figure>
</GridContainer>

환경에서 그림자를 경화하려면:

1. **Explorer** 창에서 **Lighting**을 선택합니다.
2. **Properties** 창에서 **ShadowSoftness**를 **0**으로 설정합니다. 그림자가 선명한 가장자리를 생성합니다.

###### 미래 조명 시스템 활성화

샘플 **Island Jump - Final** 경험의 `Lighting` 서비스 속성에 맞추는 세 번째 단계는 Studio에서 가장 고급 조명 시스템을 활성화하는 것입니다. Studio는 `Enum.Technology.ShadowMap` 조명 시스템으로 모든 경험을 시작하며 이는 글로벌 조명에서 선명한 그림자와 조명을 렌더링합니다. 그러나 환경을 향상시키고 로컬 광원이 정밀한 그림자와 조명을 생성할 수 있도록 하려면 대신 `Enum.Technology.Future` 조명 시스템 기술을 활성화해야 합니다.

미래 조명 시스템은 글로벌 조명과 로컬 조명이 함께 작동하여 더 현실적이고 몰입감 있는 시각 효과를 제공합니다. 예를 들어, ShadowMap 조명 시스템에서는 빛나는 플레어에서 그림자가 전혀 생성되지 않지만, 미래 조명 시스템 기술에서는 바다 스택 플랫폼의 둘레에서 미묘한 그림자를 생성합니다. 이 효과는 환경 내에 더 많은 광원이 있을수록 더 두드러집니다.

<div><b>ShadowMap 조명 시스템과 Future 조명 시스템 비교</b></div>
<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/ShadowMap-System.jpg.webp" alt="The sample Island Jump experience with the ShadowMap lighting system." />
    <figcaption>ShadowMap 조명 시스템</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Future-System.jpg.webp" alt="The sample Island Jump experience with the Future lighting system that produces more prominent lighting from the flare."/>
    <figcaption>Future 조명 시스템</figcaption>
  </figure>
</GridContainer>

미래 조명 시스템을 활성화하려면:

1. **Explorer** 창에서 **Lighting**을 선택합니다.
2. **Properties** 창에서 **Technology** 드롭다운을 클릭한 다음, **Future**를 선택합니다. 조명 시스템이 업데이트됩니다.

###### 태양 위치 변경

샘플 **Island Jump - Final** 경험의 `Lighting` 서비스 속성에 맞추는 마지막 단계는 하늘에서 태양의 위치를 변경하는 것입니다. 태양의 위치를 제어하는 세 가지 속성이 있습니다:

- `Lighting.ClockTime`은 0시부터 24시까지의 현재 시간을 나타냅니다.
- `Lighting.TimeOfDay`는 24시간 문자열로 현재 시간을 나타냅니다.
- `Lighting.GeographicLatitude`는 지리적 위도를 도 단위로 나타냅니다.

```
`Lighting.ClockTime`과 `Lighting.TimeOfDay`는 직접적으로 관련되어 있으므로 한 속성을 변경하면 다른 속성도 변경되므로 하루의 시간을 변경하려면 이 두 속성 중 하나만 사용자 지정하면 됩니다.
```

태양의 기본 위치는 하늘 높이 있으며, 실제 세계에서 정오에 해당하는 위치입니다. 그러나 더 두드러진 그림자와 방향성을 생성하려면 태양을 바다 스택 플랫폼 오른쪽으로 이동할 수 있습니다.

<div><b>기본 및 사용자 지정 태양 위치 비교</b></div>
<GridContainer numColumns="2">
  <figure>


    <img width="100%" img src="../img/05_Roblox_tutorial/Default-SunPosition.jpg.webp" alt="The sample Island Jump experience with the default sun position high in the sky."/>
    <figcaption>기본 태양 위치</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-SunPosition.jpg.webp" alt="The sample Island Jump experience with a custom sun position approaching the horizon." />
    <figcaption>사용자 지정 태양 위치</figcaption>
  </figure>
</GridContainer>

태양 위치를 변경하려면:

1. **Explorer** 창에서 **Lighting**을 선택합니다.
2. **Properties** 창에서,
   1. **ClockTime**을 **9**로 설정합니다. 태양이 오전 9시에 실제 세계에서의 위치로 이동합니다.
   2. **GeographicLatitude**를 **78**로 설정합니다. 세계가 78도 이동하여 태양이 바다 스택 플랫폼 오른쪽으로 이동합니다.

##### 대기 속성

`Lighting` 서비스의 자식 객체인 `Atmosphere`는 공기 입자를 시뮬레이트하는 속성을 기반으로 햇빛을 독특한 방식으로 산란시켜 현실적인 환경 조명 효과를 생성할 수 있게 합니다. 이러한 속성은 환경의 공기 두께를 형성하여 대기에 깊이감을 부여하는 데 매우 유용할 수 있습니다.

다음 지침에서는 샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험과 같이 물의 가장자리를 숨기고 더 많은 심도 효과를 생성하기 위해 `Atmosphere` 속성을 조정하여 약간 두꺼운 대기를 만드는 방법을 보여줍니다.

```
`Atmosphere` 내 추가 속성 개요는 [대기 효과]를 참조하세요.
```

###### 공기 입자 밀도 증가

샘플 **Island Jump - Final** 경험의 `Atmosphere` 속성에 맞추는 첫 번째 단계는 공기 입자 밀도를 증가시키는 것입니다. `Atmosphere.Density` 속성은 환경의 공기 중에 존재하는 입자의 양을 제어합니다. 이 속성을 증가시키면 추가된 입자가 플레이어의 배경 물체 시야를 방해합니다. 이는 특히 물 지형의 경계를 숨기는 데 유용합니다.

<div><b>기본 및 사용자 지정 공기 입자 밀도 비교</b></div>
<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-SunPosition.jpg.webp" alt="The sample Island Jump experience with the default air particle density that produces a clear background." />
    <figcaption>기본 공기 입자 밀도</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-AirParticleDensity.jpg.webp" alt="The sample Island Jump experience with custom air particle density that produces a hazy background." />
    <figcaption>사용자 지정 공기 입자 밀도</figcaption>
  </figure>
</GridContainer>

환경에서 공기 입자 밀도를 증가시키려면:

1. **Explorer** 창에서 **Lighting** 서비스로 이동한 다음 자식 객체 **Atmosphere**를 선택합니다.
2. **Properties** 창에서 **Density**를 **0.375**로 설정합니다. 공기가 두꺼워집니다.

###### 먼 물체 블렌딩

샘플 **Island Jump - Final** 경험의 `Atmosphere` 속성에 맞추는 두 번째 단계이자 이 튜토리얼 섹션의 마지막 단계는 수평선의 먼 물체를 블렌딩하는 것입니다. `Atmosphere.Offset` 속성은 카메라와 하늘 배경 사이의 빛의 전달 방식을 제어합니다. 이 값을 증가시키면 수평선 실루엣을 생성하고, 이 값을 감소시키면 먼 물체가 하늘과 블렌딩되어 무한하고 매끄러운 오픈 월드를 만듭니다.

샘플 경험은 이 속성을 0으로 설정하여 플레이어가 수평선을 볼 수 없도록 할 수 있었지만, 튜토리얼의 다음 섹션에서는 경험의 경계 근처에 산 객체를 추가하여 보이도록 할 필요가 있습니다. 또한, 기본 값을 감소시키되 0으로 설정하지 않으면, 먼 곳에 안개가 끼기 시작하는 것을 모방하여 더 현실적인 환경을 만듭니다.

<div><b>기본 및 사용자 지정 Offset 값 비교</b></div>
<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-AirParticleDensity.jpg.webp" alt="The sample Island Jump experience with default Offset values that keep the background visible." />
    <figcaption>기본 `Atmosphere.Offset` 속성</figcaption>
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Custom-Offset.jpg.webp" alt="The sample Island Jump experience with custom Offset values that hide the edges of the background."/>
    <figcaption>사용자 지정 `Atmosphere.Offset` 속성</figcaption>
  </figure>
</GridContainer>

환경에서 먼 물체를 블렌딩하려면:

1. **Explorer** 창에서 **Lighting** 서비스로 이동한 다음 자식 객체 **Atmosphere**를 선택합니다.
2. **Properties** 창에서 **Offset**을 **0.17**로 설정합니다. 공기가 두꺼워집니다.

이제 경험의 글로벌 조명이 사용자 지정 속성으로 설정되었으므로, 튜토리얼의 다음 섹션에서는 회색 상자 레이아웃을 고품질의 정교한 자산으로 교체하는 방법을 배웁니다.

<Tabs>
  <TabItem label="사용자 지정 전">
    <img src="../img/05_Roblox_tutorial/Lighting-Pre-Customization.jpg.webp" alt="The sample Island Jump experience's lighting visuals before the customization from this page." />
  </TabItem>
  <TabItem label="사용자 지정 시각 효과">
    <img src="../img/05_Roblox_tutorial/Lighting-Post-Customization.jpg.webp" alt="The sample Island Jump experience's lighting visuals after the customization from this page." />
  </TabItem>
</Tabs>

#### Apply Polished Assets

**고품질 자산 적용**은 최종 환경을 구성하는 마지막 단계로, 회색 상자 자리 표시 자산을 고품질의 세련된 자산으로 교체하여 경험의 미적 목표와 게임 디자인 요구를 충족시키는 과정입니다. 이 커리큘럼의 흥미진진한 섹션에서 여러분의 세계가 완성된 일관된 환경으로 변모하는 것을 확인할 수 있습니다.

[Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) `.rbxl` 파일을 참고하여, 이 튜토리얼 섹션에서는 Creator Store를 사용하여 샘플 자산 라이브러리를 프로젝트에 추가하고, 새로운 자산을 의미 있는 카테고리로 정리하는 조직 구조를 계속 유지하며, 자산 라이브러리를 3D 공간에 적용하는 방법을 배웁니다.

##### 자산 라이브러리 가져오기

**Creator Store**는 Roblox 및 Roblox 커뮤니티에서 만든 모든 자산을 프로젝트에서 사용할 수 있도록 찾을 수 있는 Toolbox의 탭입니다. 여기에는 모델, 이미지, 메쉬, 오디오, 플러그인, 비디오 및 글꼴 자산이 포함됩니다. Creator Store를 사용하여 개별 자산이나 자산 라이브러리를 열린 경험에 직접 추가할 수 있습니다.

자산 라이브러리는 쉽게 액세스하고 재사용할 수 있도록 경험의 중앙 위치에 배치할 수 있는 자산 모음입니다. Creator Store에서 사용할 자산 라이브러리에는 여섯 개의 3D 자산, 두 개의 사용자 정의 `MaterialVariant` 재료 및 [기본 시각 효과 만들기]에서 최종 입자 효과가 포함됩니다. 여섯 개의 메쉬는 다음과 같습니다:

<GridContainer numColumns="3">
  <figure>
    <img src="../img/05_Roblox_tutorial/Platform-A-Model.jpg.webp" alt="A mesh that's a grassy, circular platform with concrete surrounding its edges." />
    <figcaption>PlatformA</figcaption>
  </figure>
    <figure>
     <img src="../img/05_Roblox_tutorial/Platform-B-Model.jpg.webp" alt="A mesh that's a grassy, circular platform with rock underneath."/>
    <figcaption>PlatformB</figcaption>
  </figure>
    <figure>
    <img src="../img/05_Roblox_tutorial/Coin-Mesh.jpg.webp" alt="A mesh that's a shiny golden coin with a Roblox logo in the middle." />
    <figcaption>Coin</figcaption>
  </figure>
  <figure>
    <img src="../img/05_Roblox_tutorial/Sea-Stack-Mesh.jpg.webp" alt="A mesh that's a large rock sea stack." />
    <figcaption>SeaStackMesh</figcaption>
  </figure>
  <figure>
    <img src="../img/05_Roblox_tutorial/Sea-Stack-Cave-Mesh.jpg.webp" alt="A mesh that's a large rock sea stack with a hollow tunnel in the middle." />
    <figcaption>SeaStackCaveMesh</figcaption>
  </figure>
    <figure>
    <img src="../img/05_Roblox_tutorial/Mountain-Mesh.jpg.webp" alt="A mesh that's a large snowy mountain." />
    <figcaption>MountainMesh</figcaption>
  </figure>
</GridContainer>

이 3D 자산 각각은 단일 `MeshPart` 객체 또는 여러 `MeshPart` 객체를 저장하는 `Model` 객체이며, 사용자 정의 재료 또는 현실적인 음영과 조명을 표현할 수 있는 물리 기반 렌더링(PBR) 텍스처를 사용합니다. 이 과정에 대한 자세한 내용은 [재료 - 사용자 정의 재료] 및 [PBR 텍스처]를 참조하세요.

다음 구성 요소에서 **Add to Inventory** 링크를 클릭하여 Studio에서 인벤토리에 라이브러리를 추가할 수 있습니다. 자산이 인벤토리에 추가되면 플랫폼의 모든 프로젝트에서 이를 재사용할 수 있습니다.

[Core-Building-and-Scripting-Library](https://create.roblox.com/store/asset/14238769242)

인벤토리에서 경험으로 자산 라이브러리를 가져오려면:

1. 메뉴 바에서 **View** 탭을 선택합니다.
2. **Show** 섹션에서 **Toolbox**를 클릭합니다. **Toolbox** 창이 표시됩니다.

   <img src="../img/05_Roblox_tutorial/View-Tab-Toolbox.png.webp" alt="Studio's View tab with the Toolbox tool highlighted." width="876" />

3. **Toolbox** 창에서 **Inventory** 탭을 클릭합니다. **My Models** 정렬이 표시됩니다.

   <img src="../img/05_Roblox_tutorial/Inventory-Tab.png.webp" alt="Studio's Toolbox window with the Inventory tab highlighted." width="360" />

4. **Core Building and Scripting** 타일을 클릭합니다. 라이브러리가 뷰포트에 표시되지만 일부 메쉬는 올바른 텍스처를 표시하지 않습니다. 이는 재료가 아직 `MaterialService`에 없는 사용자 정의 변형으로 설정되어 있기 때문입니다.

   <img src="../img/05_Roblox_tutorial/Asset-Library-Complete.jpg.webp" alt="All meshes from the asset library hover above the water. Some of the meshes are missing their textures so they appear gray." width="800" />

5. **Explorer** 창에서 샘플 자산 라이브러리의 **Moss_Lumpy_A**와 **Moss_Strata_Noisy_A**를 선택한 다음, **MaterialService** 컨테이너로 드래그합니다. 자산 라이브러리가 업데이트되어 올바른 재료를 표시합니다.

   <img src="../img/05_Roblox_tutorial/MaterialService-Contents.png.webp" alt="Studio's Explorer window with both the Moss_LumpyA and Moss_Strata_Noisy_A textures highlighted underneath MaterialService." width="320" />

   <img src="../img/05_Roblox_tutorial/Asset-Library-Complete-With-Materials.jpg.webp" alt="All meshes from the asset library hover above the water, now complete with all of their textures." width="800" />

##### 조직 구조 계속하기

자산 라이브러리를 회색 상자 기하학에 적용하기 전에 [Greybox a Playable Area]에서 시작한 조직 구조를 계속 유지하여 환경에 추가할 새로운 자산에 대한 컨테이너 객체를 생성하는 것이 중요합니다. 이 과정은 Workspace를 조직적으로 유지하고 쉽게 스캔할 수 있도록 하여 특정 자산 그룹을 빠르게 업데이트할 수 있게 합니다.

조직 구조에 추가 컨테이너 객체를 추가하려면:

1. **Explorer** 창에서 **World** 폴더에 새 폴더 두 개를 삽입합니다.
2. 폴더 이름을 각각 **Platforms**와 **Mountains**로 변경합니다.
3. **Platforms** 폴더에 환경의 각 바다 스택 플랫폼에 대한 새 모델을 삽입하고, [Greybox a Playable Area]에서 만든 바다 스택 레벨 명명에 따라 이름을 변경합니다. 예를 들어, 샘플 경험에는 환경의 모든 플랫폼에 대해 18개의 개별 모델 컨테이너가 있습니다.

   <img src="../img/05_Roblox_tutorial/Organization-Structure.jpg.webp" alt="Studio's Explorer window with all of the level model objects underneat the Platforms folder." width="25%" />

##### 자산 라이브러리 적용하기


다음 지침에서는 두 가지 다른 교육 경로를 제공합니다: 고유한 환경에 자산 라이브러리를 적용하거나, 샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험 내 최종 환경을 정확히 재현하는 방법을 선택할 수 있습니다.


이제 새로운 자산을 포함할 조직 구조를 갖추었으므로, 자산 라이브러리를 회색 상자 기하학에 적용하기 시작할 수 있습니다. 두 교육 경로 중 하나를 따르면서, 예제 이미지는 자리 표시 자산을 반투명하게 만들어 단계별 진행 상황을 볼 수 있습니다.

<Tabs>
  <TabItem key = "1" label="Graybox Version">
    <img src="../img/05_Roblox_tutorial/Pre-Polished-Assets.jpg.webp" alt="A version of the sample Island Jump experience's placeholder greybox geometry." width="800" height="450" />
  </TabItem>
  <TabItem key = "2" label="Polished Assets">
    <img src="../img/05_Roblox_tutorial/Final-Polished-Assets.jpg.webp" alt="A version of the sample Island Jump experience with polished geometry." width="800" height="450" />
  </TabItem>
</Tabs

>

###### Platforms

샘플 자산 라이브러리에는 바다 스택 플랫폼 상단에 사용할 수 있는 두 가지 유형의 플랫폼이 포함되어 있습니다:

- **PlatformA** – 초기 및 최종 플랫폼용 금속 원형 베이스를 포함합니다.
- **PlatformB** – 중간 레벨 플랫폼용 기본 지형 캡을 포함합니다.

두 플랫폼 유형 모두 두 개의 `MeshPart` 객체를 포함하는 `Model` 객체입니다.

<img src="../img/05_Roblox_tutorial/Platform-Types.jpg.webp" alt="Platform A and Platform B are side-by-side, and highlighted with their platform type." width="80%" />

<Tabs>
  <TabItem key = "1" label="Apply Your Own Platforms">

플랫폼에 자산 라이브러리를 적용하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **PlatformA**를 복사합니다.
   1. **PlatformA**를 마우스 오른쪽 버튼으로 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
   1. 컨텍스트 메뉴에서 **복사**를 선택합니다.
1. **Platforms** 폴더에서 **Level_1** 모델에 **PlatformA**를 붙여넣습니다.
1. **Home** 탭에서 **Move** 및 **Scale** 도구를 사용하여 모델을 첫 번째 자리 표시 바다 스택 플랫폼의 크기로 위치시키고 크기를 조정합니다.

   <img src="../img/05_Roblox_tutorial/First-Platform.jpg.webp" alt="A view of the sample laser tag experience with only the first platform visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

1. 이 과정을 반복하여 각 자리 표시 바다 스택 플랫폼의 상단에 **PlatformA** 또는 **PlatformB** 자산을 추가하고 구성합니다.

   <img src="../img/05_Roblox_tutorial/Platforms-5.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험 내 바다 스택 플랫폼을 정확히 재현하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **PlatformA**를 복사합니다.
   1. **PlatformA**를 마우스 오른쪽 버튼으로 클릭합니다. 컨텍스트 메뉴가 표시됩니다.
   1. 컨텍스트 메뉴에서 **복사**를 선택합니다.
2. **Platforms** 폴더에서 **Level_1** 모델에 **PlatformA**를 붙여넣습니다.
3. **Properties** 창에서,

   1. **Origin.Position**을 **-30, 3, 9**로 설정합니다.
   1. **Scale**을 **2.2**로 설정합니다.

   <img src="../img/05_Roblox_tutorial/First-Platform.jpg.webp" alt="A view of the sample laser tag experience with only the first platform visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

4. 이 과정을 반복하여 다음 **PlatformA** 자산을 해당 바다 스택 플랫폼 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>부모 모델</th>
   <th>Origin.Position</th>
   <th>Scale</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>Level_2</td>
   <td>`-24, 11, 24`</td>
   <td>`1.4`</td>
   </tr>
   <tr>
   <td>Level_3a</td>
   <td>`34, 31, 9.5`</td>
   <td>`0.7`</td>
   </tr>
   <tr>
   <td>Level_3b</td>
   <td>`79, 31, 2`</td>
   <td>`0.6`</td>
   </tr>
   <tr>
   <td>Level_7</td>
   <td>`402, 312, 79`</td>
   <td>`1.1`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Platforms-4.jpg.webp" alt="A view of the sample laser tag experience with all Platform A platforms visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

5. 다음 **PlatformB** 자산을 해당 바다 스택 플랫폼 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>부모 모델</th>
   <th>Origin.Position</th>
   <th>Scale</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>Level_3c</td>
   <td>`89, 31, 48`</td>
   <td>`0.8`</td>
   </tr>
   <tr>
   <td>Level_4a</td>
   <td>`104, 65.5, 46.5`</td>
   <td>`0.6`</td>
   </tr>
   <tr>
   <td>Level_4b</td>
   <td>`127, 66, 67.5`</td>
   <td>`0.6`</td>
   </tr>
   <tr>
   <td>Level_4b</td>
   <td>`133.5, 164.5, 70.5`</td>
   <td>`0.7`</td>
   </tr>
   <tr>
   <td>Level_4c</td>
   <td>`152, 65.5, 91`</td>
   <td>`1`</td>
   </tr>
   <tr>
   <td>Level_4d</td>
   <td>`200, 66, 107`</td>
   <td>`0.5`</td>
   </tr>
   <tr>
   <td>Level_4e</td>
   <td>`238.5, 66, 81`</td>
   <td>`0.8`</td>
   </tr>
   <tr>
   <td>Level_5a</td>
   <td>`262, 120, 57.5`</td>
   <td>`0.7`</td>
   </tr>
   <tr>
   <td>Level_5b</td>
   <td>`245, 122, 15`</td>
   <td>`0.4`</td>
   </tr>
   <tr>
   <td>Level_5c</td>
   <td>`271, 122.5, -5.5`</td>
   <td>`0.4`</td>
   </tr>
   <tr>
   <td>Level_5d</td>
   <td>`318, 121, -22`</td>
   <td>`0.9`</td>
   </tr>
   <tr>
   <td>Level_6a</td>
   <td>`363, 201, -52.5`</td>
   <td>`1.2`</td>
   </tr>
   <tr>
   <td>Level_6b</td>
   <td>`381, 201, 11`</td>
   <td>`0.4`</td>
   </tr>
   <tr>
   <td>Level_6c</td>
   <td>`389, 201, 47`</td>
   <td>`0.6`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Platforms-5.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

  </TabItem>
</Tabs>

###### Sea Stacks

샘플 자산 라이브러리에는 바다 스택 플랫폼의 기둥을 형성하기 위해 창의적으로 쌓을 수 있는 두 가지 유형의 바다 스택 암석 형성이 포함되어 있습니다:

- **SeaStackMesh** – 단단한 암석 형성을 포함합니다.
- **SeaStackCaveMesh** – 터널과 단단한 상단을 포함합니다.

두 플랫폼 유형 모두 `MeshPart` 객체입니다.

<GridContainer numColumns="2">
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Sea-Stacks.jpg.webp" alt="A comparison of a single sea stack next to multiple sea stacks that are stacked on top of each other." />
  </figure>
  <figure>
    <img width="100%" img src="../img/05_Roblox_tutorial/Completed-Sea-Stack.jpg.webp" alt="A demonstration of a SeaStackCaveMesh stacked on top of a PlatformB on top of a SeaStackMesh." />
  </figure>
</GridContainer>

<Tabs>
  <TabItem key = "1" label="Apply Your Own Sea Stacks">

바다 스택에 자산 라이브러리를 적용하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **SeaStackMesh**를 복사합니다.
2. **Platforms** 폴더에서 레벨 모델 중 하나에 **SeaStackMesh**를 붙여넣습니다.
3. **Home** 탭에서 **Move**, **Scale** 및 **Rotate** 도구를 사용하여 메쉬를 자리 표시 바다 스택의 길이에 맞게 위치, 크기 조정 및 회전시킵니다. 필요한 경우 **SeaStackMesh** 메쉬를 여러 개 사용합니다.

   <img src="../img/05_Roblox_tutorial/SeaStacks-3.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms visible with the polished assets, as well as the first sea stack. Other greybox sea stacks are transluscent in the distance." width="80%" />

4. 이 과정을 반복하여 각 바다 스택과 터널에 대해 더 많은 **SeaStackMesh** 및 **SeaStackCaveMesh** 메쉬를 추가하고 구성합니다.

   <img src="../img/05_Roblox_tutorial/SeaStacks-18.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and sea stacks visible with the polished assets." width="80%" />

5. 자리 표시 회색 상자 바다 스택 플랫폼을 삭제합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험 내 바다 스택을 정확히 재현하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **SeaStackMesh**를 복사합니다.
2. **Platforms** 폴더에서 **Level_3a** 모델에 **SeaStackMesh**를 세 번 붙여넣습니다.
3. **Properties** 창에서 메쉬를 다음 값으로 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`31, 31, 34`</td>
   <td>`31, 14, 15.5`</td>
   <td>`0, 72, 0`</td>
   </tr>
   <tr>
   <td>`32, 37, 34`</td>
   <td>`39, 11, 6`</td>
   <td>`0, 162, 0`</td>
   </tr>
   <tr>
   <td>`32, 36, 34`</td>
   <td>`31, 13, 7.5`</td>
   <td>`0, 68, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-3.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1 sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

4. 이 과정을 반복하여 다음 **SeaStackMesh** 자산을 **Level_3b** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`35, 47, 36`</td>
   <td>`80, 7, 4`</td>
   <td>`0, -18, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-4.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-2 sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

5. 다음 **SeaStackMesh** 자산을 **Level_3c** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`52, 69, 53`</td>
   <td>`90, -4, 48`</td>
   <td>`0, -18, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-5.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-3 sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

6. 다음 **SeaStackMesh** 자산을 **Level_4a** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`43, 49, 43`</td>
   <td>`103, 5, 48`</td>
   <td>`0, -119, 0`</td>
   </tr>
   <tr>
   <td>`37, 49, 38`</td>
   <td>`104, 41, 47`</td>
   <td>`0, -18, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-6.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-4a sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

7. 다음 자산을 **Level_4b** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Sea Stack 유형</th>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>SeaStackCaveMesh</td>
   <td>`54, 67, 53`</td>
   <td>`131, 88, 71`</td>
   <td>`0, -111, 0`</td>
   </tr>
   <tr>
   <td>SeaStackMesh</td>
   <td>`66, 85, 65`</td>
   <td>`133, 23, 71`</td>
   <td>`0, 87, 0`</td>
   </tr>
   <tr>
   <td>SeaStackMesh</td>
   <td>`46, 55, 47`</td>
   <td>`133, 136, 71`</td>
   <td>`0, -79, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-7.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-4a and 4b sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

8. 다음 **SeaStackMesh** 자산을 **Level_4c** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`63, 81, 62`</td>
   <td>`151, 25, 91`</td>
   <td>`0, -50, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-8.jpg.webp" alt="A side view of the sample laser tag experience with level 4c sea stacks visible with the polished assets." width="80%" />

9. 다음

 **SeaStackMesh** 자산을 **Level_4d** 모델에 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`35, 39, 35`</td>
   <td>`198, -4, 108`</td>
   <td>`0, -44, 0`</td>
   </tr>
   <tr>
   <td>`33, 36, 32`</td>
   <td>`199, 21, 108`</td>
   <td>`0, -119, 0`</td>
   </tr>
   <tr>
   <td>`27, 36, 28`</td>
   <td>`199, 48, 108`</td>
   <td>`0, -18, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SeaStacks-9.jpg.webp" alt="A side view of the sample laser tag experience with level 4c and 4d sea stacks visible with the polished assets." width="80%" />

10. 다음 **SeaStackMesh** 자산을 **Level_4e** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`57, 65, 57`</td>
      <td>`239, -14, 82`</td>
      <td>`0, -63, 0`</td>
      </tr>
      <tr>
      <td>`48, 65, 50`</td>
      <td>`239, 34, 81`</td>
      <td>`0, 39, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-10.jpg.webp" alt="A side view of the sample laser tag experience with level 4c-4e sea stacks visible with the polished assets." width="80%" />

11. 다음 **SeaStackMesh** 자산을 **Level_5a** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`56, 62, 54`</td>
      <td>`264, 11, 55`</td>
      <td>`0, 150, 0`</td>
      </tr>
      <tr>
      <td>`50, 57, 50`</td>
      <td>`263, 50, 57`</td>
      <td>`0, 75, 0`</td>
      </tr>
      <tr>
      <td>`43, 57, 44`</td>
      <td>`262, 92, 57`</td>
      <td>`0, 176, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-11.jpg.webp" alt="A side view of the sample laser tag experience with level 4c-5a sea stacks visible with the polished assets." width="80%" />

12. 다음 **SeaStackMesh** 자산을 **Level_5b** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`47, 36, 40`</td>
      <td>`245, -16, 15`</td>
      <td>`0, 0, 0`</td>
      </tr>
      <tr>
      <td>`38, 38, 41`</td>
      <td>`245, 11, 14`</td>
      <td>`0, 100, 0`</td>
      </tr>
      <tr>
      <td>`36, 38, 34`</td>
      <td>`243, 34, 15`</td>
      <td>`0, -164, 0`</td>
      </tr>
      <tr>
      <td>`31, 34, 30`</td>
      <td>`244, 62, 16`</td>
      <td>`0, -45, 0`</td>
      </tr>
      <tr>
      <td>`28, 32, 28`</td>
      <td>`244, 83, 15`</td>
      <td>`0, -120, 0`</td>
      </tr>
      <tr>
      <td>`24, 32, 24`</td>
      <td>`244, 106, 15`</td>
      <td>`0, -18, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-12.png.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-5b sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

13. 다음 **SeaStackMesh** 자산을 **Level_5c** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`45, 34, 38`</td>
      <td>`270, -8, -6`</td>
      <td>`0, 180, 0`</td>
      </tr>
      <tr>
      <td>`36, 35, 38`</td>
      <td>`270, 17, -5`</td>
      <td>`0, -80, 0`</td>
      </tr>
      <tr>
      <td>`34, 35, 32`</td>
      <td>`272, 40, -5`</td>
      <td>`0, 16, 0`</td>
      </tr>
      <tr>
      <td>`29, 32, 29`</td>
      <td>`271, 65, -7`</td>
      <td>`0, 136, 0`</td>
      </tr>
      <tr>
      <td>`26, 30, 26`</td>
      <td>`271, 86, -6`</td>
      <td>`0, 61, 0`</td>
      </tr>
      <tr>
      <td>`22, 30, 23`</td>
      <td>`270, 108, -6`</td>
      <td>`0, 162, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-13.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-5c sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

14. 다음 **SeaStackMesh** 자산을 **Level_5d** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`65, 71, 63`</td>
      <td>`315, -5, -27`</td>
      <td>`0, -161, 0`</td>
      </tr>
      <tr>
      <td>`58, 66, 58`</td>
      <td>`315, 39, -25`</td>
      <td>`0, 124, 0`</td>
      </tr>
      <tr>
      <td>`50, 66, 51`</td>
      <td>`315, 89, -24`</td>
      <td>`0, -134, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-14.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-5d sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

15. 다음 **SeaStackMesh** 자산을 **Level_6a** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`94, 104, 92`</td>
      <td>`358, 32, -56`</td>
      <td>`0, -123, 0`</td>
      </tr>
      <tr>
      <td>`85, 96, 84`</td>
      <td>`360, 97, -54`</td>
      <td>`0, 162, 0`</td>
      </tr>
      <tr>
      <td>`72, 71, 74`</td>
      <td>`361, 165, -52`</td>
      <td>`0, -79, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-15.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-6a sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

16. 다음 **SeaStackMesh** 자산을 **Level_6b** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`44, 65, 47`</td>
      <td>`380, 17, 9`</td>
      <td>`0, -143, 0`</td>
      </tr>
      <tr>
      <td>`46, 44, 39`</td>
      <td>`380, 61, 11`</td>
      <td>`0, -78, 0`</td>
      </tr>
      <tr>
      <td>`37, 37, 40`</td>
      <td>`381, 92, 11`</td>
      <td>`0, 22, 0`</td>
      </tr>
      <tr>
      <td>`35, 37, 33`</td>
      <td>`381, 115, 10`</td>
      <td>`0, 118, 0`</td>
      </tr>
      <tr>
      <td>`30, 33, 30`</td>
      <td>`379, 141, 10`</td>
      <td>`0, -123, 0`</td>
      </tr>
      <tr>
      <td>`27, 31, 27`</td>
      <td>`380, 162, 10`</td>
      <td>`0, 162, 0`</td>
      </tr>
      <tr>
      <td>`23, 31, 24`</td>
      <td>`380, 185, 11`</td>
      <td>`0, -96, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-16.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-6b sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

17. 다음 **SeaStackMesh** 자산을 **Level_6c** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`68, 52, 57`</td>
      <td>`387, 3, 48`</td>
      <td>`0, -4, 0`</td>
      </tr>
      <tr>
      <td>`54, 54, 58`</td>
      <td>`388, 41, 47`</td>
      <td>`0, 96, 0`</td>
      </tr>
      <tr>
      <td>`52, 54, 48`</td>
      <td>`385, 75, 47`</td>
      <td>`0, -168, 0`</td>
      </tr>
      <tr>
      <td>`44, 49, 43`</td>
      <td>`385, 114, 49`</td>
      <td>`0, -49, 0`</td>
      </tr>
      <tr>
      <td>`40, 45, 40`</td>
      <td>`386, 145, 48`</td>
      <td>`0, -124, 0`</td>
      </tr>
      <tr>
      <td>`34, 45, 35`</td>
      <td>`387, 178, 48`</td>
      <td>`0, -22, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-17.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-6c sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

18. 다음 **SeaStackMesh** 자산을 **Level_7a** 모델에 추가하고 구성합니다:

      <table>
      <thead>
      <tr>
      <th>Size</th>
      <th>CFrame.Position</th>
      <th>CFrame.Orientation</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>`96, 98, 102`</td>
      <td>`406, 19, 82`</td>
      <td>`0, -41, 0`</td>
      </tr>
      <tr>
      <td>`92, 98, 84`</td>
      <td>`407, 81, 82`</td>
      <td>`0, -19, 0`</td>
      </tr>
      <tr>
      <td>`81, 90, 79`</td>
      <td>`407, 152, 80`</td>
      <td>`0, 90, 0`</td>
      </tr>
      <tr>
      <td>`73, 83, 73`</td>
      <td>`404, 208, 80`</td>
      <td>`0, 15, 0`</td>
      </tr>
      <tr>
      <td>`62, 83, 64`</td>
      <td>`403, 270, 79`</td>
      <td>`0, 116, 0`</td>
      </tr>
      </tbody>
      </table>

      <img src="../img/05_Roblox_tutorial/SeaStacks-18.jpg.webp" alt="A view of the sample laser tag experience with all of the platforms and level 1-7a sea stacks visible with the polished assets. Other greybox sea stacks are transluscent in the distance." width="80%" />

19. 자리 표시 회색 상자 바다 스택 플랫폼을 삭제합니다.

  </TabItem>
</Tabs>

###### Coins

샘플 자산 라이브러리에는 `MeshPart` 객체와 하위 `SurfaceAppearance` 객체가 있는 단일 **Coin** 자산이 포함되어 있습니다. `SurfaceAppearance` 객체는 동전에 반짝이는 금속 효과를 만들어 더 현실적이고 플레이어가 수집하기 더 매력적으로 만듭니다.

이 객체를 초기 자리 표시 동전을 설정한 위치에 배치하거나 플레이어에게 더 유용하게 생각되는 위치로 위치와 방향 값을 수정할 수 있습니다.

<img src="../img/05_Roblox_tutorial/Final-Coin.jpg.webp" alt="A close up view of a shiny gold coin with a Roblox icon in the middle. The coin floats over a grassy path of island." width="80%" />

<Tabs>
  <TabItem key = "1" label="Apply Your Own Coins">

동전에 자산 라이브러리를 적용하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **Coin**을 복사합니다.
1. **Platforms** 폴더에서 **Coins** 폴더에 **Coin**을

 붙여넣습니다.
1. **Home** 탭에서 **Move** 및 **Rotate** 도구를 사용하여 메쉬를 첫 번째 자리 표시 동전의 구성과 동일한 구성으로 위치시키고 회전시킵니다.
1. 이 과정을 반복하여 초기 동전 자리 표시 객체를 설정한 위치에 **coin** 자산을 추가하고 구성합니다.

   <img src="../img/05_Roblox_tutorial/Coins-Final.jpg.webp" alt="A view of shiny gold coins hovering over each level of sea stack platform." width="80%" />

1. 자리 표시 동전을 삭제합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험 내 동전을 정확히 재현하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **Coin**을 복사합니다.
2. **Platforms** 폴더에서 **Coins** 폴더에 **Coin**을 붙여넣습니다.
3. **Properties** 창에서,
   1. **CFrame.Position**을 **-121, 3, 6**으로 설정합니다.
   1. **CFrame.Orientation**을 **0, -105, 0**으로 설정합니다.
4. 이 과정을 반복하여 초기 동전 자리 표시 객체를 설정한 위치에 다음 **coin** 자산을 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`-121, 3, 6`</td>
   <td>`0, -105, 0`</td>
   </tr>
   <tr>
   <td>`-107, 3, 10`</td>
   <td>`0, -105, 0`</td>
   </tr>
   <tr>
   <td>`-104, 3, 35`</td>
   <td>`0, 120, 0`</td>
   </tr>
   <tr>
   <td>`-86, 3, 61`</td>
   <td>`0, 30, 0`</td>
   </tr>
   <tr>
   <td>`-101, 3, -12`</td>
   <td>`0, -15, 0`</td>
   </tr>
   <tr>
   <td>`-22, 6, -39`</td>
   <td>`0, 120, 0`</td>
   </tr>
   <tr>
   <td>`-48, 6, -26`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-65, 6, -6`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-74, 6, 19`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-67, 6, 46`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-38, 14, 28`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-8, 14, 8`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`-3, 14, 34`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`35, 33, 9`</td>
   <td>`0, -105, 0`</td>
   </tr>
   <tr>
   <td>`59, 39, 6`</td>
   <td>`0, 90, 0`</td>
   </tr>
   <tr>
   <td>`78, 33, 4`</td>
   <td>`0, -75, 0`</td>
   </tr>
   <tr>
   <td>`83, 39, 22`</td>
   <td>`0, -165, 0`</td>
   </tr>
   <tr>
   <td>`113, 70, 56`</td>
   <td>`0, -135, 0`</td>
   </tr>
   <tr>
   <td>`134, 70, 76`</td>
   <td>`0, -135, 0`</td>
   </tr>
   <tr>
   <td>`175, 70, 103`</td>
   <td>`0, 75, 0`</td>
   </tr>
   <tr>
   <td>`197, 70, 107`</td>
   <td>`0, 105, 0`</td>
   </tr>
   <tr>
   <td>`214, 81, 95`</td>
   <td>`0, 120, 0`</td>
   </tr>
   <tr>
   <td>`235, 99, 78`</td>
   <td>`0, 135, 0`</td>
   </tr>
   <tr>
   <td>`258, 125, 54`</td>
   <td>`0, 135, 0`</td>
   </tr>
   <tr>
   <td>`251, 132, 11`</td>
   <td>`0, 135, 0`</td>
   </tr>
   <tr>
   <td>`260, 140, 4`</td>
   <td>`0, 135, 0`</td>
   </tr>
   <tr>
   <td>`270, 132, -5`</td>
   <td>`0, 135, 0`</td>
   </tr>
   <tr>
   <td>`312, 162, -19`</td>
   <td>`0, 105, 0`</td>
   </tr>
   <tr>
   <td>`360, 206, -40`</td>
   <td>`0, 69, 0`</td>
   </tr>
   <tr>
   <td>`377, 260, -4`</td>
   <td>`0, -145, 0`</td>
   </tr>
   <tr>
   <td>`380, 206, 13`</td>
   <td>`0, 12, 0`</td>
   </tr>
   <tr>
   <td>`386, 260, 27`</td>
   <td>`0, -145, 0`</td>
   </tr>
   <tr>
   <td>`391, 206, 45`</td>
   <td>`0, 12, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Coins-Final.jpg.webp" alt="A view of shiny gold coins hovering over each level of sea stack platform." width="80%" />

5. 자리 표시 동전을 삭제합니다.

  </TabItem>
</Tabs>

###### Mountains

샘플 자산 라이브러리에는 단일 **MountainMesh** 자산이 포함되어 있어 세계의 배경을 장식하고 물 지형의 가장자리를 숨기며 바다 스택 플랫폼 주위의 환경을 둘러싸는 데 사용할 수 있습니다. 개별 산을 회전하고 크기를 조정하여 자산의 재료가 이웃 산과 섞이도록 할 수 있습니다. 이 기술은 전체 산맥이 단일 반복 메쉬라는 것을 플레이어가 감지하는 능력을 효과적으로 줄여줍니다.

<img src="../img/05_Roblox_tutorial/Mountain-Meshes-Stacked.jpg.webp" alt="Several mountain meshes with different scales and rotation values overlap each other's edges to look like a mountain range. Each mesh has a light blue outline." width="80%" />

<Tabs>
  <TabItem key = "1" label="Apply Your Own Mountains">

산에 자산 라이브러리를 적용하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **MountainMesh**를 복사합니다.
1. **Platforms** 폴더에서 **Mountains** 폴더에 **MountainMesh**를 붙여넣습니다.
1. **Home** 탭에서 **Move**, **Scale** 및 **Rotate** 도구를 사용하여 물 지형의 경계선을 따라 메쉬를 위치시키고, 크기를 조정하며 회전시킵니다.
1. 이 과정을 반복하여 물 지형의 경계선이 덮일 때까지 다양한 크

기와 회전의 산을 추가하고 구성합니다.

   <img src="../img/05_Roblox_tutorial/Mountains-Final.jpg.webp" alt="A view of the polished sea stacks, platform, and coins, with a mountain range in the background." width="80%" />

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Island Jump - Final](https://www.roblox.com/games/14238807008/Island-Jump-Completed-Sample) 경험 내 산을 정확히 재현하려면:

1. **Explorer** 창에서 자산 라이브러리로 이동하여 **MountainMesh**를 복사합니다.
2. **Platforms** 폴더에서 **Mountains** 폴더에 **MountainMesh**를 붙여넣습니다.
3. **Properties** 창에서,
   1. **Size**를 **2048, 334, 2048**로 설정합니다.
   2. **CFrame.Position**을 **-1243, 115, -1402**로 설정합니다.
   3. **CFrame.Orientation**을 **0, 46, 0**로 설정합니다.
4. 이 과정을 반복하여 물 지형의 경계선을 따라 다음 산 자산을 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>Size</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>`2048, 212, 2048`</td>
   <td>`-326, 230, -1614`</td>
   <td>`-15, -155, 0`</td>
   </tr>
   <tr>
   <td>`2048, 416, 1871`</td>
   <td>`434, 160, -1543`</td>
   <td>`0, -2, 0`</td>
   </tr>
   <tr>
   <td>`2048, 400, 2048`</td>
   <td>`1200, 147, -1534`</td>
   <td>`-15, -155, 0`</td>
   </tr>
   <tr>
   <td>`2048, 540, 1488`</td>
   <td>`1726, 220, -1139`</td>
   <td>`0, -95, 0`</td>
   </tr>
   <tr>
   <td>`2044, 442, 2044`</td>
   <td>`2344, 174, -413`</td>
   <td>`0, 5, 0`</td>
   </tr>
   <tr>
   <td>`2048, 458, 2048`</td>
   <td>`2267, 157, 1084`</td>
   <td>`0, -81, 0`</td>
   </tr>
   <tr>
   <td>`2048, 678, 2048`</td>
   <td>`1662, 221, 1804`</td>
   <td>`0, 9, 0`</td>
   </tr>
   <tr>
   <td>`2043, 352, 1467`</td>
   <td>`1025, 147, 2462`</td>
   <td>`0, 54, 0`</td>
   </tr>
   <tr>
   <td>`1980, 531, 1742`</td>
   <td>`361, 180, 2119`</td>
   <td>`0, 21, 0`</td>
   </tr>
   <tr>
   <td>`2048, 415, 2048`</td>
   <td>`-580, 160, 1961`</td>
   <td>`0, -122, 0`</td>
   </tr>
   <tr>
   <td>`2048, 415, 2048`</td>
   <td>`-900, 160, 1652`</td>
   <td>`0, 24, 0`</td>
   </tr>
   <tr>
   <td>`1321, 403, 1321`</td>
   <td>`-1303, 133, 770`</td>
   <td>`0, 55, 0`</td>
   </tr>
   <tr>
   <td>`2048, 335, 2048`</td>
   <td>`-1653, 114, 161`</td>
   <td>`0, -20, 0`</td>
   </tr>
   <tr>
   <td>`2048, 249, 2048`</td>
   <td>`-1928, 79, -674`</td>
   <td>`0, 24, 0`</td>
   </tr>
   <tr>
   <td>`2048, 450, 2048`</td>
   <td>`-1426, 73, -895`</td>
   <td>`0, -20, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Mountains-Final.jpg.webp" alt="A view of the polished sea stacks, platform, and coins, with a mountain range in the background." width="80%" />

  </TabItem>
</Tabs>

##### Playtest

자산 라이브러리를 적용하고 환경을 구성한 후에는 최종 자산의 레이아웃에서 발생한 변동이 플레이어의 게임 완료 능력에 영향을 미치지 않는지 확인하기 위해 경험을 플레이테스트해야 합니다.

경험을 플레이테스트하려면:

1. 메뉴 바에서 **Play** 버튼을 클릭합니다. Studio가 플레이테스트 모드로 전환됩니다.

   <img src="../img/05_Roblox_tutorial/Quick-Access-Toolbar-Play.png.webp" alt="Studio's Home tab with the Play button highlighted in the menu bar." width="716" />

1. 경험을 플레이하고 스택 상단의 플레어에 도달해 보세요.
1. 완료되면 메뉴 바로 이동하여 **Stop** 버튼을 클릭합니다. Studio가 플레이테스트 모드에서 종료됩니다.

   <img src="../img/05_Roblox_tutorial/Quick-Access-Toolbar-Stop.png.webp" alt="Studio's Home tab with the Stop button highlighted in the menu bar." width="716" />

Core Curriculum을 완료한 것을 축하드립니다! 이제 간단한 경험을 처음부터 끝까지 만드는 경험을 쌓았으므로 새로운 게임 플레이 기능이나 추가 레벨로 프로젝트를 확장하거나 Studio의 추가 [기능](../../../platform.md)을 탐색하거나 고품질 레이저 태그 환경을 만드는 방법을 가르쳐주는 [환경 예술 커리큘럼](../../environmental-art/index.md)과 같은 추가 튜토리얼 커리큘럼을 따를 수 있습니다. 창작을 즐기세요!

<Alert severity="info">
Core Curriculum을 따르는 과정에 대한 질문, 우려 사항 또는 추가 피드백이 있으시면 [Core Curriculum Q&A](https://devforum.roblox.com/t/feedback-on-core-curriculum/2592219)에 댓글을 남겨 주세요.
</Alert>

---
## Environmental Art Curriculum

**Environmental Art**은 게임플레이 요구 사항을 구현하고 사용자 경험에 몰입하게 하며 세계 자체에 대한 맥락 정보를 제공하는 3D 환경을 생성하고 구성하는 분야입니다.

여러분은 단계별 프로세스와 레벨 디자인, 자산 개발, 메모리 및 성능 최적화를 위한 최선의 실천을 통해 1인칭 슈팅 레이저 태그 경험을 위한 [고품질 환경](https://www.roblox.com/games/14447845297/Environment-Art-Optimizing)을 재현하는 방법을 배우게 됩니다. 이를 통해 자신만의 경험에 구현할 수 있습니다.

이 과정은 Roblox Studio에서 일반적인 빌딩 개념과 도구에 익숙한 독자를 대상으로 합니다. 환경을 만드는 방법을 배우는 데 도움이 필요하다면 [핵심 커리큘럼](#core)을 시도해 보세요.

### Chapter 1 - Greybox Your Environment

**그레이박싱 환경**, 매싱 아웃 또는 환경 블로킹이라고도 불리는 이 과정은 자산을 다듬기 전에 사용자가 게임플레이를 어떻게 경험할지 알아내기 위해 3D 공간에 간단한 형태를 추가하는 과정입니다. 이 과정은 플레이 가능한 영역의 레이아웃에서 발생할 수 있는 문제를 발견하는 데 중요합니다. 예를 들어, 이동하기 어려운 지역, 특정 관점에서의 불공평한 이점, 사용자 캐릭터에 비해 비율이 맞지 않는 자산 등이 있습니다.

[Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) `.rbxl` 파일을 참고하여 이 섹션에서는 팀 기반 1인칭 레이저 태그 슈터 경험을 위한 표준 세 개의 레인 맵 레이아웃을 그레이박싱하는 방법을 단계별로 설명합니다. 이 과정에는 다음과 같은 내용이 포함됩니다:

- 다양한 플레이 스타일을 위한 전략적 전투를 유도하는 플레이 가능한 영역 생성.
- 사용자의 위치와 방향을 알려주는 플레이스홀더 재료 적용.
- 레이아웃 테스트를 통해 재미있고 플레이할 수 있는 문제를 포함하지 않는지 확인.

이 섹션을 완료한 후에는 그레이박스 환경을 대체하거나 변환할 고품질 자산을 개발하고 게임 디자인 요구 사항을 충족하는 방법을 배우게 됩니다.

<img src="../img/05_Roblox_tutorial/PlaceholderMaterials.jpg.webp" alt="An angled top-down view of the final greybox environment with placeholder materials to mark unique sections of the map." width="100%"/>

#### 세 개의 레인 맵 레이아웃

**세 개의 레인 맵 레이아웃**은 맵의 반대쪽에 각 팀의 스폰 존이 있는 1인칭 슈터 맵 레이아웃으로, 각 팀이 스폰 존으로 이동할 수 있는 세 개의 주요 레인과 하나의 주요 레인에서 다른 레인으로 이동할 수 있는 교차 레인이 포함됩니다. 이 유형의 맵 레이아웃은 사용자가 매치에 참여하자마자 전투 구역에 빠르게 진입하게 하며, 사용자가 선택하는 주요 레인에 따라 다양한 플레이 스타일을 허용하기 때문에 1인칭 슈터 경험에 일반적으로 사용됩니다.

다음 섹션에서는 세 개의 레인 맵 레이아웃의 각 구성 요소를 설명하며, 각 구성 요소가 1인칭 슈터 경험 내에서 의도적인 게임플레이 상호작용을 생성하는 방법을 고려합니다.

##### 스폰 존

**스폰 존**은 사용자가 매치 시작 시 팀에 합류하거나 체력이 0이 된 후 다시 게임에 합류하는 맵의 영역입니다. 최소한 각 팀은 사용자가 경험에 처음 합류할 때 중앙 스폰 존을 가져야 합니다. 많은 개발자는 사용자가 매치 시작 전에 경험을 탐색할 시간을 주기 위해 이러한 중앙 스폰 존을 맵의 반대쪽 끝에 배치합니다.

<img src="../img/05_Roblox_tutorial/ThreeLaneLayout-SpawnZones.jpg" alt="A top-down view of the baseplate with each team's spawn zone highlighted on opposite sides of the map." width="100%"/>

또한, 많은 팀 기반 1인칭 슈터 경험에는 사용자가 체력이 0이 된 후 무작위로 다시 스폰할 수 있는 맵 전체에 스폰 존이 포함됩니다. 이러한 분산된 스폰 존의 배치는 특히 전투가 많은 지역 근처에 스폰 존을 배치할 때 경험의 난이도를 크게 증가시킬 수 있습니다. 게임플레이를 간단하게 유지하기 위해 샘플 레이저 태그 그레이박스 환경에는 각 팀에 하나의 중앙 스폰 존만 포함됩니다.

##### 주요 레인

**주요 레인**은 스폰 존에서 다른 스폰 존으로 이어지는 맵의 경로입니다. 세 개의 레인 맵 레이아웃에는 세 개의 주요 레인이 포함되며, 개발자는 경험의 전체 환경적 맥락에 따라 이를 개념화합니다. 예를 들어, 샘플 레이저 태그 맵에는 실내 및 실외 환경이 모두 있기 때문에 주요 레인의 이름은 다음과 같습니다:

- **실내** - 건물 입구에서 가장 먼 내부 레인.
- **중앙** - 내부 및 외부 주요 레인 사이에 있는 레인.
- **외부** - 건물 입구와 가장 가까운 레인으로, 부분적으로 실내와 실외에 있습니다.

대부분의 세 개의 레인 맵 레이아웃을 사용하는 1인칭 슈터 경험에서, 중앙 주요 레인은 실내 또는 외부 주요 레인 모두에서 공격을 받을 수 있기 때문에 맵의 가장 많은 전투가 발생하는 지역과 교차합니다. 반면, 내부 또는 외부 주요 레인을 이동하는 사용자는 중앙 주요 레인에서만 공격을 받을 수 있습니다.

<img src="../img/05_Roblox_tutorial/ThreeLaneLayout-PrimaryLanes.jpg" alt="A top-down view of the baseplate with three primary lanes highlighted between each team's spawn zone on opposite sides of the map." width="100%"/>

##### 교차 레인

**교차 레인**은 모든 주요 레인과 교차하며, 내부 주요 레인에서 외부 주요 레인까지 이어지는 경로입니다. 사용자는 이 경로를 사용하여 한 주요 레인에서 다른 주요 레인으로 이동할 수 있으며, 일반적으로 최소한의 장애물을 포함하여 사용자가 적의 공격을 피할 수 있도록 도와줍니다. 이는 장애물이 없는 구역이 사용자가 너무 오랫동안 한 장소에 머물지 않도록 장려하는 전이 공간을 생성하기 때문입니다.

<img src="../img/05_Roblox_tutorial/ThreeLaneLayout-CrossLanes.jpg" alt="A top-down view of the baseplate with three primary lanes between each team's spawn zone on opposite sides of the map, as well as five cross lanes that intersect with the primary lanes." width="100%"/>

중앙 주요 레인과 교차하는 교차 레인의 교차 지점 또는 **전투 포켓**은 내부 또는 외부 레인을 이동하는 사용자가 중앙 레인에 접근하고 쏠 수 있기 때문에 가장 많은 전투가 발생합니다. 중앙 레인을 이동하는 사용자는 내부 또는 외부 레인 방향으로 쏠 수 있습니다.

<img src="../img/05_Roblox_tutorial/ThreeLaneLayout-IntersectingPoints.jpg" alt="A top-down view of the baseplate with three primary lanes between each team's spawn zone on opposite sides of the map, as well as five cross lanes that intersect with the primary lanes. The intersections between the primary and cross lanes are highlighted." width="100%"/>

이러한 전투 포켓을 고려하여 세 개의 레인 맵 레이아웃을 구축하면 스폰 존에서의 거리를 분할하고 사용자가 서로 상호작용해야 하는 의도적인 공간을 생성할 수 있습니다. 이는 사용자가 빠른 게임플레이에 참여하고 주요 레인 간을 교차 레인을 사용하여 이동하면서 맵을 빨리 익히도록 장려합니다.

#### 플레이 가능한 영역 만들기

세 개의 레인 맵 레이아웃에 익숙해졌으니 이제 샘플 레이저 태그 그레이박스 환경의 플레이 가능한 영역을 만드는 방법을 배워보겠습니다. [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) `.rbxl` 파일의 지오메트리를 정확히 재현하는 이러한 지침을 따라가면 두 개의 스폰 존, 세 개의 주요 레인, 다섯 개의 교차 레인이 맵의 중간을 가로질러 대칭적으로 배치된 모습을 볼 수 있습니다.

<img src="../img/05_Roblox_tutorial/CreatingPlayableAreas-Intro1.jpg" alt="A top-down view of the final greybox geometry with three primary lanes between each team's spawn zone on opposite sides of the map, as well as five cross lanes that intersect with the primary lanes. The intersections between the primary and cross lanes are highlighted." width="100%"/>

<Alert severity="info">
    다음 지침은 두 가지 다른 지침 경로를 제공합니다: 고유한 레이저 태그 환경을 나타내는 파트를 삽입하거나 샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 그레이박스 환경을 정확히 재현하는 방식으로 파트를 삽입할 수 있습니다.
</Alert>

지오메트리를 경험의 사양에 맞게 조정하는 경우, 샘플 파일은 모든 문과 복도를 최소 10 스터드 너비로 유지하며, 모든 벽을 최소 10 스터드 높이로 유지합니다. 이러한 매개변수는 두 사용자가 복도와 문을 동시에 통과할 수 있도록 하고, Roblox의 기본 점프 높이인 5 스터드로 벽을 뛰어넘을 수 없도록 하며, 카메라가

 지오메트리와 간섭하지 않고 맵을 안전하게 이동할 수 있도록 합니다.

<img src="../img/05_Roblox_tutorial/CreatingPlayableAreas-Intro2.png" alt="In a doorway, two lizard avatars are stacked on top of each other on the left, and two blocky avatars are stacked on top of each other on the right. This demonstrates that only two characters can pass each other in a doorway, and they cannot jump higher than the walls." width="60%"/>

##### 바닥 지오메트리

레이저 태그 그레이박스 환경을 만드는 첫 번째 단계는 각 바닥의 지오메트리를 생성하는 것입니다:

- **메인 플로어** – 한 스폰 존에서 다른 스폰 존까지 이어집니다.
- **메자닌 플로어** – 중간 전투 포켓의 절반을 차지하며, 고도를 높입니다.
- **실외 플로어** – 실외 공간을 차지하며, 고도를 낮춥니다.

경험을 위한 각 바닥의 지오메트리를 시각화하는 데 도움이 되도록, 메인 플로어는 노란색, 메자닌 플로어는 빨간색, 실외 플로어는 파란색으로 표시된 다음 이미지를 참고하세요.

<img src="../img/05_Roblox_tutorial/Floor-Intro.jpg" alt="A top-down view of the final greybox environment with placeholder materials to mark the main, mezzanine, and outdoor floors." width="100%"/>

경험에 피크와 밸리를 포함하는 공간을 갖는 것이 중요한 이유는 수평 이동 외에도 시야선과 교전 거리를 제어할 수 있기 때문입니다. 예를 들어, 모든 플레이 가능한 공간이 고도 변화가 없는 단일 바닥으로 이루어져 있다면, 벽이 없는 한 모든 사용자가 서로 상호작용할 수 있어, 다른 사용자가 보지 않는다는 전략 외에 사용자가 개발할 수 있는 전략이 거의 없게 됩니다. 그러나 피크와 밸리가 있는 경우, 사용자가 서로를 볼 수 있는 위치를 결정할 수 있습니다.

또한, 고도의 상승은 물리적 및 감정적인 상승감을 제공하여 높은 지형에 있는 사용자가 전장을 조감하여 다음 이동 경로를 더 잘 파악할 수 있게 합니다. 이동할 준비가 되면, 고도의 하강은 물리적 및 감정적인 하강감을 제공하여 사용자가 적의 시야를 피하면서 빠르게 목표를 달성하도록 압박합니다.

<Tabs>
  <TabItem key = "1" label="Create Your Own">

자신만의 바닥 지오메트리를 생성하려면:

1. **베이스플레이트** 템플릿으로 Roblox Studio를 엽니다.
1. 메뉴 모음에서 **모델** 탭으로 이동한 다음 **그리드에 맞추기** 섹션에서,
   1. **회전**을 **90**으로 설정합니다.
   1. **이동**을 **5 스터드**로 설정합니다. 이를 통해 모든 그레이박스 지오메트리를 서로 5 스터드 간격으로 배치할 수 있습니다.

   <img src="../img/05_Roblox_tutorial/SnapToGrid.jpg" alt="Studio's Model tab with the Snap to Grid settings highlighted." width="60%"/>

1. **블록** 파트를 사용하여 건물의 **메인 플로어**를 위해 좌우 대칭 표면을 만듭니다. 이 지오메트리는 플레이 가능한 실내의 길이를 나타내며, 그 대칭은 맵의 중심을 나타냅니다.

   <img src="../img/05_Roblox_tutorial/GeneralFloor-1.jpg" alt="An angled top-down view of the main floor greybox geometry highlighted in yellow." width="100%"/>

1. **블록** 파트를 사용하여 건물의 **메자닌 플로어**를 위해 좌우 대칭 표면을 만듭니다. 이 지오메트리는 맵의 가장 높은 지형을 나타냅니다.

   <img src="../img/05_Roblox_tutorial/Floor-3.jpg" alt="An angled top-down view of both the main and mezzanine floors. The mezzanine floor greybox geometry is highlighted in yellow." width="100%"/>

1. **웨지** 파트를 사용하여 메인 플로어와 메자닌 플로어 사이의 **고도 상승**을 만듭니다. 이 지오메트리는 내부 주요 레인 또는 맵 중앙의 교차 레인을 이동하는 플레이어의 시야를 차단합니다.

   <img src="../img/05_Roblox_tutorial/Floor-4.jpg" alt="An angled top-down view of both the main, mezzanine floor, and rise in elevation parts. The rise in elevation greybox geometry is highlighted in yellow." width="100%"/>

1. **웨지** 파트를 사용하여 메인 플로어와 실외 플로어 사이의 **고도 하강**을 만듭니다. 이 지오메트리는 외부 주요 레인이며, 맵의 가장 낮은 지형으로 내려갑니다.

   <img src="../img/05_Roblox_tutorial/Floor-5.jpg" alt="An angled top-down view of both the main, mezzanine floor, and rise and drop in elevation parts. The drop in elevation greybox geometry is highlighted in yellow." width="100%"/>

1. 모든 파트를 고정합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 바닥 지오메트리를 정확히 재현하려면:

1. **베이스플레이트** 템플릿으로 Roblox Studio를 엽니다.
1. 메뉴 모음에서 **모델** 탭으로 이동한 다음 **그리드에 맞추기** 섹션에서,
   1. **회전**을 **90**으로 설정합니다.
   1. **이동**을 **5 스터드**로 설정합니다. 이를 통해 모든 그레이박스 지오메트리를 서로 5 스터드 간격으로 배치할 수 있습니다.

   <img src="../img/05_Roblox_tutorial/SnapToGrid.jpg" alt="Studio's Model tab with the Snap to Grid settings highlighted." width="60%"/>

1. **블록** 파트를 추가하고 **메인 플로어**의 왼쪽 표면을 구성합니다. 이 프로세스를 사용하여 모든 플레이 가능한 영역을 만들 수 있습니다.

   1. 메뉴 모음에서 **모델** 탭을 선택합니다.
   1. **파츠** 섹션에서 드롭다운 화살표를 클릭하고 **블록**을 선택합니다. 블록 파트가 뷰포트에 표시됩니다.

      <img src="../img/05_Roblox_tutorial/Model-Tab-Part-Tools.png.webp" width="660" alt="Studio's Model tab with the Part button and Part Type Picker elements highlighted." />

   1. **탐색기** 창에서 블록을 선택한 다음 **속성** 창에서,
      1. **크기**를 **105, 1, 185**로 설정합니다.
      1. **CFrame.Position**을 **-77.5, 4.5, 252.5**로 설정합니다.

   <img src="../img/05_Roblox_tutorial/Floor-1.jpg.webp" alt="An angled top-down view of the left-side of the main floor greybox geometry highlighted in yellow." width="100%"/>

1. **메인 플로어**의 나머지 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>오른쪽 바닥</td>
   <td>`105, 1, 185`</td>
   <td>`-77.5, 4.5, 67.5`</td>
   </tr>
   <tr>
   <td>중앙 왼쪽 바닥</td>
   <td>`20, 10, 50`</td>
   <td>`-15, 0, 185`</td>
   </tr>
   <tr>
   <td>중앙 오른쪽 바닥</td>
   <td>`20, 10, 50`</td>
   <td>`-15, 0, 135`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Floor-2.jpg.webp" alt="An angled top-down view of the main floor geometry. The right-side and middle portion of the main floor greybox geometry is highlighted in yellow." width="100%"/>

1. **메자닌 플로어**를 위한 **블록** 파

트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 바닥</td>
   <td>`70, 5, 35`</td>
   <td>`-110, 7.5, 177.5`</td>
   </tr>
   <tr>
   <td>오른쪽 바닥</td>
   <td>`70, 5, 35`</td>
   <td>`-110, 7.5, 142.5`</td>
   </tr>
   <tr>
   <td>왼쪽 가장자리</td>
   <td>`10, 5, 10`</td>
   <td>`-70, 7.5, 165`</td>
   </tr>
   <tr>
   <td>오른쪽 가장자리</td>
   <td>`10, 5, 10`</td>
   <td>`-70, 7.5, 155`</td>
   </tr>
   <tr>
   <td>가장자리 벽</td>
   <td>`1, 3, 20`</td>
   <td>`-65.5, 11.5, 160`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Floor-3.jpg" alt="An angled top-down view of both the main and mezzanine floors. The mezzanine floor greybox geometry is highlighted in yellow." width="100%"/>

1. **메인 플로어**와 **메자닌 플로어** 사이의 **고도 상승**을 위한 **웨지** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   <th>CFrame.Orientation</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 고도</td>
   <td>`15, 5, 10`</td>
   <td>`-102.5, 7.5, 200`</td>
   <td>`0, 180, 0`</td>
   </tr>
   <tr>
   <td>오른쪽 고도</td>
   <td>`15, 5, 10`</td>
   <td>`-102.5, 7.5, 120`</td>
   <td>`0, 0, 0`</td>
   </tr>
   <tr>
   <td>중앙 왼쪽 고도</td>
   <td>`15, 5, 10`</td>
   <td>`-70, 7.5, 177.5`</td>
   <td>`0, -90, 0`</td>
   </tr>
   <tr>
   <td>중앙 오른쪽 고도</td>
   <td>`15, 5, 10`</td>
   <td>`-70, 7.5, 142.5`</td>
   <td>`0, -90, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Floor-4.jpg" alt="An angled top-down view of both the main, mezzanine floor, and rise in elevation parts. The rise in elevation greybox geometry is highlighted in yellow." width="100%"/>

1. **메인 플로어**와 **실외 플로어** 사이의 **고도 하강**을 위한 **웨지** 파트를 추가하고 구성합니다. **크기**는 `270, 11, 45`, **CFrame.Position**은 `-2.5, -0.5, 160`, **CFrame.Orientation**은 `0, -90, 0`입니다.

   <img src="../img/05_Roblox_tutorial/Floor-5.jpg" alt="An angled top-down view of both the main, mezzanine floor, and rise and drop in elevation parts. The drop in elevation greybox geometry is highlighted in yellow." width="100%"/>

1. 모든 바닥 파트를 고정합니다.

  </TabItem>
</Tabs>

##### 주변 벽 지오메트리

레이저 태그 그레이박스 환경을 만드는 두 번째 단계는 건물의 주변 벽 지오메트리를 만드는 것입니다. 이는 경험의 실내 게임플레이를 위한 경계를 제공하고, 사용자가 어디로 가서 서로 상호작용할 수 있는지 안내합니다.

경험을 위해 만드는 건물의 주변 벽 지오메트리를 시각화하는 데 도움이 되도록 다음 이미지를 참고하세요. 노란색으로 표시되어 있습니다.

<img src="../img/05_Roblox_tutorial/Perimeter-Intro.jpg" alt="A top-down view of the final greybox environment with the perimeter wall geometry highlighted in yellow." width="100%"/>

<Tabs>
  <TabItem key = "1" label="Create Your Own">

자신만의 주변 벽 지오메트리를 생성하려면:

1. **블록** 파트를 사용하여 건물의 메인 플로어 주변에 **주변 경계**를 만듭니다. 건물 입구의 가장자리를 제외합니다. 이 지오메트리는 플레이 가능한 영역을 벗어나지 않도록 하면서 건물에 들어오고 나갈 수 있도록 합니다.

   <img src="../img/05_Roblox_tutorial/GeneralPerimeter-1.jpg" alt="An angled top-down view of the floor and perimeter walls. The perimeter wall geometry is highlighted in yellow." width="100%"/>

1. 이 파트를 고정합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 주변 벽 지오메트리를 정확히 재현하려면:

1. **상단** 주변 벽을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 상단 벽</td>
   <td>`30, 30, 185`</td>
   <td>`-140, 20, 282.5`</td>
   </tr>
   <tr>
   <td>중앙 상단 벽</td>
   <td>`10, 30, 60`</td>
   <td>`-150, 20, 160`</td>
   </tr>
   <tr>
   <td>오른쪽 상단 벽</td>
   <td>`30, 30, 185`</td>
   <td>`-140, 20, 37.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Perimeter-1.jpg.webp" alt="An angled top-down view of the floor and top perimeter walls. The top perimeter wall geometry is highlighted in yellow." width="100%"/>

1. **측면** 주변 벽을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 벽</td>
   <td>`105, 30, 35`</td>
   <td>`-72.5, 20, 357.5`</td>
   </tr>
   <tr>
   <td>오른쪽 벽</td>
   <td>`105, 30, 35`</td>
   <td>`-72.5, 20, -37.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Perimeter-2.jpg.webp" alt="An angled top-down view of the floor, top perimeter walls, and side perimeter walls. The side perimeter wall geometry is highlighted in yellow." width="100%"/>

1. **왼쪽 하단** 주변 벽을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>

왼쪽 벽</td>
   <td>`20, 20, 40`</td>
   <td>`-34, 15, 320`</td>
   </tr>
   <tr>
   <td>중앙 벽</td>
   <td>`12, 45, 15`</td>
   <td>`-29, 24.5, 297.5`</td>
   </tr>
   <tr>
   <td>오른쪽 벽</td>
   <td>`5, 35, 5`</td>
   <td>`-27.5, 19.5, 287.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Perimeter-3.jpg.webp" alt="An angled top-down view of the floor, top perimeter walls, side perimeter walls, and bottom-left perimeter walls. The bottom-left perimeter wall geometry is highlighted in yellow." width="100%"/>

1. **오른쪽 하단** 주변 벽을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 벽</td>
   <td>`5, 35, 5`</td>
   <td>`-27.5, 19.5, 32.5`</td>
   </tr>
   <tr>
   <td>중앙 벽</td>
   <td>`12, 45, 15`</td>
   <td>`-29, 24.5, 22.5`</td>
   </tr>
   <tr>
   <td>오른쪽 벽</td>
   <td>`20, 20, 40`</td>
   <td>`-35, 15, 0`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Perimeter-4.jpg.webp" alt="An angled top-down view of the floor, top perimeter walls, side perimeter walls, bottom perimeter walls. The bottom-right perimeter wall geometry is highlighted in yellow." width="100%"/>

1. 이 주변 벽 파트를 모두 고정합니다.

  </TabItem>
</Tabs>

##### 스폰 존 지오메트리

레이저 태그 그레이박스 환경을 만드는 세 번째 단계는 각 팀의 스폰 존을 포함하는 지오메트리를 만드는 것입니다. 중앙 집중 스폰 존만 포함하는 경험의 경우, 이를 개별 방으로 구분하면 사용자가 매치에 처음 합류할 때 경험에 적응할 수 있으며, 체력이 0이 된 후 매치에 다시 합류할 때 적의 공격으로부터 보호받을 수 있습니다.

[Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) `.rbxl` 파일에는 사용자가 합류할 수 있는 각 팀에 하나씩 두 개의 스폰 존이 있으며, 맵의 반대쪽 끝에 위치해 있습니다. 각 스폰 존에는 사용자가 주요 게임플레이 영역으로 빠르게 접근할 수 있도록 두 개의 출구가 있어, 두 개의 주요 레인에 빠르게 접근할 수 있으며, 스폰 존 근처의 교차 레인에서 적의 공격으로부터 보호받을 수 있습니다. 두 개의 출구가 있는 것은 중요한데, 하나의 출구만 있을 경우 사용자가 스폰 존에 들어가거나 나가려고 할 때 병목 현상이 발생할 수 있고, 세 개의 스폰 존은 매치 시작 후 적의 공격으로부터 충분한 보호를 제공하지 않기 때문입니다.

<img src="../img/05_Roblox_tutorial/SpawnZone-ExitPoints.jpg" alt="An angled top-down view of a spawn zone with arrows pointing toward the two exit points and all paths users can take away from the spawn zone." width="60%"/>

경험을 위해 만드는 스폰 존 영역의 지오메트리를 시각화하는 데 도움이 되도록 다음 이미지를 참고하세요. 노란색으로 표시되어 있습니다.

<img src="../img/05_Roblox_tutorial/SpawnZone-Intro.jpg" alt="A top-down view of the final greybox environment with the spawn zone wall geometry highlighted in yellow." width="100%"/>

<Tabs>
  <TabItem key = "1" label="Create Your Own">

자신만의 스폰 존 지오메트리를 생성하려면:

1. **블록** 파트를 사용하여 맵의 왼쪽 끝과 오른쪽 끝에 대칭적으로 각 팀의 **스폰 존**을 두 개의 출구로 분할합니다.

   <img src="../img/05_Roblox_tutorial/GeneralSpawnZone-1.jpg" alt="An angled top-down view of the floor, perimeter, and spawn zone walls. The spawn zone wall geometry is highlighted in yellow." width="100%"/>

1. 이 파트를 고정합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 스폰 존 지오메트리를 정확히 재현하려면:

1. 추가 **스폰 존 벽**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 스폰 존 벽</td>
   <td>`15, 15, 45`</td>
   <td>`-117.5, 12.5, 317.5`</td>
   </tr>
   <tr>
   <td>오른쪽 스폰 존 벽</td>
   <td>`15, 15, 45`</td>
   <td>`-117.5, 12.5, 2.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SpawnZone-1.jpg.webp" alt="An angled top-down view of the floor, perimeter, and top spawn zone walls. The top spawn zone wall geometry is highlighted in yellow." width="100%"/>

1. 왼쪽 스폰 존의 **출입구**를 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 스폰, 상단 벽</td>
   <td>`10, 15, 5`</td>
   <td>`-105, 12.5, 297.5`</td>
   </tr>
   <tr>
   <td>왼쪽 스폰, 상단 문</td>
   <td>`10, 5, 5`</td>
   <td>`-95, 17.5, 297.5`</td>
   </tr>
   <tr>
   <td>왼쪽 스폰, 중앙 벽</td>
   <td>`25, 15, 5`</td>
   <td>`-77.5, 12.5, 297.5`</td>
   </tr>
   <tr>
   <td>왼쪽 스폰, 하단 문</td>
   <td>`10, 5, 5`</td>
   <td>`-60, 17.5, 297.5`</td>
   </tr>
   <tr>
   <td>왼쪽 스폰, 하단 벽</td>
   <td>`20, 15, 5`</td>
   <td>`-45, 12.5, 297.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SpawnZone-2.jpg.webp" alt="An angled top-down view of the floor, perimeter, top spawn zone walls, and left spawn zone walls. The left spawn zone wall geometry is highlighted in yellow." width="100%"/>

1. 오른쪽 스폰 존의 **출입구**를 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>오른쪽 스폰 상단 벽</td>
   <td>`10, 15, 5`</td>
   <td

>`-105, 12.5, 22.5`</td>
   </tr>
   <tr>
   <td>오른쪽 스폰, 상단 문</td>
   <td>`10, 5, 5`</td>
   <td>`-95, 17.5, 22.5`</td>
   </tr>
   <tr>
   <td>오른쪽 스폰, 중앙 벽</td>
   <td>`25, 15, 5`</td>
   <td>`-77.5, 12.5, 22.5`</td>
   </tr>
   <tr>
   <td>오른쪽 스폰, 하단 문</td>
   <td>`10, 5, 5`</td>
   <td>`-60, 17.5, 22.5`</td>
   </tr>
   <tr>
   <td>오른쪽 스폰, 하단 벽</td>
   <td>`20, 15, 5`</td>
   <td>`-45, 12.5, 22.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/SpawnZone-3.jpg.webp" alt="An angled top-down view of the floor, perimeter, all spawn zone walls. The right spawn zone wall geometry is highlighted in yellow." width="100%"/>

1. 이 스폰 존 파트를 모두 고정합니다.

  </TabItem>
</Tabs>

##### 전투 포켓 지오메트리

레이저 태그 그레이박스 환경을 만드는 네 번째 단계는 건물 내부의 전투 포켓 지오메트리를 만드는 것입니다. 이 지오메트리는 경험의 플레이 가능한 영역 대부분을 차지하며, 주요 레인과 교차 레인의 교차점에서 전투 포켓이 형성되어 건물 전체에 걸쳐 있습니다.

이 섹션의 지침에서는 맵의 상단 보기 위치에 따라 이 지오메트리를 세 개의 별도 전투 포켓으로 설명합니다: 왼쪽 전투 포켓, 중간 전투 포켓, 오른쪽 전투 포켓. 대부분의 전투 포켓에는 사용자가 공간을 탐색할 때 선택 과부하를 피하기 위해 최대 세 개의 입구 또는 출구가 포함됩니다.

<img src="../img/05_Roblox_tutorial/CombatPockets-Intro1.jpg" alt="A top-down view of the final greybox environment with the left, middle, and right combat pockets highlighted." width="100%"/>

경험을 위해 만드는 전투 포켓 지오메트리를 시각화하는 데 도움이 되도록 다음 이미지를 참고하세요. 노란색으로 표시되어 있습니다.

<img src="../img/05_Roblox_tutorial/CombatPockets-Intro2.jpg" alt="A top-down view of the final greybox environment with the combat pocket geometry highlighted in yellow." width="100%"/>

<Tabs>
  <TabItem key = "1" label="Create Your Own">

자신만의 전투 포켓 지오메트리를 생성하려면:

1. **블록** 파트를 사용하여 두 개의 출구가 있는 **왼쪽 전투 포켓**을 만들고 플레이어가 중앙 레인을 이동할 수 있도록 하며, 한 개의 출구는 내부 주요 레인으로 열립니다. 이 지오메트리는 교차 레인을 위해 전투 포켓의 양쪽에 공간을 두고, 외부 주요 레인에서 플레이어의 진입을 차단해야 합니다.

   <img src="../img/05_Roblox_tutorial/CombatPockets-1.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, and left combat pocket. The left combat pocket geometry is highlighted in yellow." width="100%"/>

1. **블록** 파트를 사용하여 이 전투 포켓의 대칭 복사본을 다른 팀의 스폰 존 근처에 만들고 배치합니다. 이 지오메트리는 **오른쪽 전투 포켓**을 나타냅니다.

   <img src="../img/05_Roblox_tutorial/GeneralCombatPockets-2.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, and right combat pocket. The right combat pocket geometry is highlighted in yellow." width="100%"/>

1. **블록** 파트를 사용하여 두 개의 출구가 있는 **중간 전투 포켓**을 만들고 플레이어가 중앙 레인을 이동할 수 있도록 하며, 한 개의 출구는 내부 주요 레인으로 열리고 가장자리에는 외부 주요 레인으로 이어지는 열린 공간을 만듭니다.

   <img src="../img/05_Roblox_tutorial/GeneralCombatPockets-3.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, middle combat pocket, and right combat pocket. The middle combat pocket geometry is highlighted in yellow." width="100%"/>

1. **(선택 사항)** **블록** 파트를 사용하여 중앙 전투 포켓의 **복도 추가**를 만들어 내부 주요 레인의 시야선을 분할합니다.

   <img src="../img/05_Roblox_tutorial/GeneralCombatPockets-4.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, middle combat pocket, right combat pocket, and hallway addition walls. The hallway addition geometry is highlighted in yellow." width="100%"/>

1. 이 파트를 고정합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 전투 포켓 지오메트리를 정확히 재현하려면:

1. **왼쪽 전투 포켓**을 위한 **블록** 파트를 추가하고 구성합니다.

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>상단 복도 확장</td>
   <td>`10, 15, 15`</td>
   <td>`-100, 12.5, 272.5`</td>
   </tr>
   <tr>
   <td>상단 출입구, 왼쪽 벽</td>
   <td>`5, 15, 15`</td>
   <td>`-92.5, 12.5, 262.5`</td>
   </tr>
   <tr>
   <td>상단 출입구, 오버행</td>
   <td>`5, 5, 10`</td>
   <td>`-92.5, 17.5, 250`</td>
   </tr>
   <tr>
   <td>상단 출입구, 오른쪽 벽</td>
   <td>`5, 15, 20`</td>
   <td>`-92.5, 12.5, 235`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 상단 벽</td>
   <td>`20, 15, 5`</td>
   <td>`-85, 12.5, 272.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 오버행</td>
   <td>`10, 5, 5`</td>
   <td>`-70, 17.5, 272.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 하단 벽</td>
   <td>`20, 15, 5`</td>
   <td>`-55, 12.5, 272.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 상단 벽</td>
   <td>`15, 15, 10`</td>
   <td>`-82.5, 12.5, 230`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 오버행</td>
   <td>`10, 5, 10`</td>
   <td>`-70, 17.5, 230`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 하단 벽</td>
   <td>`20, 15, 10`</td>
   <td>`-55, 12.5, 230`</td>
   </tr>
   <tr>
   <td>하단 벽</td>
   <td>`10, 15, 35`</td>
   <td>`-50, 12.5, 252.5

`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/CombatPockets-1.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, and left combat pocket. The left combat pocket geometry is highlighted in yellow." width="100%"/>

1. 내부 주요 레인의 시야선을 분할하는 중간 전투 포켓의 **상단 복도 추가**를 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 복도 확장</td>
   <td>`15, 20, 45`</td>
   <td>`-117.5, 15, 212.5`</td>
   </tr>
   <tr>
   <td>오른쪽 복도 확장</td>
   <td>`15, 20, 45`</td>
   <td>`-117.5, 15, 107.5`</td>
   </tr>
   <tr>
   <td>왼쪽 복도</td>
   <td>`5, 20, 45`</td>
   <td>`-92.5, 15, 187.5`</td>
   </tr>
   <tr>
   <td>오른쪽 복도</td>
   <td>`5, 20, 45`</td>
   <td>`-92.5, 15, 132.5`</td>
   </tr>
   <tr>
   <td>상단 복도 입구, 왼쪽 벽</td>
   <td>`15, 15, 5`</td>
   <td>`-102.5, 17.5, 172.5`</td>
   </tr>
   <tr>
   <td>상단 복도 입구, 입구 왼쪽 벽</td>
   <td>`5, 15, 10`</td>
   <td>`-112.5, 17.5, 170`</td>
   </tr>
   <tr>
   <td>상단 복도 입구, 오른쪽 벽</td>
   <td>`15, 15, 5`</td>
   <td>`-102.5, 17.5, 147.5`</td>
   </tr>
   <tr>
   <td>상단 복도 입구, 입구 오른쪽 벽</td>
   <td>`5, 15, 10`</td>
   <td>`-112.5, 17.5, 150`</td>
   </tr>
   <tr>
   <td>문 오버행</td>
   <td>`5, 5, 10`</td>
   <td>`-92.5, 22.5, 160`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/CombatPockets-2.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, and top hallway addition walls. The top hallway addition wall geometry is highlighted in yellow." width="100%"/>

1. 중간 전투 포켓의 **중간 방**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>복도로 확장되는 왼쪽 벽</td>
   <td>`10, 20, 25`</td>
   <td>`-85, 15, 197.5`</td>
   </tr>
   <tr>
   <td>복도로 확장되는 오른쪽 벽</td>
   <td>`10, 20, 25`</td>
   <td>`-85, 15, 122.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 상단 벽</td>
   <td>`25, 20, 15`</td>
   <td>`-67.5, 15, 192.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 오버행</td>
   <td>`10, 10, 15`</td>
   <td>`-50, 20, 192.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 하단 벽</td>
   <td>`5, 20, 15`</td>
   <td>`-42.5, 15, 192.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 상단 벽</td>
   <td>`25, 20, 15`</td>
   <td>`-67.5, 15, 127.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 오버행</td>
   <td>`10, 10, 15`</td>
   <td>`-50, 20, 127.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 하단 벽</td>
   <td>`5, 20, 15`</td>
   <td>`-42.5, 15, 127.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/CombatPockets-3.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, top hallway addition walls, and the middle room of the middle combat pocket. The middle room of the middle combat pocket geometry is highlighted in yellow." width="100%"/>

1. **오른쪽 전투 포켓**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>상단 복도 확장</td>
   <td>`10, 15, 15`</td>
   <td>`-100, 12.5, 47.5`</td>
   </tr>
   <tr>
   <td>상단 출입구, 왼쪽 벽</td>
   <td>`5, 15, 20`</td>
   <td>`-92.5, 12.5, 85`</td>
   </tr>
   <tr>
   <td>상단 출입구, 오버행</td>
   <td>`5, 5, 10`</td>
   <td>`-92.5, 17.5, 70`</td>
   </tr>
   <tr>
   <td>상단 출입구, 오른쪽 벽</td>
   <td>`5, 15, 15`</td>
   <td>`-92.5, 12.5, 57.5`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 상단 벽</td>
   <td>`15, 15, 10`</td>
   <td>`-82.5, 12.5, 90`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 오버행</td>
   <td>`10, 5, 10`</td>
   <td>`-70, 17.5, 90`</td>
   </tr>
   <tr>
   <td>왼쪽 출입구, 하단 벽</td>
   <td>`20, 15, 10`</td>
   <td>`-55, 12.5, 90`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 상단 벽</td>
   <td>`20, 15, 5`</td>
   <td>`-85, 12.5, 47.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 오버행</td>
   <td>`10, 5, 5`</td>
   <td>`-70, 17.5, 47.5`</td>
   </tr>
   <tr>
   <td>오른쪽 출입구, 하단 벽

</td>
   <td>`20, 15, 5`</td>
   <td>`-55, 12.5, 47.5`</td>
   </tr>
   <tr>
   <td>하단 벽</td>
   <td>`10, 15, 35`</td>
   <td>`-50, 12.5, 67.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/CombatPockets-4.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, left combat pocket, top hallway addition walls, middle combat pocket, and right combat pocket. The right combat pocket geometry is highlighted in yellow." width="100%"/>

1. 이 전투 포켓 파트를 모두 고정합니다.

  </TabItem>
</Tabs>

##### 외부 지오메트리

레이저 태그 그레이박스 환경을 만드는 마지막 단계는 실외 공간을 위한 흥미로운 구성을 만들기 위한 플레이스홀더 외부 자산을 만들고, 외부 주요 레인을 이동하는 사용자에게 최소한의 커버를 제공하는 것입니다. 이 영역은 위험이 따르지만 적의 스폰 존으로 빠르게 이동할 수 있는 경로를 제공하기 때문에 중요합니다.

경험을 위해 만드는 외부 자산의 지오메트리를 시각화하는 데 도움이 되도록 다음 이미지를 참고하세요. 노란색으로 표시되어 있습니다.

<img src="../img/05_Roblox_tutorial/Exterior-Intro.jpg" alt="A top-down view of the final greybox environment with the exterior geometry highlighted in yellow." width="100%"/>

<Tabs>
  <TabItem key = "1" label="Create Your Own">

자신만의 외부 지오메트리를 생성하려면:

1. **블록** 파트를 사용하여 외부 주요 레인 주변에 대칭 **장애물**을 만듭니다. 예를 들어, 샘플 그레이박스 환경은 나중에 타워, 기둥, 화단이 될 부품을 추가하여 시야를 차단합니다.

   <img src="../img/05_Roblox_tutorial/GeneralExterior-1.jpg" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, and exterior geometry. The exterior geometry is highlighted in yellow." width="100%"/>

1. 이 파트를 고정합니다.

  </TabItem>
  <TabItem key = "2" label="Recreate the Sample">

샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) 장소 파일 내에서 외부 지오메트리를 정확히 재현하려면:

1. **왼쪽 타워**를 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 벽</td>
   <td>`15, 25, 5`</td>
   <td>`-32.5, 22.5, 192.5`</td>
   </tr>
   <tr>
   <td>오른쪽 벽</td>
   <td>`15, 40, 10`</td>
   <td>`-32.5, 30, 185`</td>
   </tr>
   <tr>
   <td>하단 가장자리</td>
   <td>`20, 5, 15`</td>
   <td>`-30, 7.5, 187.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Exterior-1.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, and left tower geometry. The left tower geometry is highlighted in yellow." width="100%"/>

1. **오른쪽 타워**를 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 벽</td>
   <td>`15, 40, 10`</td>
   <td>`-32.5, 30, 135`</td>
   </tr>
   <tr>
   <td>오른쪽 벽</td>
   <td>`15, 25, 5`</td>
   <td>`-32.5, 22.5, 127.5`</td>
   </tr>
   <tr>
   <td>하단 가장자리</td>
   <td>`20, 5, 15`</td>
   <td>`-30, 7.5, 132.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Exterior-2.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, left tower, and right tower geometry. The right tower geometry is highlighted in yellow." width="100%"/>

1. **타워 왼쪽의 장애물**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 장애물</td>
   <td>`20, 10, 5`</td>
   <td>`-15, 5, 262.5`</td>
   </tr>
   <tr>
   <td>중앙 장애물</td>
   <td>`15, 30, 5`</td>
   <td>`-22.5, 15, 237.5`</td>
   </tr>
   <tr>
   <td>오른쪽 장애물</td>
   <td>`10, 10, 15`</td>
   <td>`-5, 5, 202.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Exterior-3.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, left tower, right tower, and obstacle geometry to the left of the left tower. The obstacle geometry to the left of the left tower are highlighted in yellow." width="100%"/>

1. **타워 오른쪽의 장애물**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>왼쪽 장애물</td>
   <td>`10, 10, 15`</td>
   <td>`-5, 5, 117.5`</td>
   </tr>
   <tr>
   <td>중앙 장애물</td>
   <td>`15, 30, 5`</td>
   <td>`-22.5, 15, 82.5`</td>
   </tr>
   <tr>
   <td>오른쪽 장애물</td>
   <td>`20, 10, 5`</td>
   <td>`-15, 5, 57.5`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Exterior-4.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, left tower, right tower, and obstacle geometry to the left and right of the towers. The obstacle geometry to the right of the right tower are highlighted in yellow." width="100%"/>

1. **타워 사이의 장애물**을 위한 **블록** 파트를 추가하고 구성합니다:

   <table>
   <thead>
   <tr>
   <th>파트</th>
   <th>크기</th>
   <th>CFrame.Position</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>상단 장애물</td>
   <td>`10, 5, 5`</td>
   <td>`-50, 7.5, 160`</td>
   </tr>
   <tr>
   <td>중앙 장애물</td>
   <td>`20, 10, 10`</td>
   <td

>`-35, 10, 160`</td>
   </tr>
   <tr>
   <td>하단 장애물</td>
   <td>`10, 10, 30`</td>
   <td>`0, 5, 160`</td>
   </tr>
   </tbody>
   </table>

   <img src="../img/05_Roblox_tutorial/Exterior-5.jpg.webp" alt="An angled top-down view of the floor, perimeter, spawn zone walls, combat pockets, left tower, right tower, and obstacle geometry. The obstacle geometry between the towers are highlighted in yellow." width="100%"/>

1. 이 타워 파트를 모두 고정합니다.

  </TabItem>
</Tabs>

#### 플레이스홀더 재료 적용

이제 플레이스홀더 지오메트리가 자리에 있으므로, 경험의 특정 위치를 사용자에게 알려주는 주요 영역에 플레이스홀더 재료를 적용할 시간입니다. 샘플 [Environment Art - Greyboxing](https://www.roblox.com/games/14447721254/Environment-Art-Greyboxing) `.rbxl` 파일은 다음 색상 지도를 사용하지만, 동일한 목적을 달성하기 위해 원하는 색상을 사용할 수 있습니다:

- **상단 주변 벽의 딥 오렌지** – 사용자가 건물의 뒷면에 있는 위치를 알 수 있도록 합니다.
- **모든 왼쪽 바닥의 퍼시몬** – 사용자가 건물의 오른쪽에 있는 위치를 알 수 있도록 합니다.
- **모든 오른쪽 바닥의 라피스** – 사용자가 건물의 왼쪽에 있는 위치를 알 수 있도록 합니다.
- **외부 고도의 밝은 녹색** – 사용자가 건물 외부에 있는 위치를 알 수 있도록 합니다.

이 특정 주요 영역에 재료를 적용하는 것은 중요합니다. 사용자가 경험의 어느 위치에 있든 이 색상 중 하나라도 볼 수 있다면, 전체 맵 내에서 자신의 대략적인 위치를 빠르게 추론하고, 스폰 존과의 관계를 이해할 수 있기 때문입니다.

예를 들어, 다음 사용자가 "빨간색" 팀에 속해 있을 때, 빨간색 바닥 위를 걷고 노란색 벽이 오른쪽에 있으면, 사용자는 내부 주요 레인에 있으며 자신의 스폰 존을 향해 이동하고 있음을 알 수 있습니다. 반대로, 파란색 바닥 위를 걷고 노란색 벽이 왼쪽에 있으면, 사용자는 내부 레인에 있으며 적 팀의 스폰 존을 향해 이동하고 있음을 알 수 있습니다.

<GridContainer numColumns="2">
  <figure>
    <img src="../img/05_Roblox_tutorial/Placeholder-Left.jpg" alt="A Rthro avatar standing on a red floor with a yellow wall to their right. This color configuration informs the user that they're in the interior primary lane and moving toward the red spawn zone." width="100%"/>
  </figure>
  <figure>
    <img src="../img/05_Roblox_tutorial/Placeholder-Right.jpg" alt="A Rthro avatar standing on a blue floor with a yellow wall to their left. This color configuration informs the user that they're in the interior primary lane and moving toward the blue spawn zone." width="100%"/>
  </figure>
</GridContainer>

플레이스홀더 재료를 적용하려면:

1. 상단 주변 벽과 상단 복도 추가물을 선택한 다음 `Class.Part.Color`를 **255, 176, 0**으로 설정합니다.
1. 왼쪽 바닥 파트를 선택한 다음 `Class.Part.Color`를 **255, 89, 89**으로 설정합니다.
1. 오른쪽 바닥 파트를 선택한 다음 `Class.Part.Color`를 **16, 42, 220**으로 설정합니다.
1. 지상과 1층 사이의 고도를 위한 파트를 선택한 다음 `Class.Part.Color`를 **75, 151, 75**으로 설정합니다.

<img src="../img/05_Roblox_tutorial/PlaceholderMaterials.jpg" alt="An angled top-down view of the final greybox environment with placeholder materials to mark unique sections of the map." width="100%"/>

#### 레이아웃 테스트

경험이 재미있고 기능적이며, 개발 과정의 거의 모든 단계에서 레이아웃을 지속적으로 테스트하는 것이 중요합니다. 이렇게 하면 프로세스가 진행될수록 작은 문제가 더 큰 문제로 발전하기 전에 잡을 수 있습니다. 테스트하면서 다음 질문을 스스로에게 던져보세요:

- 어느 팀에게 유리하거나 불리한 점이 있습니까?
- 사용자가 맵의 어느 지점에서도 성공적으로 자신의 위치를 파악하고 이해할 수 있습니까?
- 맵의 어느 부분이 너무 많은 선택지로 사용자를 압도합니까?
- 레이아웃이나 게임플레이에 대해 즐겁거나 좌절감을 느끼는 점은 무엇입니까?
- 사용자가 이 지역에 있을 때 원하는 감정을 느끼게 할 수 있습니까?
- 맵의 어느 부분을 우회하여 목표를 달성할 수 있습니까?

경험을 테스트하려면:

1. **테스트** 탭에서 **플레이** 아이콘으로 이동하여 **모드 선택기**를 클릭합니다.

   <img src="../img/05_Roblox_tutorial/Model-Tab-Quick-Access-Play.png" width="770" alt="Studio's Model tab with the Play button highlighted in the menu bar." />

2. 다음 플레이 테스트 옵션 중 하나를 선택합니다:

   - **플레이** – 경험을 시뮬레이션하기 시작하여 아바타를 `Class.SpawnLocation` 또는 약 **0, 100, 0**의 좌표에 삽입합니다.
   - **여기서 플레이** – 경험을 시뮬레이션하기 시작하여 아바타를 현재 카메라 위치 앞에 삽입합니다.
   - **실행** – 아바타를 삽입하지 않고 경험을 시뮬레이션하기 시작합니다. 대신, 시뮬레이션은 현재 카메라 위치에서 시작되며 Studio 카메라 제어를 사용하여 주변을 탐색할 수 있습니다.

플레이 테스트 중에는 기본 Roblox 경험과 동일한 컨트롤을 사용할 수 있습니다. 전체 레이아웃에 만족하면 그레이박스 지오메트리를 대체할 경험의 아트 스타일에 따라 자산을 만드는 작업을 시작할 수 있습니다.


### Chapter 2 - Develop Polished Assets

### Chapter 3 - Assemble an Asset Library

### Chapter 4 - Construct Your World

### Chapter 5 - Optimize Your Experience



---
## 출처
 - [Creating Your First Experience](https://create.roblox.com/docs/ko-kr/tutorials/first-experience)
---
## [다음]()