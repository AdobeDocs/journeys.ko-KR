---
product: adobe campaign
solution: Journey Orchestration
title: 고급 표현식 편집기 사용
description: 고급 표현식을 작성하는 방법에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# 고급 표현식 예제

고급 표현식 편집기를 사용하여 여정에서 사용자를 필터링할 수 있는 조건을 만들 수 있습니다. 이러한 조건을 통해 시간, 날짜, 위치, 기간 또는 장바구니 구매 또는 포기와 같은 작업을 기준으로 사용자를 타깃팅하여 장바구니에서 재타깃팅할 수 있습니다.

>[!NOTE]
>
>이벤트는 @, 데이터 소스는 #.

## 경험 이벤트에 대한 구축 조건

고급 표현식 편집기는 구매 목록 또는 메시지 과거 클릭 수와 같은 시간 시리즈에 대한 쿼리를 반드시 수행해야 합니다. 이러한 쿼리는 단순 편집기를 사용하여 수행할 수 없습니다.

경험 이벤트는 Adobe Experience Platform에서 시간순 반대로 컬렉션으로 검색되므로, 다음과 같이 됩니다.

* 첫 번째 함수는 가장 최근 이벤트를 반환합니다.
* 마지막 함수는 가장 오래된 함수를 반환합니다.

예를 들어 고객이 매장 근처에 도착하면 메시지(장바구니 포기 후 최근 7일 동안 고객을 타깃팅하여 장바구니에 담긴 상품을 제공한다고 가정해 봅시다.

**다음 조건을 빌드해야 합니다.**

우선 온라인 스토어를 탐색했지만 지난 7일 동안 주문을 완료하지 않은 고객을 타깃팅합니다.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**이 표현식은 지난 7일 동안 지정된 이 사용자에 대한 모든 이벤트를 찾습니다.**

그런 다음 completePurchase로 전환되지 않은 모든 장바구니 이벤트를 선택합니다.

>[!NOTE]
>
>식에 필드를 빠르게 삽입하려면 편집기의 왼쪽 패널에서 필드를 두 번 클릭합니다.

지정된 타임스탬프가 날짜 시간 값 역할을 하며, 두 번째 타임스탬프는 일 수입니다.

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

이 표현식은 부울 값을 반환합니다.

**이제 제품 재고가 있는지 확인하는 표현식을 만들어 보겠습니다**

* Inventory에서 이 표현식은 제품의 수량 필드를 검색하고 0보다 커야 합니다.

`#{Inventory.fieldgroup3.quantity} > 0`

* 오른쪽에서 필요한 값이 지정되며 여기에서 &quot;ArcomeLumaStudio&quot; 이벤트 위치에서 매핑되는 스토어의 위치를 검색해야 합니다.

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 그리고 `first` 함수를 사용하여 SKU를 지정하여 가장 최근의 &quot;addToCart&quot; 상호 작용을 검색합니다.

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

여기에서 제품이 매장 상태가 아닌 경우 여정에서 다른 경로를 추가하고 참여 오퍼와 함께 알림을 보낼 수 있습니다. 그에 따라 메시지를 구성하고 개인화 데이터를 사용하여 메시지 대상을 향상시킵니다.

## 고급 표현식 편집기를 사용한 문자열 조작 예

**조건**

이 조건은 &quot;Arlington&quot;에서 트리거된 gefoence 이벤트만 검색합니다.

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

설명:이것은 `Is sensitive`이 선택된 상태로 `equal to`을 사용하는 단순 모드의 쿼리와 동일한 엄격한 문자열 비교(대/소문자 구분)입니다.

`Is sensitive`이 선택 취소된 것과 동일한 쿼리는 고급 모드에서 다음 표현식을 생성합니다.

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**작업 중**

다음 표현식을 사용하여 작업 개인화 필드에서 CRM ID를 정의할 수 있습니다.

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

설명:이 예제에서는 `substr` 및 `lastIndexOf` 함수를 사용하여 모바일 앱 시작 이벤트로 전달된 CRM ID를 포함하는 중괄호를 제거합니다.

고급 표현식 편집기를 사용하는 방법에 대한 자세한 내용은 [이 비디오](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)를 참조하십시오.
