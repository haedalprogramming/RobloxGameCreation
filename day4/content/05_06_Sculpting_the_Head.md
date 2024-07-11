# Sculpting the Head

## 목차
- [Sculpting the Head](#sculpting-the-head)
  - [목차](#목차)
  - [출처](#출처)
  - [다음](#다음)

---

모델링 모범 사례와 조각 팁을 검토한 후 캐릭터 조각을 시작할 수 있습니다. 이 튜토리얼은 [RoundMale 템플릿](https://prod.docsiteassets.roblox.com/assets/art/reference-files/RoundMale.zip)에 대한 조각 변경을 시연하여 고블린과 같은 캐릭터를 만드는 방법을 보여줍니다.

조각 지침은 다음 조각 도구를 사용합니다:

- **Grab** - 선택하고 그룹의 정점을 당깁니다.
- **Smooth** - 브러시의 영향 영역에서 불규칙성을 제거합니다.
- **Flatten** - 브러시의 영향 아래에 있는 정점을 공통 평면에서 평균화합니다.
- **Elastic Deform** - Grab과 유사하지만 인접한 정점에 유기적 스트레치와 탄력을 더합니다.

<Alert severity='info'>
Blender의 다른 조각 도구를 사용할 수 있지만 모델의 정점을 보존하기 위해 비파괴 모델링 개념과 일치하는 도구를 사용하는 것이 중요합니다.
</Alert>

머리 조각을 시작하려면:

1. 템플릿 프로젝트를 열고 다른 Geo 객체를 숨겨 머리 메쉬를 분리합니다.
2. **Head_Geo** 메쉬 객체를 선택하고 **Sculpting** 모드로 전환합니다.
3. 뷰포트의 오른쪽 상단에서 다음 옵션을 설정합니다:
   1. **X-Axis Symmetry**를 활성화합니다.
   2. **Wireframe** 뷰를 활성화합니다.
      <video controls src="../img/05_06_Sculpting_the_Head/Sculpting_01.mp4" width="100%"></video>
4. **Mask** 도구를 사용하여 입과 눈을 덮어 예기치 않게 조각하지 않도록 합니다.
   <video controls muted src="../img/05_06_Sculpting_the_Head/Sculpting_02.mp4" width="100%"></video>
5. **Grab** 및 **Smooth** 도구를 사용하여 템플릿 머리에 다음 수정을 수행합니다:

   1. 머리 모양을 재구성하여 윗부분을 평평하게 하고 크게 만듭니다.

   2. 귀를 길게 늘립니다.

      1. 귀 근처의 표면을 확장하여 기반을 넓힙니다.
      2. 각 귀를 잡아당기고 확장하여 부드럽게 연결하고 가능한 경우 정점이 비례적으로 유지되도록 합니다.
      3. Flatten 도구를 사용하여 영역을 정렬하고 평평하게 합니다.
      4. Elastic Deform 도구를 사용하여 여러 정점을 늘리고 당깁니다.
         <video controls muted src="../img/05_06_Sculpting_the_Head/Sculpting_03.mp4" width="100%"></video>

   3. 콧등을 늘리고 눈썹 크기를 확장합니다.
      <video controls src="../img/05_06_Sculpting_the_Head/Sculpting_04.mp4" width="100%" muted></video>

   4. 턱을 넓혀서 눈에 띄게 돌출되게 합니다.
      <video controls src="../img/05_06_Sculpting_the_Head/Sculpting_06.mp4" width="100%" muted></video>

6. 최종 디테일을 추가하고 주요 특징을 다듬고 강조하여 정제 작업을 수행합니다. 예를 들어:
   - 외부 및 내부 귀에 디테일 추가
   - 턱과 뺨에 더 많은 디테일 추가
   - 정점이 밀집된 영역에서 엣지 라인과 간격 개선
     <video controls src="../img/05_06_Sculpting_the_Head/Sculpting_07.mp4" width="100%"></video>

<Alert severity = 'success'>
비교 참조를 위해 조각이 완료된 [이 튜토리얼 프로젝트 버전](https://prod.docsiteassets.roblox.com/assets/art/reference-files/checkpoint/1_Goblin-sculpted.blend)을 다운로드할 수 있습니다.
</Alert>

---
## 출처
 - [Sculpting the Head](https://create.roblox.com/docs/art/characters/creating/sculpting)

---
## [다음](./05_07_Texturing_Setup.md)