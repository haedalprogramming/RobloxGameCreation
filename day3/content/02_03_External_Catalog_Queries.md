# External Catalog Queries

## 목차
- [External Catalog Queries](#external-catalog-queries)
  - [목차](#목차)
  - [크리에이터 스토어 API](#크리에이터-스토어-api)
    - [쿼리 매개 변수](#쿼리-매개-변수)
    - [응답 필드](#응답-필드)
  - [마켓플레이스 API](#마켓플레이스-api)
    - [쿼리 매개 변수](#쿼리-매개-변수-1)
    - [응답 필드](#응답-필드-1)
  - [출처](#출처)
  - [다음](#다음)

---

Roblox의 에셋을 Studio 외부에서 검색하려면 외부 카탈로그 API에 접근할 수 있습니다. [크리에이터 스토어 API](#크리에이터-스토어-api)를 사용하여 Studio 에셋(메시, 모델, 오디오 등)을 쿼리하고, [마켓플레이스 API](#마켓플레이스-api)를 사용하여 마켓플레이스에서 아바타 에셋을 쿼리할 수 있습니다.

각 API는 특정 카탈로그에 대해 URL과 사용자 정의 검색 매개 변수가 필요합니다. URL과 매개 변수가 모두 유효하면 API는 검색 결과를 JSON 형식으로 반환합니다.

## 크리에이터 스토어 API

다음 URL을 사용하여 크리에이터 스토어 카탈로그에서 항목을 쿼리할 수 있습니다:
`https://search.roblox.com/catalog/json?[params]`

적절한 [쿼리 매개 변수](#쿼리-매개-변수)로 `[params]`를 교체하여 검색을 사용자 정의할 수 있습니다.

### 쿼리 매개 변수

매개 변수와 값을 URL에 추가하여 일련의 매개 변수와 값을 지정할 수 있으며, 각각은 `&`로 구분됩니다.

크리에이터 스토어 카탈로그를 쿼리하려면 다음 매개 변수를 사용하십시오:

<table>
<thead>
  <tr>
    <th>매개 변수</th>
    <th>유형</th>
    <th>옵션 및 값</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Category</td>
    <td>byte</td>
    <td>`6` = 모델 <br />`7` = 플러그인 <br />`8` = 데칼 <br />`9` = 오디오 <br />`10` = 메시</td>
  </tr>
  <tr>
    <td>CreatorID</td>
    <td>long</td>
    <td>검색에 `UserID`를 지정합니다. 그룹이 만든 항목을 찾으려면 그룹 에이전트의 ID를 입력하고, 그룹 ID를 입력하지 마십시오.</td>
  </tr>
  <tr>
    <td>CurrencyType</td>
    <td>byte</td>
    <td>`0` = 모두 (기본값) <br />`3` = CustomRobux <br />`5` = 무료 <br /> <br /> CustomRobux는 사용자 정의 PxMax 및 PxMin 값을 사용합니다. </td>
  </tr>
  <tr>
    <td>Genres</td>
    <td>byte</td>
    <td>검색에 장르를 지정합니다. 카탈로그 페이지의 URL과 일치시키는 것이 장르를 필터링하는 권장 방법입니다. <br />`1` = TownAndCity <br />`2` = Medieval <br />`3` = SciFi <br />`4` = Fighting <br />`5` = Horror <br />`6` = Naval <br />`7` = Adventure <br />`8` = Sports <br />`9` = Comedy <br />`10` = Western <br />`11` = Military <br />`13` = Building <br />`14` = FPS <br />`15` = RPG </td>
  </tr>
  <tr>
    <td>Keyword</td>
    <td>string</td>
    <td>일반적인 키워드 검색.</td>
  </tr>
  <tr>
    <td>PageNumber</td>
    <td>int</td>
    <td>`ResultsPerPage`와 함께 페이지 번호를 지정하여 결과를 페이지별로 나눕니다.</td>
  </tr>
  <tr>
    <td>PxMax</td>
    <td>int</td>
    <td>쿼리 항목의 최대 가격을 로벅스로 지정합니다.</td>
  </tr>
  <tr>
    <td>PxMin</td>
    <td>int</td>
    <td>쿼리 항목의 최소 가격을 로벅스로 지정합니다.</td>
  </tr>
  <tr>
    <td>ResultsPerPage</td>
    <td>int</td>
    <td>기본적으로 현재 각 카탈로그 탐색 페이지에 표시되는 항목과 동일합니다. 이 최대 수보다 큰 값을 지정할 수 없습니다.</td>
  </tr>
  <tr>
    <td>SortAggregation</td>
    <td>byte</td>
    <td>`0` = 지난 하루 <br />`1` = 지난 주 <br />`2` = 지난 달 <br />`3` = 전체 기간</td>
  </tr>
  <tr>
    <td>SortType</td>
    <td>byte</td>
    <td>`0` = 관련성 (기본값)<br />`1` = 가장 좋아요 많은 순 <br />`2` = 베스트셀러 <br />`3` = 최근 업데이트 <br />`4` = 가격 낮은 순 <br />`5` = 가격 높은 순</td>
  </tr>
</tbody>
</table>

다음 URL은 "모델" 하위 카테고리에서 10개의 항목을 검색하며, 가장 최근에 업데이트된 순서로 정렬합니다.

`https://search.roblox.com/catalog/json?Category=6&SortType=3&ResultsPerPage=10`

### 응답 필드

API 응답은 JSON 형식으로 반환됩니다. 응답은 다음 주요 필드를 포함한 에셋 세부 정보를 제공합니다:

<table>
<thead>
  <tr>
    <th>필드</th>
    <th>설명</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>AssetTypeID</td>
    <td>에셋 유형 값. <br />`3` = 오디오<br />`4` = 메시<br />`5` = Lua<br />`10` = 모델<br />`13` = 데칼<br />`21` = 배지<br />`24` = 애니메이션<br />`34` = 게임패스<br />`38` = 플러그인<br />`40` = 메시파트</td>
  </tr>
  <tr>
    <td>BestPrice</td>
    <td>한정판 항목을 제외하고는 비어 있습니다. 한정판 항목의 경우 최적의 가격을 반환합니다.</td>
  </tr>
  <tr>
    <td>ContentRatingTypeID</td>
    <td>`0` = 콘텐츠 등급 유형 없음<br />`1` = 13세 이상 등급 항목</td>
  </tr>
  <tr>
    <td>CreatedDate</td>
    <td>항목이 생성된 날짜 (UTC 형식).</td>
  </tr>
  <tr>
    <td>MinimumMembershipLevel</td>
    <td>`1` = 모든 멤버십<br />`4` = <a href="https://www.roblox.com/premium/membership">Roblox 프리미엄</a> 전용</td>
  </tr>
  <tr>
    <td>Name</td>
    <td>UTF-8 형식의 항목 이름.</td>
  </tr>
  <tr>
    <td>PriceView</td>
    <td>주로 웹사이트에서 가격을 표시하는 데 사용됩니다. 옵션은 다음과 같습니다:<br />`0` = 무료<br />`1` = 수집 가능<br />`2` = 가격 있음<br />`3` = 판매 불가</td>
  </tr>
  <tr>
    <td>PrivateSales</td>
    <td>한정판 항목의 경우를 제외하고는 비어 있습니다. 한정판 항목의 경우 개인 판매자의 수를 반환합니다.</td>
  </tr>
  <tr>
    <td>UpdatedDate</td>
    <td>항목이 마지막으로 업데이트된 날짜 (UTC 형식).</td>
  </tr>
</tbody>
</table>

다음은 단일 항목에 대한 예상 반환 출력의 예입니다:

```json
{
	"AssetId": 3374795585,
	"Name": "Rat",
	"Description": "",
	"AbsoluteUrl": "https://www.roblox.com/catalog/3374795585/Rat",
	"Price": "",
	"Updated": "8 months ago",
	"Favorited": "80 times",
	"Sales": "1,613",
	"Remaining": "",
	"Creator": "ROBLOX",
	"CreatorAbsoluteUrl": "https://www.roblox.com/users/1/profile",
	"PrivateSales": "",
	"PriceView": 0,
	"BestPrice": "",
	"ContentRatingTypeID": 0,
	"IsServerSideThumbnailLookupInCatalogEnabled": true,
	"AudioUrl": null,
	"IsLargeItem": false,
	"IsThumbnailFinal": true,
	"IsThumbnailUnapproved": false,
	"ThumbnailUrl": "https://t1.rbxcdn.com/745a4be8c2366db2e55d0a67678434dc",
	"BcOverlayUrl": null,
	"LimitedOverlayUrl": null,
	"DeadlineOverlayUrl": null,
	"LimitedAltText": null,
	"NewOverlayUrl": null,
	"SaleOverlayUrl": null,
	"IosOverlayUrl": null,
	"XboxOverlayUrl": null,
	"GooglePlayOverlayUrl": null,
	"AmazonOverlayUrl": null,
	"IsTransparentBackground": false,
	"IsNewRobuxIconEnabled": true,
	"AssetTypeID": 10,
	"CreatorID": 1,
	"CreatedDate": "/Date(1561635090927)/",
	"UpdatedDate": "/Date(1562003916210)/",
	"IsForSale": false,
	"IsPublicDomain": true,
	"IsLimited": false,
	"IsLimitedUnique": false,
	"MinimumMembershipLevel": 0,
	"OffSaleDeadline": null,
	"ProductId": 586905093
}
```

## 마켓플레이스 API

다음 URL을 사용하여 마켓플레이스에서 아바타 항목을 쿼리할 수 있습니다:
`https://catalog.roblox.com/v1/search/items/details?[params]`

적절한 [쿼리 매개 변수](#쿼리-매개-변수-1)로 `[params]`를 교체하여 검색을 사용자 정의할 수 있습니다.

### 쿼리 매개 변수

매개 변수와 값을 URL에 추가하여 일련의 매개 변수와 값을 지정할 수 있으며, 각각은 `&`로 구분됩니다.

마켓플레이스를 쿼리하려면 다음 매개 변수를 사용하십시오:

<table>
<thead>
  <tr>
    <th>매개 변수</th>
    <th>유형</th>
    <th>옵션 및 값</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Category</td>
    <td>byte</td>
    <td>`0` = 추천<br />`1` = 모두<br />`2` = 수집품<br />`3` = 의류<br />`4` = 신체 부위<br />`5` = 장비<br />`11` = 액세서리<br />`12` = 아바타 애니메이션<br />`13` = 커뮤니티 창작물</td>
  </tr>
  <tr>
    <td>CreatorName</td>
    <td>string</td>
    <td>창작자 이름으로 검색. `Enum.CreatorType`이 제공되지 않으면 검색은 사용자만 대상으로 합니다.</td>
  </tr>
  <tr>
    <td>CreatorTargetId</td>
    <td>long</td>
    <td>제공된 CreatorType에 따라 사용자 또는 그룹 ID.</td>
  </tr>
  <tr>
    <td>CreatorType</td>
    <td>byte</td>
    <td>`1` = 사용자 또는 `2` = 그룹.</td>
  </tr>
  <tr>
    <td>Cursor</td>
    <td>string</td>
    <td>각 검색 응답에는 다음 페이지가 있는 경우 `nextPageCursor`와 이전 페이지가 있는 경우 `previousPageCursor`가 포함됩니다. 다음 또는 이전 페이지의 결과를 얻으려면 다음 쿼리에 Cursor 매개 변수로 이러한 값을 전달합니다. 커서가 유효하려면 다른 쿼리 매개 변수가 동일하게 유지되어야 합니다.</td>
  </tr>
  <tr>
    <td>Genres</td>
    <td>byte</td>
    <td>검색에 장르를 지정합니다. 카탈로그 페이지의 URL과 일치시키는 것이 장르를 필터링하는 권장 방법입니다. <br />`1` = TownAndCity<br />`2` = Medieval<br />`3` = SciFi<br />`4` = Fighting<br />`5` = Horror<br />`6` = Naval<br />`7` = Adventure<br />`8` = Sports<br />`9` = Comedy<br />`10` = Western<br />`11` = Military<br />`13` = Building<br />`14` = FPS<br />`15` = RPG</td>
  </tr>
  <tr>
    <td>Keyword</td>
    <td>string</td>
    <td>일반적인 키워드 검색.</td>
  </tr>
  <tr>
    <td>Limit</td>
    <td>int</td>
    <td>반환할 결과의 수. 현재 값은 10, 28, 30으로 제한됩니다.</td>
  </tr>
  <tr>
    <td>MaxPrice</td>
    <td>int</td>
    <td>쿼리 항목의 최대 가격을 로벅스로 지정합니다.</td>
  </tr>
  <tr>
    <td>MinPrice</td>
    <td>int</td>
    <td>쿼리 항목의 최소 가격을 로벅스로 지정합니다.</td>
  </tr>
  <tr>
    <td>SortAggregation</td>
    <td>byte</td>
    <td>`1` = 지난 하루<br />`3` = 지난 주<br />`4` = 지난 달<br />`5` = 전체 기간</td>
  </tr>
  <tr>
    <td>SortType</td>
    <td>byte</td>
    <td>`0` = 관련성 (기본값)<br />`1` = 좋아요 순<br />`2` = 판매량<br />`3` = 업데이트<br />`4` = 가격 오름차순<br />`5` = 가격 내림차순 </td>
  </tr>
  <tr>
    <td>Subcategory</td>
    <td>byte</td>
    <td>
    `0` = 추천<br />
    `1` = 모두<br />
    `2` = 수집품<br />
    `3` = 의류<br />
    `4` = 신체 부위<br />
    `5` = 장비<br />
    `9` = 모자<br />
    `10` = 얼굴<br />
    `12` = 셔츠<br />
    `13` = 티셔츠<br />
    `14` = 바지<br />
    `15` = 머리<br />
    `19` = 액세서리<br />
    `20` = 머리 액세서리<br />
    `21` = 얼굴 액세서리<br />
    `22` = 목 액세서리<br />
    `23` = 어깨 액세서리<br />
    `24` = 앞 액세서리<br />
    `25` = 뒤 액세서리<br />
    `26` = 허리 액세서리<br />
    `27` = 아바타 애니메이션<br />
    `37` = 번들<br />
    `38` = 애니메이션 번들 <br />
    `39` = 이모트 애니메이션<br />
    `40` = 커뮤니티 창작물<br />
    `41` = 근접 무기<br />
    `42` = 원거리 무기<br />
    `43` = 폭발물<br />
    `44` = 파워업<br />
    `45` = 네비게이션<br />
    `46` = 악기<br />
    `47` = 소셜<br />
    `48` = 건축<br />
    `49` = 운송<br />
    `54` = 머리 액세서리<br />
    `55` = 클래식 티셔츠<br />
    `56` = 클래식 셔츠<br />
    `57` = 클래식 바지<br />
    `58` = 티셔츠 액세서리<br />
    `59` = 셔츠 액세서리<br />
    `60` = 바지 액세서리<br />
    `61` = 재킷 액세서리<br />
    `62` = 스웨터 액세서리<br />
    `63` = 반바지 액세서리<br />
    `64` = 신발 번들<br />
    `65` = 드레스/치마 액세서리<br />
    `66` = 다이내믹 헤드<br />
    </td>

  </tr>
</tbody>
</table>

다음 URL은 Roblox("CreatorTargetId")가 만든 "액세서리"의 "장비" 항목 중 첫 번째 10개를 모든 기간("SortAggregation")과 관련성("SortType")으로 정렬하여 검색합니다:

`https://catalog.roblox.com/v1/search/items/details?Category=11&Subcategory=5&CreatorTargetId=1&SortType=0&SortAggregation=5&Limit=10`

### 응답 필드

API 응답은 JSON 형식으로 반환됩니다. 응답은 `data` 키를 사용하여 다음 필드를 포함한 에셋 세부 정보를 제공합니다:

<table>
<thead>
  <tr>
    <th>필드</th>
    <th>설명</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>assetType</td>
    <td>다음 에셋 유형 값 중 하나 (항목이 에셋인 경우에만 반환됨).<br />`2` = 티셔츠<br />`8` = 모자<br />`11` = 셔츠<br />`12` = 바지<br />`17` = 머리<br />`18` = 얼굴<br />`19` = 장비<br />`25` = 팔<br />`26` = 다리<br />`27` = 상체<br />`28` = 오른팔<br />`29` = 왼팔<br />`30` = 왼다리<br />`31` = 오른다리<br />`41` = 머리 액세서리<br />`42` = 얼굴 액세서리<br />`43` = 목 액세서리<br />`44` = 어깨 액세서리<br />`45` = 앞 액세서리<br />`46` = 뒤 액세서리<br />`47` = 허리 액세서리<br />`48` = 등반 애니메이션<br />`49` = 죽음 애니메이션<br />`50` = 낙하 애니메이션<br />`51` = 대기 애니메이션<br />`52` = 점프 애니메이션<br />`53` = 달리기 애니메이션<br />`54` = 수영 애니메이션<br />`55` = 걷기 애니메이션<br />`56` = 포즈 애니메이션<br />`61` = 이모트 애니메이션</td>
  </tr>
  <tr>
    <td>bundleType</td>
    <td>번들 유형 ID (항목이 번들인 경우에만 반환됨). 가능한 값은 `BodyParts`와 `AvatarAnimations`입니다.</td>
  </tr>
  <tr>
    <td>creatorName</td>
    <td>창작자의 이름.</td>
  </tr>
  <tr>
    <td>creatorTargetId</td>
    <td>창작자의 ID.</td>
  </tr>
  <tr>
    <td>creatorType</td>
    <td>항목의 창작자 유형.</td>
  </tr>
  <tr>
    <td>description</td>
    <td>항목 설명.</td>
  </tr>
  <tr>
    <td>favoriteCount</td>
    <td>항목의 좋아요 수.</td>
  </tr>
  <tr>
    <td>genres</td>
    <td>항목의 장르 목록. 가능한 값은 `All`, `Tutorial`, `Scary`, `TownAndCity`, `War`, `Funny`, `Fantasy`, `Adventure`, `SciFi`, `Pirate`, `FPS`, `RPG`, `Sports`, `Ninja`, `WildWest` 등이 있습니다.</td>
  </tr>
  <tr>
    <td>id</td>
    <td>항목의 ID.</td>
  </tr>
  <tr>
    <td>itemRestrictions</td>
    <td>항목의 제한 목록. 가능한 값은 `ThirteenPlus`, `LimitedUnique`, `Limited`, `Rthro` 등이 있습니다.</td>
  </tr>
  <tr>
    <td>itemStatus</td>
    <td>항목의 상태 플래그 목록. 가능한 값은 `New`, `Sale`, `XboxExclusive`, `AmazonExclusive`, `GooglePlayExclusive`, `IosExclusive`, `SaleTimer` 등이 있습니다.</td>
  </tr>
  <tr>
    <td>itemType</td>
    <td>항목 유형. 가능한 값은 `Asset` 또는 `Bundle`입니다.</td>
  </tr>
  <tr>
    <td>lowestPrice</td>
    <td>항목이 재판매 가능한 경우 항목의 최저 재판매 가격 (재판매 가능한 항목인 경우에만 반환됨).</td>
  </tr>
  <tr>
    <td>name</td>
    <td>항목의 이름.</td>
  </tr>
  <tr>
    <td>price</td>
    <td>항목의 목록 가격 (현재 가격은 항목이 재판매 가능한 경우 다를 수 있음).</td>
  </tr>
  <tr>
    <td>priceStatus</td>
    <td>판매 중이지 않은 항목의 가격 상태. 가능한 값은 `Free`, `OffSale`, `NoResellers`입니다.</td>
  </tr>
  <tr>
    <td>purchaseCount</td>
    <td>항목의 구매 수.</td>
  </tr>
  <tr>
    <td>unitsAvailableForConsumption</td>
    <td>한정판 유니크 항목의 소비 가능 단위.</td>
  </tr>
</tbody>
</table>

다음은 단일 항목에 대한 예상 반환 출력의 예입니다:

```json
{
	"keyword": null,
	"previousPageCursor": null,
	"nextPageCursor": "2_1_c541d05046b5c1c78a5d386b5e302243",
	"data": [
    {
        "id":527373900,
        "itemType":
        "Asset",
        "assetType":42,
        "name":"Restless Souls Bandana",
        "description":"This bandana won't help you blend in with ghosts, but at least you'll be stylish.",
        "productId":41270974,
        "genres":[
          "Scary",
          "Adventure"
          ],
        "itemStatus":[],
        "itemRestrictions":[],
        "creatorType":"User",
        "creatorTargetId":1,
        "creatorName":"Roblox",
        "price":300,
        "favoriteCount":15943,
        "offSaleDeadline":null
        }
	]
}
```

---
## 출처
 - [External Catalog Queries](https://create.roblox.com/docs/projects/assets/api)

---
## [다음](./02_04_Packages.md)