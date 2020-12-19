---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign 작업 사용
description: Adobe Campaign 작업에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 5%

---


# Adobe Campaign 작업 사용 {#using_campaign_action}

Adobe Campaign Standard이 있는 경우 다음과 같은 바로 사용 가능한 작업 활동을 사용할 수 있습니다.**[!UICONTROL Email]**, **[!UICONTROL Push]** 및 **[!UICONTROL SMS]**.

>[!NOTE]
>
>이를 위해 기본 제공 작업을 구성해야 합니다. [이 페이지](../action/working-with-adobe-campaign.md)를 참조하십시오.

이러한 각 채널에 대해 Adobe Campaign Standard 트랜잭션 메시지 **템플릿**&#x200B;을 선택합니다. 실제로 [!DNL Journey Orchestration]은(는) 메시지 전송 솔루션이 아닙니다. 내장된 이메일, SMS 및 푸시 채널의 경우 트랜잭션 메시지를 통해 메시지 전송을 실행할 수 있습니다. 즉, 여행 중에 특정 메시지 템플릿을 사용하려면 Adobe Campaign Standard에서 게시해야 합니다. 이 기능을 사용하는 방법에 대해 알려면 [이 페이지](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)를 참조하십시오.

>[!NOTE]
>
>Journey Orchestration에서 사용하려면 Campaign Standard 트랜잭션 메시지 및 관련 이벤트를 게시해야 합니다. 이벤트가 게시되었지만 메시지가 게시되지 않으면 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되지만 연관된 이벤트가 게시되지 않으면 Journey Orchestration 인터페이스에 메시지를 볼 수 있지만 사용할 수는 없습니다.

![](../assets/journey59.png)

이벤트(실시간)나 프로필 트랜잭션 메시징 템플릿을 사용할 수 있습니다.

>[!NOTE]
>
>사용자 지정 작업 덕분에 실시간 트랜잭션 메시지(rtEvent)를 보내거나 제3자 시스템으로 메시지를 라우팅할 때 피로, 차단 목록 또는 구독 취소 관리에 특정 설정이 필요합니다. 예를 들어 &quot;가입 해지&quot; 속성이 Adobe Experience Platform 또는 제3자 시스템에 저장되어 있는 경우 이 조건을 확인하기 위해 메시지를 보내기 전에 조건을 추가해야 합니다.

템플릿을 선택하면 메시지 페이로드에 필요한 모든 필드가 **[!UICONTROL Address]** 및 **[!UICONTROL Personalization Data]** 아래의 활동 구성 창에 표시됩니다. 이벤트 또는 데이터 소스에서 사용할 필드에 이러한 각 필드를 매핑해야 합니다. 고급 표현식 편집기를 사용하여 값을 수동으로 전달하고, 검색된 정보에 대한 데이터 조작(예: 문자열을 대문자로 변환)을 수행하거나, &quot;if, then, else&quot;와 같은 함수를 사용할 수도 있습니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

![](../assets/journey60.png)

## 이메일 및 SMS {#section_asc_51g_nhb}

**[!UICONTROL Email]** 및 **[!UICONTROL SMS]**&#x200B;의 경우 매개 변수가 동일합니다.

