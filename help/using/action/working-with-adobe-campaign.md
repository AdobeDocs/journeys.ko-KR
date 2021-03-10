---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign 작업
description: Adobe Campaign 작업에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 5c94f64c10d12690e27585806962bf9537636e9c
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 4%

---


# Adobe Campaign 작업 {#using_adobe_campaign_standard}

Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 보낼 수 있습니다.

[!DNL Journey Orchestration] Adobe Campaign Standard에 연결할 수 있는 기본 동작을 제공합니다.

Journey Orchestration에서 사용하려면 Campaign Standard 트랜잭션 메시지 및 관련 이벤트를 게시해야 합니다. 이벤트가 게시되었지만 메시지가 게시되지 않으면 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되지만 연관된 이벤트가 게시되지 않으면 Journey Orchestration 인터페이스에 메시지를 볼 수 있지만 사용할 수는 없습니다.

>[!NOTE]
>
>Adobe Campaign Standard 통합이 설정되는 즉시 Adobe Campaign Standard 작업에 대해 초당 13회의 호출 규칙이 자동으로 정의됩니다. 이는 Adobe Campaign Standard 트랜잭션 메시징의 공식 비율에 해당합니다.
>
>[Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)에서 트랜잭션 메시징 SLA에 대한 자세한 내용을 참조하십시오.

구성 단계는 다음과 같습니다.

1. **[!UICONTROL Actions]** 목록에서 내장 **[!UICONTROL AdobeCampaignStandard]** 동작을 클릭합니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard 인스턴스 URL을 복사하여 **[!UICONTROL URL]** 필드에 붙여 넣습니다.

1. **[!UICONTROL Test the instance URL]**&#x200B;을 클릭하여 인스턴스의 유효성을 테스트합니다.

   >[!NOTE]
   >
   >이 테스트는 다음을 확인합니다.
   >
   >호스트는 &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; 또는 &quot;.adls.adobe.com&quot;입니다.
   >
   >URL은 https,
   >
   >이 Adobe Campaign Standard 인스턴스와 연관된 ORG는 Journey Orchestration ORG와 동일합니다.

여정을 디자인할 때 **[!UICONTROL Action]** 범주에서 3개의 작업을 사용할 수 있습니다.**[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]**(Adobe Campaign 작업 사용](../building-journeys/using-adobe-campaign-actions.md) 참조) [ **반응** 이벤트로 인해 메시지 클릭, 열기 등에 반응할 수도 있습니다. ([반응 이벤트](../building-journeys/reaction-events.md) 참조).

![](../assets/journey58.png)

제3자 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 추가하고 구성해야 합니다. [사용자 지정 작업 구성 정보](../action/about-custom-action-configuration.md)를 참조하십시오.
