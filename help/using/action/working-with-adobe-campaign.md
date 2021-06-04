---
product: adobe campaign
title: Adobe Campaign 작업
description: Adobe Campaign 작업에 대해 알아보기
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 04aa7d95c2f12fe03497efe74f2ab8bd1a270b5b
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# Adobe Campaign 작업 {#using_adobe_campaign}

## Adobe Campaign Standard 사용 {#using_adobe_campaign_standard}

Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 보낼 수 있습니다.

[!DNL Journey Orchestration] 은 Adobe Campaign Standard에 연결할 수 있는 기본 작업을 제공합니다.

Campaign Standard 트랜잭션 메시지와 관련 이벤트를 Journey Orchestration에 사용하려면 게시해야 합니다. 이벤트가 게시되었지만 메시지가 게시되지 않은 경우 Journey Orchestration 인터페이스에 표시되지 않습니다. 메시지가 게시되지만 연결된 이벤트가 게시되지 않으면 Journey Orchestration 인터페이스에 표시되지만 사용할 수 없습니다.

>[!NOTE]
>
>Adobe Campaign Standard 통합이 설정되는 즉시 초당 13개의 호출의 최대 가용량 규칙이 Adobe Campaign Standard 작업에 대해 자동으로 정의됩니다. 이는 Adobe Campaign Standard 트랜잭션 메시지의 공식 규모에 해당합니다.
>
>[Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)에서 트랜잭션 메시지 SLA에 대해 자세히 알아보십시오.

구성하는 단계는 다음과 같습니다.

1. **[!UICONTROL Actions]** 목록에서 기본 제공 **[!UICONTROL AdobeCampaignStandard]** 작업을 클릭합니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard 인스턴스 URL을 복사하여 **[!UICONTROL URL]** 필드에 붙여넣습니다.

1. **[!UICONTROL Test the instance URL]** 을 클릭하여 인스턴스의 유효성을 테스트합니다.

   >[!NOTE]
   >
   >이 테스트는 다음을 확인합니다.
   >
   >호스트는 &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; 또는 &quot;.adls.adobe.com&quot;입니다.
   >
   >URL은 https,
   >
   >이 Adobe Campaign Standard 인스턴스에 연결된 ORG는 Journey Orchestration의 ORG와 동일합니다.

여정을 디자인할 때 **[!UICONTROL Action]** 카테고리에서 세 가지 작업을 사용할 수 있습니다.**[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]**([Adobe Campaign 작업 사용](../building-journeys/using-adobe-campaign-actions.md) 참조). **반응** 이벤트로 인해 메시지 클릭, 열기 등에 대응할 수도 있습니다. ( [반응 이벤트](../building-journeys/reaction-events.md) 참조).

![](../assets/journey58.png)

서드파티 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 추가하고 구성해야 합니다. [사용자 지정 작업 구성 정보](../action/about-custom-action-configuration.md)를 참조하십시오.

## Adobe Campaign v7/v8 사용 {#using_adobe_campaign_v7_v8}

이 통합은 21.1 릴리스부터 Adobe Campaign Classic v7 및 Adobe Campaign v8에서 사용할 수 있습니다. Adobe Campaign 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 전송할 수 있습니다.

Journey Orchestration과 Campaign 인스턴스 간의 연결은 프로비저닝 시 Adobe에 의해 설정됩니다.

이 [섹션](../usecase/campaign-v7-v8-use-case.md)에 사용 사례가 나와 있습니다.

구성된 각 작업에 대해 여정 디자이너 팔레트에서 작업 활동을 사용할 수 있습니다. 이 [섹션](../building-journeys/using-adobe-campaign-actions.md)을 참조하십시오.

### 중요 정보

* 메시지 제한이 없습니다. 현재 Campaign SLA를 기반으로 하여 시간당 50,000개로 전송할 수 있는 메시지 수를 제한합니다. 따라서 여정 오케스트레이션은 단일 사용 사례(세그먼트가 아닌 개별 이벤트)에서만 사용해야 합니다.

* 사용하려는 템플릿당 캔버스에서 한 개의 작업을 구성해야 합니다. Adobe Campaign에서 사용할 각 템플릿에 대해 Journey Orchestration에서 하나의 작업을 구성해야 합니다.

* 진행 중인 다른 Campaign 작업에 영향을 주지 않도록 이 통합을 위해 호스팅되는 전용 메시지 센터 인스턴스를 사용하는 것이 좋습니다. 마케팅 서버는 호스팅 또는 온프레미스할 수 있습니다. 필요한 빌드는 21.1 릴리스 후보 이상입니다.

* 페이로드 또는 Campaign 메시지가 올바른지 확인하지 않습니다.

* 세그먼트 자격 이벤트에서 캠페인 작업을 사용할 수 없습니다.

### 필수 구성 요소

Campaign에서는 트랜잭션 메시지와 관련 이벤트를 만들고 게시해야 합니다. [Adobe Campaign 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)를 참조하십시오.

아래 패턴에 따라 각 메시지에 해당하는 JSON 페이로드를 작성할 수 있습니다. 그런 다음 Journey Orchestration에서 작업을 구성할 때 이 페이로드를 붙여 넣습니다(아래 참조)

다음은 한 예입니다.

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **채널**:캠페인 트랜잭션 템플릿에 대해 정의된 채널
* **eventType**:Campaign 이벤트의 내부 이름
* **ctx**:변수에 설정된 값은 메시지에 포함된 개인화를 기반으로 합니다.

### 작업 구성

Journey Orchestration에서 트랜잭션 메시지당 하나의 작업을 구성해야 합니다. 다음 단계를 수행합니다.

1. 새 작업을 만듭니다. 이 [섹션](../action/action.md)을 참조하십시오.
1. 이름과 설명을 입력합니다.
1. **작업 유형** 필드에서 **Adobe Campaign Classic**&#x200B;을 선택합니다.
1. **페이로드** 필드를 클릭하고 Campaign 메시지에 해당하는 JSON 페이로드의 예제를 붙여넣습니다. 이 페이로드를 가져오려면 Adobe에 문의하십시오.
1. 여정 캔버스에 매핑할지 여부에 따라 다른 필드를 정적 또는 변수로 조정합니다. 전자 메일 주소 및 개인화 필드(ctx)에 대한 채널 매개 변수와 같은 특정 필드는 여정 컨텍스트에서 매핑을 위한 변수로 정의할 수 있습니다.
1. **저장**&#x200B;을 클릭합니다.

![](../assets/accintegration1.png)


