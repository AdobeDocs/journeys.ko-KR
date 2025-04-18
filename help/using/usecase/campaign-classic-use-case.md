---
product: adobe campaign
solution: Journey Orchestration
title: Campaign v7/v8을 사용하여 메시지 보내기
description: Campaign v7/v8을 사용하여 메시지 보내기
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Campaign v7/v8을 사용하여 메시지 보내기 {#campaign-classic-use-case}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


이 사용 사례에서는 Adobe Campaign Classic v7 및 Adobe Campaign v8과의 통합을 사용하여 이메일을 보내는 데 필요한 모든 단계를 설명합니다.

먼저 Campaign에서 트랜잭션 이메일 템플릿을 만듭니다. 그런 다음 Journey Orchestration에서 이벤트, 작업 및 여정 디자인을 만듭니다.

Campaign 통합에 대한 자세한 내용은 다음 페이지를 참조하십시오.

* [Campaign 작업 만들기](../action/acc-action.md)
* [여정에서 작업 사용](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

이 통합을 위해 Campaign 인스턴스를 프로비저닝해야 합니다. 트랜잭션 메시지 기능을 구성해야 합니다.

1. Campaign 컨트롤 인스턴스에 로그인합니다.

1. **관리** > **플랫폼** > **열거형**&#x200B;에서 **이벤트 유형**(eventType) 열거형을 선택합니다. 새 이벤트 유형(&quot;이 예제의 경우 &quot;여정-이벤트&quot;)을 만듭니다. 나중에 JSON 파일을 작성할 때 이벤트 유형의 내부 이름을 사용해야 합니다.

   ![](../assets/accintegration-uc-1.png)

1. 생성을 위해 인스턴스 연결을 끊고 인스턴스에 다시 연결합니다.

1. **메시지 센터** > **트랜잭션 메시지 템플릿**&#x200B;에서 이전에 만든 이벤트 유형을 기반으로 새 전자 메일 템플릿을 만듭니다.

   ![](../assets/accintegration-uc-2.png)

1. 템플릿 디자인 이 예제에서는 프로필의 이름과 주문 번호에 대한 개인화를 사용합니다. 이름은 Adobe Experience Platform 데이터 소스에 있고 주문 번호는 Journey Orchestration 이벤트의 필드입니다. Campaign에서 올바른 필드 이름을 사용해야 합니다.

   ![](../assets/accintegration-uc-3.png)

1. 트랜잭션 템플릿을 게시합니다.

   ![](../assets/accintegration-uc-4.png)

1. 이제 템플릿에 해당하는 JSON 페이로드를 작성해야 합니다.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* 채널의 경우 &quot;email&quot;을 입력해야 합니다.
* eventType의 경우 이전에 만든 이벤트 유형의 내부 이름을 사용합니다.
* 이메일 주소는 변수가 되므로 임의의 레이블을 입력할 수 있습니다.
* ctx에서 개인화 필드도 변수입니다.

**Journey Orchestration**

1. 먼저 이벤트를 만들어야 합니다. purchaseOrderNumber 필드를 포함해야 합니다.

   ![](../assets/accintegration-uc-5.png)

1. 그런 다음 Journey Orchestration에서 Campaign 템플릿에 해당하는 작업을 만들어야 합니다. **작업 유형** 드롭다운에서 **Adobe Campaign Classic**&#x200B;을 선택합니다.

   ![](../assets/accintegration-uc-6.png)

1. **페이로드 필드**&#x200B;를 클릭하고 이전에 만든 JSON을 붙여 넣습니다.

   ![](../assets/accintegration-uc-7.png)

1. 전자 메일 주소와 두 개의 개인화 필드의 경우 **상수**&#x200B;을(를) **변수**(으)로 변경하십시오.

   ![](../assets/accintegration-uc-8.png)

1. 이제 새 여정을 만들고 이전에 만든 이벤트로 시작합니다.

   ![](../assets/accintegration-uc-9.png)

1. 작업을 추가하고 각 필드를 Journey Orchestration의 올바른 필드에 매핑합니다.

   ![](../assets/accintegration-uc-10.png)

1. **End** 활동을 추가하고 여정을 테스트합니다.

   ![](../assets/accintegration-uc-11.png)

1. 이제 여정을 게시할 수 있습니다.
