---
product: adobe campaign
title: Adobe Campaign을 사용한 작업
description: Adobe Campaign 작업에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Adobe Campaign Standard 작업 {#using_adobe_campaign_standard}

Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 보낼 수 있습니다.

[!DNL Journey Orchestration] 은 Adobe Campaign Standard에 연결할 수 있는 기본 작업을 제공합니다.

Campaign Standard 트랜잭션 메시지와 관련 이벤트를 Journey Orchestration에 사용하려면 게시해야 합니다. 이벤트가 게시되었지만 메시지가 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되지만 연결된 이벤트가 게시되지 않으면 Journey Orchestration 인터페이스에 표시되지만 사용할 수 없습니다.

>[!NOTE]
>
>Adobe Campaign Standard 통합이 설정되는 즉시 초당 13개의 호출의 최대 가용량 규칙이 Adobe Campaign Standard 작업에 대해 자동으로 정의됩니다. 이는 Adobe Campaign Standard 트랜잭션 메시지의 공식 규모에 해당합니다.
>
>의 트랜잭션 메시지 SLA에 대해 자세히 알아보십시오. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html).

구성하는 단계는 다음과 같습니다.

1. 에서 **[!UICONTROL Actions]** 목록에서 기본 제공 **[!UICONTROL AdobeCampaignStandard]** 작업. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard 인스턴스 URL을 복사하여 **[!UICONTROL URL]** 필드.

1. 을(를) 클릭합니다. **[!UICONTROL Test the instance URL]** 를 눌러 인스턴스의 유효성을 테스트합니다.

   >[!NOTE]
   >
   >이 테스트는 다음을 확인합니다.
   >
   >호스트는 &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; 또는 &quot;.adls.adobe.com&quot;입니다.
   >
   >URL은 https,
   >
   >이 Adobe Campaign Standard 인스턴스에 연결된 ORG는 Journey Orchestration의 ORG와 동일합니다.

여정을 디자인할 때 **[!UICONTROL Action]** 범주: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** 자세한 내용은 [Adobe Campaign 작업 사용](../building-journeys/using-adobe-campaign-actions.md)). **반응 이벤트** 또한 메시지 클릭 수, 열기 등에 대응할 수도 있습니다. 자세한 내용은 [반응 이벤트](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

서드파티 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 추가하고 구성해야 합니다. 자세한 내용은 [사용자 지정 작업 구성](../action/about-custom-action-configuration.md).
