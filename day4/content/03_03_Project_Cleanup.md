# Project Cleanup

## 목차
- [Project Cleanup](#project-cleanup)
  - [목차](#목차)
  - [출처](#출처)
  - [다음](#다음)

---

모델링 및 텍스처링을 완료한 후, Blender 프로젝트를 `.fbx` 파일로 **내보내는** 과정을 시작할 수 있습니다. 이 과정의 시작은 프로젝트를 정리하는 것으로, 이는 액세서리 메시만 내보낼 수 있도록 조명, 카메라 또는 마네킹 메시와 같은 불필요한 객체를 삭제하거나 제거하는 것을 포함할 수 있으며, 메시 객체에 모든 수정자를 적용하는 것을 포함할 수 있습니다.

종종 잊혀지는 정리 단계는 방향, 회전 및 크기 델타를 0으로 설정하여 변형을 **적용**하는 것으로, 이는 **변환 고정**이라고도 합니다. 변환을 적용하지 않으면 Studio에서 메시를 가져올 때 예상치 못한 동작과 방향이 발생할 수 있습니다.

변환을 고정하려면:

1. 객체 모드에서 메시 객체를 선택합니다.
2. **Object** > **Apply** > **All Transforms**로 이동합니다.

   <img src="../img/03_03_Project_Cleanup/Blender-Apply-Transforms.png" />

---
## 출처
 - [Project Cleanup](https://create.roblox.com/docs/art/accessories/creating-rigid/clean-up)

---
## [다음](./03_04_Exporting_FBX.md)