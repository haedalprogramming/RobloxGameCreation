# Sculpting Detail

## 목차
- [Sculpting Detail](#sculpting-detail)
  - [목차](#목차)
  - [출처](#출처)
  - [다음](#다음)

---

의상 메시의 크기를 조정하고 위치를 설정한 후, 메시에 옷감 및 섬유 세부 사항을 추가하기 위해 조각 세부 작업을 시작합니다. Blender에서 객체를 조각하는 방법은 여러 가지가 있지만, 이 튜토리얼에서는 주로 **Elastic Deform**, **Inflate**, **Cloth** 도구를 사용하여 메시를 더 현실적인 의상처럼 보이게 합니다.

<center>
  <figure>
    <img src="../img/04_03_Sculpting_Detail/Modeling-Complete-2.png" width="60%" />
    <figcaption>조각 세부 작업 후 의상 메시</figcaption>
  </figure>
</center>

의상 세부 사항을 추가하려면:

1. 셔츠가 강조 표시된 상태에서 **Sculpt Mode**로 전환합니다.
2. 필요에 따라 **X-Ray 모드**를 비활성화합니다.
3. 대칭 편집을 수행하려면 **X Mirror**를 활성화합니다.
4. **Elastic Deform** 도구를 선택하고 강도를 `.5`로 설정하여 마네킹을 완전히 덮도록 정점의 일부를 늘립니다.

   1. <kbd>F</kbd>를 사용하여 브러시의 반경을 변경합니다.
   2. 접근하기 어려운 영역에 접근하기 위해 마네킹을 숨길 수 있습니다.

      <video controls src="../img/04_03_Sculpting_Detail/Modeling_05.mp4" width="100%"></video>

5. **Cloth** 도구를 선택합니다.
6. **X Mirror**를 비활성화합니다. 천 도구는 대칭이 활성화된 상태에서 예상치 못한 결과를 초래할 수 있습니다.
7. Cloth 도구를 사용하여 메시에 천과 같은 표면을 추가하기 위해 클릭하고 드래그합니다. 변형 강도를 변경하려면 설정을 조정합니다.

   <video controls src="../img/04_03_Sculpting_Detail/Modeling_06.mp4" width="100%"></video>

8. **Elastic Deform**, **Inflate**, **Cloth** 도구를 사용하여 최종적으로 메시를 조정하여 마네킹 위에 원하는 최종 모양으로 배치합니다.

   <video controls src="../img/04_03_Sculpting_Detail/Modeling_07.mp4" width="100%"></video>

---
## 출처
 - [Sculpting Detail](https://create.roblox.com/docs/art/accessories/creating/sculpting)

---
## [다음]()