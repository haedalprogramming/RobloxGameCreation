# Rigging a Humanoid Model

## 목차
- [Rigging a Humanoid Model](#rigging-a-humanoid-model)
  - [목차](#목차)
  - [Blender 설정](#blender-설정)
    - [모델 가져오기](#모델-가져오기)
    - [뷰포트 시각화](#뷰포트-시각화)
  - [뼈대와 뼈 설정](#뼈대와-뼈-설정)
    - [X-Axis Mirror 활성화](#x-axis-mirror-활성화)
    - [뼈 위치 지정](#뼈-위치-지정)
    - [뼈대 종속](#뼈대-종속)
  - [메시를 뼈에 할당](#메시를-뼈에-할당)
  - [테스트](#테스트)
  - [출처](#출처)
  - [다음](#다음)

---

R15 휴머노이드 캐릭터 모델은 사용자 아바타 캐릭터를 구성하는 모델로, 15개의 개별 메시 객체로 구성됩니다. 간단한 메시를 리깅하는 것과 유사하게, 여러 개의 메시를 내부 뼈대에 결합하거나 종속시킬 수 있습니다. 여러 메시로 구성된 모델을 리깅하려면 [Blender](https://www.blender.org) 또는 [Maya](https://www.autodesk.com/products/maya/overview)와 같은 서드파티 모델링 도구에서 추가 단계를 수행해야 합니다.

이 고급 가이드는 제공된 템플릿과 휴머노이드 모델을 사용하여 Blender에서 휴머노이드 모델을 리깅하는 과정을 다룹니다. 이 리깅 단계는 [휴머노이드 모델 스킨닝](https://create.roblox.com/docs/art/modeling/skinning-a-humanoid-model) 전에 수행해야 합니다. 계속 진행하기 전에 [기본 모델 리깅](https://create.roblox.com/docs/art/modeling/rigging-a-simple-mesh)에 익숙해져야 합니다.

Blender에서 휴머노이드 모델을 리깅하려면 다음 단계를 수행합니다:

- [캐릭터 모델 가져오기](#모델-가져오기)하여 미리 만들어진 R15 뼈대 구조에 쉽게 접근할 수 있는 템플릿 파일을 사용합니다.
- 휴머노이드 캐릭터에 맞게 뼈대를 대칭적으로 [생성, 크기 조정 및 위치 지정](#뼈대와-뼈-설정)합니다.
- 단일 뼈대에 여러 메시를 [종속시켜](#뼈대-종속) 스켈레톤 리그를 결합합니다.
- 각 메시 객체와 뼈대에 [완전한 영향 할당](#메시를-뼈에-할당)하여 영향을 할당합니다.


이 가이드에서는 다운로드 가능한 [리그 및 부착 템플릿 Blender 프로젝트](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/reference-files/Rig_and_Attachments_Template.blend), 참조용 [롤라 캐릭터 모델](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/reference-files/lola-base-model.fbx), 그리고 [Blender 버전 3.0](https://www.blender.org/download/releases/3-0/)을 사용합니다. 다른 버전의 Blender를 사용하는 경우 UI 및 설정에 약간의 차이가 있을 수 있습니다.


## Blender 설정

휴머노이드 리깅 메시를 만들기 시작하려면 Blender 프로젝트에서 다음을 설정합니다:

- 매니킨 템플릿 Blender 프로젝트에 롤라 캐릭터 모델을 [가져오기](#모델-가져오기).
- 리깅 과정을 최적화하기 위해 [뷰포트 시각화](#뷰포트-시각화) 설정.

### 모델 가져오기

모델을 리깅할 때 사용하는 캐릭터 모델이 Studio의 [아바타 캐릭터 사양](https://create.roblox.com/docs/art/characters/specifications)을 준수하는지 확인하세요. 이 가이드에서는 매니킨 템플릿 프로젝트에 [롤라 참조 모델](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/reference-files/lola-base-model.fbx)을 가져옵니다.

모델을 가져오려면:

1. Blender에서 **File** > **Open**을 선택하고 `Rig_and_Attachments_Template.blend`를 엽니다.
2. **File** > **Import** > **FBX (.fbx)**를 선택하고 참조 롤라 모델 파일을 가져옵니다.
3. 필요한 경우, 모델을 뼈대 구조의 크기와 대략적으로 맞추기 위해 크기를 조정합니다. 아웃라이너에서 모든 메시 기하학을 선택하고 <kbd>G</kbd>를 눌러 재배치하고 <kbd>S</kbd>를 눌러 메시 객체의 크기를 조정할 수 있습니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/1-resizing-base-model.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/1-resizing-base-model.mp4)

### 뷰포트 시각화

뼈 객체에 대한 더 나은 시각화 및 접근을 위해 뷰포트 앞에 항상 표시되도록 뼈 객체를 설정합니다.

뼈 시각화를 설정하려면:

1. **뷰포트**에서 뼈대의 임의의 뼈를 클릭합니다.
2. **속성 편집기 패널**에서 **객체 데이터 속성 탭**을 선택합니다.
3. 뷰포트 디스플레이를 확장하고, **표시** 속성으로 이동한 다음 **앞에**를 활성화합니다.
   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/2-bone-visualization.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/2-bone-visualization.mp4)

스킨닝 과정 중 언제든지, 3D 뷰포트의 오른쪽 상단에 있는 다양한 재질 미리보기 옵션을 전환하여 캐릭터 모델의 시각화를 변경할 수 있습니다. 예를 들어 X-ray 또는 텍스처 보기를 활성화할 수 있습니다.

## 뼈대와 뼈 설정

이 가이드에서는 휴머노이드 캐릭터를 대칭적으로 변형하기 위해 X-Axis Mirroring을 설정합니다. 모델을 리깅할 때 가능한 한 대칭을 유지하도록 합니다.


뼈대를 수정하거나 새 뼈대 구조를 생성할 경우, R15 캐릭터 모델에 대한 <a href="https://create.roblox.com/docs/art/characters/specifications#humanoid-rigs">특정 뼈대 계층 및 이름 지정 요구 사항</a>을 유의해야 합니다.


### X-Axis Mirror 활성화

X-Axis Mirror 설정은 뼈대의 좌우 대칭을 유지하여 위치 변화를 반영합니다. 포즈 및 애니메이션과 관련된 문제를 줄이기 위해 가능한 한 대칭을 유지하는 것이 중요합니다.

X-Axis Mirror를 설정하려면:

1. **객체 모드**에서 **뼈대**를 선택합니다.
2. **편집 모드** (<kbd>Tab</kbd>)로 전환합니다.
3. 뷰포트 오른쪽 사이드바에서 도구 패널을 확장하고 **X-Axis Mirror**를 활성화합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/3-x-axis-mirror.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/3-x-axis-mirror.mp4)

### 뼈 위치 지정

모델을 프로젝트에 추가한 후, 템플릿에서 제공된 뼈대를 캐릭터 구조에 맞게 재배치할 수 있습니다. 대부분의 경우, 각 뼈는 해당하는 메시 객체의 중심에 위치해야 합니다. 예를 들어, 머리 뼈는 Head_Geo 메시 객체의 중심에 위치해야 합니다.

뼈 위치 지정은 사용 사례에 따라 다를 수 있으며, 특정 포즈나 애니메이션이 의도대로 작동하지 않을 경우 웨이트 페인팅 및 테스트 후 다시 방문해야 할 수도 있습니다.

개별 뼈의 위치를 지정하려면:

1. 객체 모드에서 재배치하려는 **뼈**를 클릭하여 강조 표시합니다.
2. 모드 드롭다운에서 **편집 모드**로 전환합니다.
3. 뼈의 **끝부분**을 클릭하여 강조 표시하고 <kbd>G</kbd>를 누릅니다. 뼈의 끝부분이 커서와 함께 움직입니다.
4. 이 뼈를 모델의 내부 중심과 정렬되도록 당긴 후 클릭하여 뼈의 위치를 설정합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/4-repositioning-bones.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/4-repositioning-bones.mp4)

5. 마우스 스크롤 휠을 클릭하고 끌거나 다양한 시점에서 뼈가 메시 객체 내에 있는지 확인합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/5-inspect-bones.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/5-inspect-bones.mp4)

### 뼈대 종속

뼈 구조를 위치시킨 후, 뼈대를 모델에 종속시켜야 합니다. 모든 15개의 메시 객체를 하나의 뼈대에 종속시켜야 합니다.

이 예제에서는 다음 [휴머노이드 모델 스킨닝](https://create.roblox.com/docs/art/modeling/skinning-a-humanoid-model) 가이드에서 정점 그룹 할당 및 웨이트 페인팅 과정을 설명하기 위해 메시 객체를 빈 그룹으로 뼈대에 종속시킵니다.

모델을 뼈대에 종속시키려면:

1. **객체 모드**로 전환합니다.
2. 아웃라이너에서 검색창에 "geo"를 입력하여 메시 객체를 필터링합니다.
3. 아웃라이너에서 첫 번째 및 마지막 메시 객체를 클릭하고 <kbd>Shift</kbd>를 누른 상태로 모든 메시 객체를 선택합니다.
4. 메시가 강조 표시된 상태에서 <kbd>Shift</kbd>를 누른 상태로 뷰포트 또는 아웃라이너에서 뼈대 객체를 클릭합니다.
5. 뷰포트에서 마우스 오른쪽 버튼을 클릭하고 **종속** > **빈 그룹으로**를선택합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/6-parenting-bones.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/6-parenting-bones.mp4)

## 메시를 뼈에 할당

이제 뼈대를 메시 객체에 연결했으므로 개별 팔과 다리의 정점을 대응하는 뼈에 완전히 영향을 받도록 할당할 수 있습니다. 이 과정이 완료되면 모델은 스킨닝 준비가 됩니다. 메시에 여러 뼈 영향을 적용하는 방법은 [휴머노이드 모델 스킨닝](https://create.roblox.com/docs/art/modeling/skinning-a-humanoid-model)을 참조하세요.


휴머노이드 리그의 **Root** 및 **HumanoidRootNode** 부모 뼈에는 어떠한 영향도 적용하지 않아야 합니다. 추가된 영향은 Studio로 가져올 때 삭제됩니다.


머리 메시에 완전한 영향을 할당하려면:

1. **객체 모드**에서 **머리 메시 객체**를 클릭하여 강조 표시합니다.
2. **편집 모드**로 전환합니다.
3. <kbd>A</kbd>를 눌러 메시 객체의 모든 정점을 선택합니다.
4. 모든 머리 정점이 강조 표시된 상태에서 화면 오른쪽의 **객체 속성 패널**로 이동합니다.
5. 패널의 **정점 그룹** 섹션에서 할당하려는 뼈의 이름을 선택하고 **할당**을 클릭합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/7-assign-influence-head.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/7-assign-influence-head.mp4)

이 모드에서는 아웃라이너에서 다음 메시 객체를 선택하고 해당 정점 그룹에 할당하여 모든 메시 객체를 빠르게 반복할 수 있습니다. 이 가이드에서는 **캐릭터의 모든 메시 객체를 해당 뼈에 할당**합니다.

나머지 바디 메시에 정점 그룹을 빠르게 할당하려면:

1. 아웃라이너 패널에서 편집하려는 객체 옆의 점을 클릭합니다. 점을 클릭하면 활성 편집 아이콘으로 전환됩니다.
2. 정점이 강조 표시되지 않은 경우 <kbd>A</kbd>를 눌러 모든 정점을 선택합니다.
3. **객체 속성 패널** > **정점 그룹** 섹션에서 적절한 정점 그룹을 선택하고 **할당**을 클릭합니다. 검색창을 사용하여 특정 정점 그룹 이름을 찾을 수 있습니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/8-assign-influence.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/8-assign-influence.mp4)

## 테스트

포즈 모드에서 뼈와 할당된 메시 객체를 테스트하고 포즈를 취할 수 있습니다. 영향을 적용하거나 편집한 후 모델을 테스트하는 것이 중요합니다.

포즈 모드로 전환하여 포즈를 테스트하려면:

1. **객체 모드**에서 모델의 임의의 부분을 선택합니다.
2. 모드 드롭다운을 클릭한 다음 **포즈** 모드로 전환합니다.
3. <kbd>Shift</kbd>를 누르고 테스트하려는 뼈를 클릭하여 강조 표시한 다음 <kbd>R</kbd>을 눌러 회전을 테스트합니다.
4. <kbd>Alt</kbd><kbd>A</kbd> (<kbd>⌥</kbd><kbd>A</kbd>)를 눌러 현재 뼈를 선택 취소한 다음 다른 뼈를 다시 선택하고 테스트합니다.

   <!-- <video controls src="../img/01_04_Rigging_a_Humanoid_Model/9-test-bones.mp4" width="100%"></video> -->
   [![](../img/youtube.png)](https://prod.docsiteassets.roblox.com/assets/modeling/meshes/rigging-humanoid/9-test-bones.mp4)


   선택된 뼈를 중립으로 되돌리려면 <KeyboardInput>Alt</KeyboardInput>+<KeyboardInput>R</KeyboardInput>을 누르십시오. 회전하는 동안 마우스의 스크롤 휠을 눌러 회전 축을 변경할 수도 있습니다.


이 단계에서, 모든 메시 객체가 해당 뼈의 영향을 받는 경우, 이 리깅된 모델을 Studio에서 사용할 수 있도록 `.fbx`로 [내보내기](https://create.roblox.com/docs/art/modeling/export-requirements)하거나 [휴머노이드 모델 스킨닝](https://create.roblox.com/docs/art/modeling/skinning-a-humanoid-model)의 다음 단계로 계속 진행할 수 있습니다.

---
## 출처
 - [Rigging a Humanoid Model](https://create.roblox.com/docs/art/modeling/rigging-a-humanoid-model.md)

---
## [다음](./01_05_Skinning_a_Humanoid_Model.md)