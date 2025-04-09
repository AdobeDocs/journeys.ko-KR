---
product: adobe campaign
title: Using Adobe Campaign actions
description: Learn about Adobe Campaign actions
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Adobe Campaign Standard 사용 {#using_campaign_action}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._



Adobe Campaign Standard이 있는 경우 다음과 같은 기본 작업 활동을 사용할 수 있습니다. **[!UICONTROL Email]**, **[!UICONTROL Push]** 및 **[!UICONTROL SMS]**.

>[!NOTE]
>
>이를 위해서는 기본 작업을 구성해야 합니다. [이 페이지](../action/working-with-adobe-campaign.md)를 참조하십시오.

이러한 각 채널에 대해 Adobe Campaign Standard 트랜잭션 메시지 **템플릿**&#x200B;을(를) 선택합니다. [!DNL Journey Orchestration]은(는) 메시지 전송 솔루션이 아닙니다. 기본 제공 이메일, SMS 및 푸시 채널의 경우 트랜잭션 메시지를 사용하여 메시지 전송을 실행합니다. 즉, 여정에서 특정 메시지 템플릿을 사용하려면 Adobe Campaign Standard에 게시해야 합니다. 이 기능을 사용하는 방법에 대해 알아보려면 [이 페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ko)를 참조하세요.

>[!NOTE]
>
>Journey Orchestration에서 사용하려면 Campaign Standard 트랜잭션 메시지와 관련 이벤트를 게시해야 합니다. 이벤트가 게시되었지만 메시지는 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되었지만 연결된 이벤트가 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지만 사용할 수 없습니다.

![](../assets/journey59.png)

이벤트(실시간 이라고도 함) 또는 프로필 트랜잭션 메시지 템플릿을 사용할 수 있습니다.

>[!NOTE]
>
>실시간 트랜잭션 메시지(rtEvent)를 보내거나 사용자 지정 작업 덕분에 서드파티 시스템으로 메시지를 라우팅하는 경우 피로, 차단 목록 또는 구독 취소 관리에 특정 설정이 필요합니다. 예를 들어 &quot;구독 취소&quot; 속성이 Adobe Experience Platform 또는 서드파티 시스템에 저장된 경우 이 조건을 확인하려면 메시지를 보내기 전에 조건을 추가해야 합니다.

템플릿을 선택하면 메시지 페이로드에 필요한 모든 필드가 **[!UICONTROL Address]** 및 **[!UICONTROL Personalization Data]** 아래의 활동 구성 창에 표시됩니다. 이러한 각 필드를 이벤트 또는 데이터 소스에서 사용할 필드에 매핑해야 합니다. You can also use the advanced expression editor to pass a value manually, perform data manipulation on retrieved information (for example convert a string to uppercase) or use functions such as &quot;if, then, else&quot;. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

![](../assets/journey60.png)

## Email and SMS {#section_asc_51g_nhb}

For **[!UICONTROL Email]** and **[!UICONTROL SMS]**, the parameters are identical.

>[!NOTE]
>
>For email, if you&#39;re using a profiles transactional template, the unsubscription mechanism is handled out-of-the-box by Campaign Standard. You simply add an **[!UICONTROL Unsubscription link]** content block in the template ([learn more](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ko)). 이벤트 기반 템플릿(rtEvent)을 사용하는 경우 메시지에 URL 매개 변수에서 개인 이메일을 전달하고 구독 취소 랜딩 페이지를 가리키는 링크를 추가해야 합니다. You need to create this landing page and make sure the person&#39;s decision to unsubscribe is transmitted to Adobe.

First, you need to choose a transactional messaging template. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

Two categories are available: **[!UICONTROL Address]** and **[!UICONTROL Personalization Data]**.

You can easily define where to retrieve the **[!UICONTROL Address]** or the **[!UICONTROL Personalization Data]** using the interface. You can browse through events and available data source&#39;s fields. You can also use the advanced expression editor for more advanced use cases such as using a data source that requires the passing of parameters or performing manipulations. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

**[!UICONTROL Address]**

>[!NOTE]
>
>이 범주는 &quot;이벤트&quot; 트랜잭션 메시지를 선택한 경우에만 표시됩니다. &quot;프로필&quot; 메시지의 경우 **[!UICONTROL Address]** 필드는 시스템에서 Adobe Campaign Standard에서 자동으로 검색됩니다.

시스템이 메시지를 보낼 위치를 알아야 하는 필드입니다. 이메일 템플릿의 경우 이메일 주소입니다. SMS의 경우 휴대폰 번호입니다.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>개인화 데이터에서 컬렉션을 전달할 수 없습니다. 트랜잭션 이메일 또는 SMS에 컬렉션이 필요한 경우 작동하지 않습니다. 또한 개인화 데이터에는 예상 형식(예: 문자열, 십진수 등)이 있습니다. 이러한 예상 형식을 준수하도록 주의해야 합니다.

Adobe Campaign Standard 메시지에서 예상하는 필드입니다. 이러한 필드는 메시지를 개인화하거나, 조건부 서식을 적용하거나, 특정 메시지 변형을 선택하는 데 사용할 수 있습니다.

![](../assets/journey62.png)

## 푸시 {#section_im3_hvf_nhb}

푸시 활동을 사용하기 전에 푸시 알림을 전송하기 위해 Campaign Standard과 함께 모바일 앱을 구성해야 합니다. 이 [article](https://helpx.adobe.com/kr/campaign/kb/integrate-mobile-sdk.html)을(를) 사용하여 모바일에 필요한 구현 단계를 수행하십시오.

먼저 드롭다운 목록에서 모바일 앱을 선택하고 트랜잭션 메시지를 표시해야 합니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

![](../assets/journey62bis.png)

Two categories are available: **[!UICONTROL Target]** and **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>This category is only visible if you select an event message. For profile messages, the **[!UICONTROL Target]** fields are automatically retrieved by the system using the reconciliation performed by Adobe Campaign Standard.

In this section, you need to define the **[!UICONTROL Push platform]**. The drop-down list allows you to select **[!UICONTROL Apple Push Notification Server]** (iOS) or **[!UICONTROL Firebase Cloud Messaging]** (Android). You can alternatively select a specific field from an event or a data source, or define an advanced expression.

You also need to define the **[!UICONTROL Registration Token]**. The expression depends on how the token is defined in the event payload or in other [!DNL Journey Orchestration] information. 토큰이 예를 들어 컬렉션에 정의된 경우 단순 필드 또는 더 복잡한 식이 될 수 있습니다.

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>개인화 데이터에서 컬렉션을 전달할 수 없습니다. 트랜잭션 푸시에 컬렉션이 필요한 경우 작동하지 않습니다. 또한 개인화 데이터에는 예상 형식(예: 문자열, 십진수 등)이 있습니다. 이러한 예상 형식을 준수하도록 주의해야 합니다.

Adobe Campaign Standard 메시지에 사용된 트랜잭션 템플릿에서 예상하는 필드입니다. 이 필드를 사용하여 메시지를 개인화하거나, 조건부 서식을 적용하거나, 특정 메시지 변형을 선택할 수 있습니다.
