---
product: adobe campaign
title: 고급 표현식 편집기 사용
description: 고급 표현식을 작성하는 방법에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 고급 표현식 예

고급 표현식 편집기를 사용하여 여정에서 사용자를 필터링할 수 있는 조건을 만들 수 있습니다. 이러한 조건을 사용하면 여정에서 재타겟팅할 수 있도록 시간, 날짜, 위치, 기간 또는 장바구니 구매나 포기 등의 조치를 통해 사용자를 타깃팅할 수 있습니다.

>[!NOTE]
>
>이벤트는 @, 데이터 소스는 #.

## 경험 이벤트에 대한 조건 작성

고급 표현식 편집기는 구매 목록 또는 메시지 과거 클릭 수와 같은 시계열에 대한 쿼리를 수행해야 합니다. 단순 편집기를 사용하여 이러한 쿼리를 수행할 수 없습니다.

경험 이벤트는 Adobe Experience Platform에서 시간 순서대로 컬렉션으로 검색되므로,

* 첫 번째 함수는 가장 최근 이벤트를 반환합니다
* 마지막 함수는 가장 오래된 함수를 반환합니다.

예를 들어 고객이 스토어에 가까워지면 장바구니에 저장된 항목에 대한 오퍼와 함께 메시지를 보낼 수 있도록 지난 7일 동안 장바구니 포기 고객을 타겟팅한다고 가정합니다.

**다음 조건을 빌드해야 합니다.**

먼저, 온라인 스토어를 탐색했지만 지난 7일 동안 주문을 확정하지 않은 고객을 타깃팅합니다.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**이 표현식은 지난 7일 동안 지정된 이 사용자에 대한 모든 이벤트를 찾습니다.**

그런 다음 completePurchase로 변환되지 않은 모든 장바구니 이벤트를 선택합니다.

>[!NOTE]
>
>표현식에 필드를 빠르게 삽입하려면 편집기 왼쪽 패널의 필드를 두 번 클릭합니다.

지정한 타임스탬프가 날짜 시간 값으로 작동하며, 두 번째는 일 수입니다.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

이 표현식은 부울을 반환합니다.

**이제 제품이 재고가 있는지 확인하는 표현식을 만들어 보겠습니다**

* Inventory에서 이 표현식은 제품의 수량 필드를 찾아서 0보다 커야 함을 지정합니다.

`#{Inventory.fieldgroup3.quantity} > 0`

* 오른쪽에서는 필요한 값이 지정되며, 여기에서 &quot;DeliveryLumaStudio&quot; 이벤트의 위치에서 매핑되는 저장소의 위치를 검색해야 합니다.

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 및 함수를 사용하여 SKU를 지정합니다 `first` 가장 최근 &quot;addToCart&quot; 상호 작용을 검색하려면

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

여기에서 제품이 매장 되어 있지 않을 경우에 대한 여정에 다른 경로를 추가하여 참여 오퍼와 함께 알림을 보낼 수 있습니다. 그에 따라 메시지를 구성하고 개인화 데이터를 사용하여 메시지 타겟을 강화합니다.

## 고급 표현식 편집기를 사용한 문자열 조정의 예

**조건**

이 조건은 &quot;Arlington&quot;에서 트리거된 지오펜스 이벤트만 검색합니다.

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

설명: 이는 를 사용하는 단순 모드의 질의와 동일한 엄격한 문자열 비교(대/소문자 구분)입니다 `equal to` with `Is sensitive` 확인됨.

과 동일한 쿼리 `Is sensitive` 선택 취소하면 고급 모드에서 다음 표현식이 생성됩니다.

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**작업**

다음 표현식을 사용하면 작업 개인화 필드에서 CRM ID를 정의할 수 있습니다.

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

설명: 이 예에서는 을 사용합니다 `substr` 및 `lastIndexOf` 모바일 앱 실행 이벤트와 함께 전달된 CRM ID를 포함하는 중괄호를 제거하는 함수입니다.

고급 표현식 편집기를 사용하는 방법에 대한 자세한 내용은 [이 비디오](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
