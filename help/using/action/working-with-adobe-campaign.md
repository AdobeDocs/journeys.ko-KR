---
product: adobe campaign
title: Adobe Campaign 작업
description: Adobe Campaign 작업에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 545352efdcda80cb9940010c4587a20f53326085
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Adobe Campaign Standard 작업 {#using_adobe_campaign_standard}

Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 전송할 수 있습니다.

[!DNL Journey Orchestration]에는 Adobe Campaign Standard에 연결할 수 있는 기본 동작이 포함되어 있습니다.

Journey Orchestration에서 사용하려면 Campaign Standard 트랜잭션 메시지와 관련 이벤트를 게시해야 합니다. 이벤트가 게시되었지만 메시지는 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되었지만 연결된 이벤트가 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지만 사용할 수 없습니다.

>[!NOTE]
>
>Adobe Campaign Standard 통합이 설정되는 즉시 Adobe Campaign Standard 작업에 대해 5분당 4000회의 최대 가용량 규칙이 자동으로 정의됩니다. 이는 Adobe Campaign Standard 트랜잭션 메시지의 공식 규모에 해당합니다.
>
>[Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)에서 트랜잭션 메시지 SLA에 대해 자세히 알아보세요.

이를 구성하는 단계는 다음과 같습니다.

1. **[!UICONTROL Actions]** 목록에서 기본 제공 **[!UICONTROL AdobeCampaignStandard]** 작업을 클릭합니다. 작업 구성 창이 화면 오른쪽에 열립니다.

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard 인스턴스 URL을 복사하여 **[!UICONTROL URL]** 필드에 붙여넣습니다.

1. **[!UICONTROL Test the instance URL]**&#x200B;을(를) 클릭하여 인스턴스의 유효성을 테스트합니다.

   >[!NOTE]
   >
   >이 테스트는 다음을 확인합니다.
   >
   >호스트는 &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; 또는 &quot;.adls.adobe.com&quot;입니다.
   >
   >URL은 https로 시작합니다.
   >
   >이 Adobe Campaign Standard 인스턴스와 연결된 조직이 Journey Orchestration 조직과 동일합니다.

여정을 디자인할 때 **[!UICONTROL Action]** 범주에서 다음 세 가지 작업을 사용할 수 있습니다. **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]**([Adobe Campaign 작업 사용](../building-journeys/using-adobe-campaign-actions.md) 참조). **반응 이벤트**&#x200B;를 사용하면 메시지 클릭, 열기 등에 반응할 수도 있습니다. ([반응 이벤트](../building-journeys/reaction-events.md) 참조).

![](../assets/journey58.png)

서드파티 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 추가하고 구성해야 합니다. [사용자 지정 작업 구성 정보](../action/about-custom-action-configuration.md)를 참조하세요.
