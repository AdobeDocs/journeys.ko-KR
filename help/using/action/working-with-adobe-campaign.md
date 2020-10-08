---
title: Adobe Campaign 작업
description: Adobe Campaign 작업에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 4%

---


# Adobe Campaign 작업 {#using_adobe_campaign_standard}

Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 보낼 수 있습니다.

[!DNL Journey Orchestration] adobe campaign standard에 바로 연결할 수 있는 특별 액션이 포함되어 있습니다.

Journey Orchestration에서 사용하려면 Campaign Standard 트랜잭션 메시지 및 관련 이벤트를 게시해야 합니다. 이벤트가 게시되었지만 메시지가 게시되지 않으면 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되었지만 연결된 이벤트가 없으면 Journey Orchestration 인터페이스에 표시되지만 사용할 수는 없습니다.

>[!NOTE]
>
>Adobe Campaign Standard 트랜잭션 메시징이 오버로드되지 않도록 Campaign Standard 통합에 대한 **매핑 규칙** 설정을 권장합니다.
>
>Adobe Campaign Standard 제품 설명에서 트랜잭션 메시징 SLA에 대한 자세한 내용을 [참조하십시오](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html).

다음은 구성 단계입니다.

1. 목록에서 **[!UICONTROL Actions]** 기본 제공 작업을 **[!UICONTROL AdobeCampaignStandard]** 클릭합니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard 인스턴스 URL을 복사하여 **[!UICONTROL URL]** 필드에 붙여 넣습니다.

1. 인스턴스 **[!UICONTROL Test the instance URL]** 의 유효성을 테스트하려면 을 클릭합니다.

   >[!NOTE]
   >
   >이 테스트는 다음을 확인합니다.
   >
   >호스트는 &quot;.campaign.adobe.com&quot; 또는 &quot;.campaign-sandbox.adobe.com&quot;입니다.
   >
   >URL은 https,
   >
   >이 Adobe Campaign Standard 인스턴스와 연관된 ORG는 Journey Orchestration ORG와 동일합니다.

여정을 디자인할 때 다음 세 가지 작업을 카테고리에서 사용할 수 **[!UICONTROL Action]** 있습니다. **[!UICONTROL Email]**, **[!UICONTROL Push]**(Adobe Campaign 작업 **[!UICONTROL SMS]** 사용 참조 [](../building-journeys/using-adobe-campaign-actions.md)) **또한 반응 이벤트를** 사용하면 메시지 클릭, 열기 등에 반응할 수 있습니다. ( [반응 이벤트 참조](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

타사 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 추가하고 구성해야 합니다. See [About custom action configuration](../action/about-custom-action-configuration.md).
