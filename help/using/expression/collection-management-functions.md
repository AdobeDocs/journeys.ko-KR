---
product: adobe campaign
title: 컬렉션 관리 기능
description: 컬렉션 관리 기능의 데이터 유형에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 1%

---

# 컬렉션 관리 기능 {#collection-management-functions}

표현식 언어에서는 컬렉션을 쿼리하기 위한 함수 집합도 소개합니다.

이러한 기능은 아래에 설명되어 있습니다. 다음 예제에서는 컬렉션을 포함하는 이벤트 페이로드를 사용하겠습니다.

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**함수 &quot;all(`<condition>`)&quot;**

**[!UICONTROL all]** 함수를 사용하면 부울 식을 사용하여 주어진 컬렉션에서 필터를 정의할 수 있습니다.

```json
<listExpression>.all(<condition>)
```

예를 들어 모든 앱 사용자 중에서 IOS 13(부울 표현식 &quot;IOS 13== 사용된 앱&quot;)을 사용하여 앱 사용자를 가져올 수 있습니다. 이 함수의 결과는 부울 표현식(예: 앱 사용자 1, 앱 사용자 34, 앱 사용자 432)과 일치하는 항목을 포함하는 필터링된 목록입니다.

Data Source 조건 활동에서 **[!UICONTROL all]** 함수의 결과가 null인지 여부를 확인할 수 있습니다. 이 **[!UICONTROL all]** 함수를 **[!UICONTROL count]**&#x200B;과(와) 같은 다른 함수와 결합할 수도 있습니다. 자세한 내용은 [데이터 Source 조건 활동](../building-journeys/condition-activity.md#data_source_condition)을 참조하세요.

**예 1:**

사용자가 특정 버전의 애플리케이션을 설치했는지 확인하려고 합니다. 이를 위해 버전이 1.0인 모바일 애플리케이션과 연결된 모든 푸시 알림 토큰을 가져옵니다. 그런 다음 **[!UICONTROL count]** 함수로 조건을 수행하여 반환된 토큰 목록에 하나 이상의 요소가 포함되어 있는지 확인합니다.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

결과는 true입니다.

**예 2:**

여기에서는 **[!UICONTROL count]** 함수를 사용하여 컬렉션에 푸시 알림 토큰이 있는지 확인합니다.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

그 결과는 참이 될 것이다.

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>**all()** 함수의 필터링 조건이 비어 있으면 필터가 목록에 있는 모든 요소를 반환합니다. **그러나 컬렉션의 요소 수를 계산하려면 all 함수가 필요하지 않습니다.**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

식의 결과는 **3**&#x200B;입니다.

**예 3:**

여기에서는 개인이 지난 24시간 내에 어떤 연락도 받지 않았는지 확인합니다. 컬렉션의 두 요소를 기반으로 하는 두 개의 표현식을 사용하여 ExperiencePlatform 데이터 소스에서 검색된 경험 이벤트 컬렉션을 필터링합니다. 특히 이벤트의 타임스탬프는 **[!UICONTROL nowWithDelta]** 함수에서 반환된 dateTime과 비교됩니다.

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

두 조건과 일치하는 경험 이벤트가 없으면 결과는 true가 됩니다.

**예 4:**

여기에서는 개인이 자습서를 시작할 수 있도록 푸시 알림을 트리거하기 위해 지난 7일 동안 애플리케이션을 최소 한 번 시작했는지 확인하려고 합니다.

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]**&#x200B;은(는) 이벤트 컬렉션 및 **currentDataPackField**&#x200B;을 조작할 때만 사용할 수 있습니다.
>데이터 소스 컬렉션을 조작할 때. **[!UICONTROL all]**, **[!UICONTROL first]** 및 **[!UICONTROL last]**(으)로 컬렉션을 처리할 때
>컬렉션의 각 요소를 하나씩 반복합니다. **[!UICONTROL currentEventField]** 및 **currentDataPackField**
>루핑되는 요소에 해당합니다.

**함수 &quot;first(`<condition>`)&quot; 및 &quot;last(`<condition>`)&quot;**

**[!UICONTROL first]** 및 **[!UICONTROL last]** 함수는 필터를 충족하는 목록의 첫 번째/마지막 요소를 반환하면서 컬렉션에서 필터를 정의할 수도 있습니다.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**예 1:**

이 표현식은 버전이 1.0인 모바일 애플리케이션과 연결된 첫 번째 푸시 알림 토큰을 반환합니다.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

결과는 &quot;token_1&quot;입니다.

**예 2:**

이 표현식은 버전이 1.0인 모바일 애플리케이션과 연결된 마지막 푸시 알림 토큰을 반환합니다.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

결과는 &quot;token_2&quot;입니다.

>[!NOTE]
>
>경험 이벤트는 Adobe Experience Platform에서 역시간 순서로 컬렉션으로 검색되므로
>
>* **[!UICONTROL first]** 함수는 가장 최근 이벤트를 반환합니다.
>* **[!UICONTROL last]** 함수는 가장 오래된 함수를 반환합니다.

**예 3:**

DMA ID에 대해 0이 아닌 값이 있는 첫 번째(가장 최근) Adobe Analytics 이벤트의 값이 602와 같은지 확인합니다.

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**함수 &quot;at(`<index>`)&quot;**

**[!UICONTROL at]** 함수를 사용하면 인덱스에 따라 컬렉션의 특정 요소를 참조할 수 있습니다.
색인 0은 컬렉션의 첫 번째 색인입니다.

_`<listExpression>`.at(`<index>`)_

**예:**

이 표현식은 목록의 두 번째 푸시 알림 토큰을 반환합니다.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

결과는 &quot;token_2&quot;입니다.

**다른 예**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
