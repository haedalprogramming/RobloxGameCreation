# Global Lighting

## 목차
- [Global Lighting](#global-lighting)
  - [목차](#목차)
  - [색상](#색상)
    - [Ambient](#ambient)
    - [OutdoorAmbient](#outdoorambient)
    - [ColorShift\_Top](#colorshift_top)
    - [ColorShift\_Bottom](#colorshift_bottom)
  - [강도](#강도)
    - [Brightness](#brightness)
    - [ExposureCompensation](#exposurecompensation)
  - [그림자](#그림자)
    - [GlobalShadows](#globalshadows)
    - [ShadowSoftness](#shadowsoftness)
  - [환경](#환경)
    - [ClockTime 및 TimeOfDay](#clocktime-및-timeofday)
    - [GeographicLatitude](#geographiclatitude)
    - [EnvironmentDiffuseScale](#environmentdiffusescale)
    - [EnvironmentSpecularScale](#environmentspecularscale)
  - [기술](#기술)
  - [출처](#출처)
  - [다음](#다음)

---

`Lighting` 서비스에는 경험에서 전역 조명을 업데이트하고 사용자 지정할 수 있는 속성이 포함되어 있습니다. 조명 속성은 다섯 가지 범주로 나눌 수 있습니다:

- [색상](#색상) &mdash; 경험 내 색조를 설정합니다.
- [강도](#강도) &mdash; 카메라에 닿는 빛의 강도 또는 양을 설정합니다.
- [그림자](#그림자) &mdash; 사용자 경험에서 그림자가 어떻게 표시되는지를 설정합니다.
- [환경](#환경) &mdash; 시간대 및 지리적 위도와 같은 경험 세계의 조건을 설정합니다.
- [기술](#기술) &mdash; 조명과 그림자를 렌더링하기 위해 Studio에서 사용하는 조명 기술을 설정합니다.

## 색상

### Ambient

`Ambient` 속성은 경험 전체의 색조를 설정합니다. 이 속성은 실외 및 실내 환경 모두에 영향을 미칩니다.

<Tabs>
<TabItem label="[0, 0, 0]">
<img src="../img/05_01_Global_Lighting/Ambient-0-0-0.jpg" width="800" height="450" alt="Ambient 속성이 [0, 0, 0]인 조명" />
</TabItem>
<TabItem label="[160, 80, 0]">
<img src="../img/05_01_Global_Lighting/Ambient-160-80-0.jpg" width="800" height="450" alt="Ambient 속성이 [160, 80, 0]인 조명" />
</TabItem>
<TabItem label="[25, 0, 125]">
<img src="../img/05_01_Global_Lighting/Ambient-25-0-125.jpg" width="800" height="450" alt="Ambient 속성이 [25, 0, 125]인 조명" />
</TabItem>
</Tabs>

### OutdoorAmbient

`OutdoorAmbient` 속성은 경험의 **실외** 영역에 색조를 설정합니다. 이는 실제 조명의 주변 색상이 하루 중 시간에 따라 어떻게 변하는지를 시뮬레이션하는 데 도움이 됩니다. 예를 들어, 이른 아침이나 늦은 오후의 햇빛은 보통 더 따뜻하고 핑크와 오렌지 색조가 더 많이 포함되어 있으며, 늦은 저녁은 보통 더 차갑고 파란색과 보라색 톤이 더 많습니다.

다음 이미지에서 차고와 카페 내부의 조명이 [Ambient](#ambient) 속성을 변경할 때와 달리 변하지 않는 것을 확인할 수 있습니다.

<Tabs>
<TabItem label="[255, 150, 50]">
<img src="../img/05_01_Global_Lighting/OutdoorAmbient-255-150-50.jpg" width="800" height="450" alt="OutdoorAmbient 속성이 [255, 150, 50]인 조명" />
</TabItem>
<TabItem label="[200, 150, 240]">
<img src="../img/05_01_Global_Lighting/OutdoorAmbient-200-150-240.jpg" width="800" height="450" alt="OutdoorAmbient 속성이 [200, 150, 240]인 조명" />
</TabItem>
<TabItem label="[0, 175, 255]">
<img src="../img/05_01_Global_Lighting/OutdoorAmbient-0-175-255.jpg" width="800" height="450" alt="OutdoorAmbient 속성이 [0, 175, 255]인 조명" />
</TabItem>
</Tabs>

### ColorShift_Top

`ColorShift_Top` 속성은 태양이나 달을 향한 표면에서 반사되는 색조를 설정합니다.

<Tabs>
<TabItem label="[0, 100, 255]">
<img src="../img/05_01_Global_Lighting/ColorShift-Top-0-100-255.jpg" width="800" height="450" alt="ColorShift_Top 속성이 [0, 100, 255]인 조명" />
</TabItem>
<TabItem label="[255, 60, 0]">
<img src="../img/05_01_Global_Lighting/ColorShift-Top-255-60-0.jpg" width="800" height="450" alt="ColorShift_Top 속성이 [255, 60, 0]인 조명" />
</TabItem>
</Tabs>

### ColorShift_Bottom

`ColorShift_Bottom` 속성은 태양이나 달을 향하지 않는 표면에서 반사되는 색조를 설정합니다.

다음 이미지에서 태양을 등지고 있는 사암 벽의 색조 변화를 확인할 수 있습니다.

<Tabs>
<TabItem label="[255, 0, 220]">
<img src="../img/05_01_Global_Lighting/ColorShift-Bottom-255-0-220.jpg" width="800" height="450" alt="ColorShift_Bottom 속성이 [255, 0, 220]인 조명" />
</TabItem>
<TabItem label="[0, 255, 190]">
<img src="../img/05_01_Global_Lighting/ColorShift-Bottom-0-255-190.jpg" width="800" height="450" alt="ColorShift_Bottom 속성이 [0, 255, 190]인 조명" />
</TabItem>
</Tabs>

<Alert severity="warning">
이 속성은 특히 미묘합니다. 경험에서 변화를 확인할 수 없다면 [Technology](#technology) 속성을 **Compatibility**로 변경하고 [Brightness](#brightness) 값을 높여보세요.
</Alert>

## 강도

### Brightness

`Brightness` 속성은 조명의 강도를 설정합니다. 이는 밝게 조명된 영역과 그림자 간의 대조를 증가시켜 밝은 햇빛과 따뜻한 날씨를 시뮬레이션하는 데 도움이 됩니다.

<Tabs>
<TabItem label="0.5">
<img src="../img/05_01_Global_Lighting/Brightness-0.5.jpg" width="800" height="450" alt="Brightness 속성이 0.5인 조명" />
</TabItem>
<TabItem label="1.5">
<img src="../img/05_01_Global_Lighting/Brightness-1.5.jpg" width="800" height="450" alt="Brightness 속성이 1.5인 조명" />
</TabItem>
<TabItem label="3.75">
<img src="../img/05_01_Global_Lighting/Brightness-3.75.jpg" width="800" height="450" alt="Brightness 속성이 3.75인 조명" />
</TabItem>
</Tabs>

### ExposureCompensation

`ExposureCompensation` 속성은 경험에 노출을 적용합니다. 노출은 카메라에 닿는 빛의 양을 나타냅니다.

낮은 값은 사진 촬영에서 과소 노출과 유사하며, 높은 값은 과노출과 유사합니다.

<Tabs>
<TabItem label="0">
<img src="../img/05_01_Global_Lighting/ExposureCompensation-0.jpg" width="800" height="450" alt="ExposureCompensation 속성이 0인 조명" />
</TabItem>
<TabItem label="-1">
<img src="../img/05_01_Global_Lighting/ExposureCompensation--1.jpg" width="800" height="450" alt="ExposureCompensation 속성이 -1인 조명" />
</TabItem>
<TabItem label="1.25">
<img src="../img/05_01_Global_Lighting/ExposureCompensation-1.25.jpg" width="800" height="450" alt="ExposureCompensation 속성이 1.25인 조명" />
</TabItem>
</Tabs>

## 그림자

### GlobalShadows

활성화되면 `GlobalShadows` 속성은 그림자를 렌더링합니다.

<Tabs>
<TabItem label="활성화됨">
<img src="../img/05_01_Global_Lighting/GlobalShadows-True.jpg" width="800" height="450" alt="GlobalShadows 속성이 활성화된 조명" />
</TabItem>
<TabItem label="비활성화됨">
<img src="../img/05_01_Global_Lighting/GlobalShadows-False.jpg" width="800" height="450" alt="GlobalShadows 속성이 비활성화된 조명" />
</TabItem>
</Tabs>

### ShadowSoftness

`ShadowSoftness` 속성은 그림자의 가장자리가 0(단단한 가장자리)에서 1(부드러운 가장자리)까지의 값으로 얼마나 흐릿한지를 조정합니다.

<Tabs>
<TabItem label="0">
<img src="../img/05_01_Global_Lighting/ShadowSoftness-0.jpg" width="800" height="450" alt="ShadowSoftness 속성이 0인 조명" />
</TabItem>
<TabItem label="1">
<img src="../img/05_01_Global_Lighting/ShadowSoftness-1.jpg" width="800" height="
450" alt="ShadowSoftness 속성이 1인 조명" />
</TabItem>
</Tabs>

## 환경

### ClockTime 및 TimeOfDay

`ClockTime` 및 `TimeOfDay` 속성은 모두 시간 단위로 현재 시간을 나타내며, 상호 연관되어 있습니다. 하나의 속성을 변경하면 다른 속성도 변경됩니다.

이 속성들 간의 유일한 차이점은 숫자 값입니다. `ClockTime`은 0시부터 24시까지의 시간을 나타내는 반면,
`TimeOfDay`는 24시간 문자열로 시간을 나타냅니다.

<Tabs>
<TabItem label="0 = 00:00:00">
<img src="../img/05_01_Global_Lighting/TimeOfDay-0.jpg" width="800" height="450" alt="ClockTime이 0 (TimeOfDay가 00:00:00)인 조명" />
</TabItem>
<TabItem label="6.3 = 06:18:00">
<img src="../img/05_01_Global_Lighting/TimeOfDay-6.3.jpg" width="800" height="450" alt="ClockTime이 6.3 (TimeOfDay가 06:18:00)인 조명" />
</TabItem>
<TabItem label="17 = 17:00:00">
<img src="../img/05_01_Global_Lighting/TimeOfDay-17.jpg" width="800" height="450" alt="ClockTime이 17 (TimeOfDay가 17:00:00)인 조명" />
</TabItem>
</Tabs>

<Alert severity="info">
이 속성들은 실제 시간의 흐름을 따르지 않으며, 스크립트를 통해 변경하지 않는 한 경험 동안에는 변하지 않습니다.
</Alert>

### GeographicLatitude

`GeographicLatitude` 속성은 위도를 도 단위로 나타냅니다. 이 속성은 태양과 달의 위치를 변경하지만 [`ClockTime`](#clocktime-및-timeofday) 및 [`TimeOfDay`](#clocktime-및-timeofday) 속성은 변경되지 않습니다.

<video src="../img/05_01_Global_Lighting/Geographic-Latitude.mp4" controls width="800" alt="360도 변화를 보여주는 GeographicLatitude 속성 변경 비디오"></video>

### EnvironmentDiffuseScale

`EnvironmentDiffuseScale` 속성은 환경에서 파생된 주변광의 양을 결정합니다.

다음 이미지에서 라면 가게 주방 내부의 주변광 변화에 주목하세요.

<Tabs>
<TabItem label="0">
<img src="../img/05_01_Global_Lighting/EnvironmentDiffuseScale-0.jpg" width="800" height="450" alt="EnvironmentDiffuseScale 속성이 0인 조명" />
</TabItem>
<TabItem label="1">
<img src="../img/05_01_Global_Lighting/EnvironmentDiffuseScale-1.jpg" width="800" height="450" alt="EnvironmentDiffuseScale 속성이 1인 조명" />
</TabItem>
</Tabs>

### EnvironmentSpecularScale

`EnvironmentSpecularScale` 속성은 환경에서 파생된 반사광의 양을 결정합니다. 값이 1에 가까울수록 매끄러운 객체가 환경을 더 잘 반사하고 금속이 더 현실적으로 보입니다.

<Tabs>
<TabItem label="0">
<img src="../img/05_01_Global_Lighting/EnvironmentSpecularScale-0.jpg" width="800" height="450" alt="EnvironmentSpecularScale 속성이 0인 조명" />
</TabItem>
<TabItem label="1">
<img src="../img/05_01_Global_Lighting/EnvironmentSpecularScale-1.jpg" width="800" height="450" alt="EnvironmentSpecularScale 속성이 1인 조명" />
</TabItem>
</Tabs>

## 기술

`Technology` 속성은 3D 환경을 렌더링하기 위한 조명 시스템을 결정합니다. 네 가지 조명 시스템이 있으며, 높은 품질에서 낮은 품질로 성능 영향이 순차적으로 나타납니다:

- **Future** &mdash; 고품질 조명과 그림자를 위한 가장 진보된 기술을 제공합니다.
  - 모든 유형의 조명에 대한 세부 그림자 지원을 확장하며, 태양 그림자에 대한 복잡한 그림자 기술과 점 조명에 대한 더 현실적인 조명 및 그림자 기술을 제공합니다.
  - 가장 현실적인 조명 모드이지만, 높은 품질로 인해 저사양 장치에서는 성능 저하가 발생할 수 있습니다.

- **ShadowMap** &mdash; 햇빛이나 방향성 광원에서 더 현실적이고 선명한 그림자를 생성하는 그림자 매핑을 특징으로 합니다. `PointLights`와 같은 다른 유형의 조명에 대해서는 정밀도와 성능 영향이 덜한 보셀 그리드를 사용합니다.

- **Voxel** &mdash; 3D 세계를 4&times;4&times;4 보셀 그리드로 나누어 빛과 그림자를 계산합니다.
  - 각 보셀은 작은 입방체 공간을 나타냅니다. 그리드는 각 보셀 내의 빛 존재 정보를 포함하고 빛이 3D 환경 및 객체와 상호작용하는 방식을 결정하는 데 도움이 됩니다.
  - 더 정밀하지 않은 조명과 **ShadowMap**과 같은 더 고급 그림자 매핑 기술에 비해 부드러운 그림자를 제공합니다.
  - 저사양 장치에만 권장됩니다.

- **Compatibility** (권장하지 않음) &mdash; **Voxel** 시스템을 사용하여 더 이상 지원되지 않는 레거시 기술을 시뮬레이션합니다.

<Tabs>
<TabItem label="Future">
<img src="../img/05_01_Global_Lighting/Technology-Future.jpg" width="800" height="450" alt="Technology 설정이 Future인 조명" />
</TabItem>
<TabItem label="ShadowMap">
<img src="../img/05_01_Global_Lighting/Technology-ShadowMap.jpg" width="800" height="450" alt="Technology 설정이 ShadowMap인 조명" />
</TabItem>
<TabItem label="Voxel">
<img src="../img/05_01_Global_Lighting/Technology-Voxel.jpg" width="800" height="450" alt="Technology 설정이 Voxel인 조명" />
</TabItem>
<TabItem label="Compatibility">
<img src="../img/05_01_Global_Lighting/Technology-Compatibility.jpg" width="800" height="450" alt="Technology 설정이 Compatibility인 조명" />
</TabItem>
</Tabs>

---
## 출처
 - [Global Lighting](https://create.roblox.com/docs/environment/lighting)

---
## [다음](./05_02_Atmospheric_Effects.md)