>[!NOTE]
>
>이메일의 경우 프로파일 트랜잭션 템플릿을 사용하는 경우, 구독 취소 메커니즘은 기본적으로 Campaign Standard으로 처리됩니다. 템플릿에 **[!UICONTROL Unsubscription link]** 내용 블록을 추가하면 됩니다([자세한 내용](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). 이벤트 기반 템플릿(rtEvent)을 사용하는 경우 메시지에 URL 매개 변수의 이메일 전달과 구독 취소 랜딩 페이지를 가리키는 링크를 추가해야 합니다. 이 랜딩 페이지를 만들고 가입 해지를 결정한 사람이 Adobe으로 전송되도록 해야 합니다.

먼저 트랜잭션 메시지 템플릿을 선택해야 합니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

다음 두 가지 카테고리를 사용할 수 있습니다.**[!UICONTROL Address]** 및 **[!UICONTROL Personalization Data]**.

인터페이스를 사용하여 **[!UICONTROL Address]** 또는 **[!UICONTROL Personalization Data]**&#x200B;을 검색할 위치를 쉽게 정의할 수 있습니다. 이벤트 및 사용 가능한 데이터 소스의 필드를 검색할 수 있습니다. 매개 변수를 전달해야 하거나 조작을 수행하는 데이터 소스를 사용하는 등 고급 표현식 편집기를 사용하여 고급 사용 사례를 사용할 수도 있습니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

**[!UICONTROL Address]**

>[!NOTE]
>
>이 카테고리는 &quot;이벤트&quot; 트랜잭션 메시지를 선택하는 경우에만 표시됩니다. &quot;profile&quot; 메시지의 경우 시스템에서 **[!UICONTROL Address]** 필드를 Adobe Campaign Standard에서 자동으로 검색합니다.

메시지를 보낼 위치를 알아야 하는 필드입니다. 이메일 템플릿의 경우 이메일 주소입니다. SMS는 휴대폰 번호입니다.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>개인화 데이터에서 컬렉션을 전달할 수 없습니다. 트랜잭션 이메일 또는 SMS에 컬렉션이 필요한 경우 작동하지 않습니다. 또한 개인화 데이터의 형식은 예상 형식입니다(예:문자열, 십진수 등). 이러한 예상 형식을 존중해야 합니다.

Adobe Campaign Standard 메시지에 필요한 필드입니다. 이러한 필드를 사용하여 메시지를 개인화하고, 조건부 서식을 적용하거나, 특정 메시지 변형을 선택할 수 있습니다.

![](../assets/journey62.png)

## {#section_im3_hvf_nhb} 푸시

푸시 활동을 사용하기 전에 푸시 알림을 전송하려면 모바일 앱을 Campaign Standard과 함께 구성해야 합니다. 모바일에 필요한 구현 단계를 수행하려면 이 [article](https://helpx.adobe.com/kr/campaign/kb/integrate-mobile-sdk.html)을 사용하십시오.

먼저 드롭다운 목록에서 모바일 앱을 선택하고 트랜잭션 메시지를 선택해야 합니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

![](../assets/journey62bis.png)

다음 두 가지 카테고리를 사용할 수 있습니다.**[!UICONTROL Target]** 및 **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>이 카테고리는 이벤트 메시지를 선택하는 경우에만 표시됩니다. 프로필 메시지의 경우 Adobe Campaign Standard에서 수행하는 조정을 사용하여 **[!UICONTROL Target]** 필드가 자동으로 검색됩니다.

이 섹션에서 **[!UICONTROL Push platform]**&#x200B;을 정의해야 합니다. 드롭다운 목록을 사용하여 **[!UICONTROL Apple Push Notification Server]**(iOS) 또는 **[!UICONTROL Firebase Cloud Messaging]**(Android)를 선택할 수 있습니다. 이벤트 또는 데이터 소스에서 특정 필드를 선택하거나 고급 표현식을 정의할 수도 있습니다.

**[!UICONTROL Registration Token]**&#x200B;도 정의해야 합니다. 표현식은 이벤트 페이로드나 다른 [!DNL Journey Orchestration] 정보에서 토큰이 정의된 방식에 따라 달라집니다. 토큰을 예를 들어 컬렉션에 정의하는 경우 단순한 필드 또는 보다 복잡한 표현식이 될 수 있습니다.

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>개인화 데이터에서 컬렉션을 전달할 수 없습니다. 트랜잭션 푸시에 컬렉션이 필요한 경우 작동하지 않습니다. 또한 개인화 데이터의 형식은 예상 형식입니다(예:문자열, 십진수 등). 이러한 예상 형식을 존중해야 합니다.

Adobe Campaign Standard 메시지에 사용되는 트랜잭션 템플릿에서 요구하는 필드입니다. 이러한 필드를 사용하여 메시지를 개인화하고, 조건부 서식을 적용하거나, 특정 메시지 변형을 선택할 수 있습니다.
