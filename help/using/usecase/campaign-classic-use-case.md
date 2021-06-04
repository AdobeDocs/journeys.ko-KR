---
product: adobe campaign
solution: Journey Orchestration
title: 피로 점수 활용
description: 여정에서 피로도 점수를 활용하는 방법을 알아봅니다
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---


# Campaign Classic {#campaign-classic-use-case}을 사용하여 메시지 보내기

이 사용 사례에서는 Adobe Campaign Classic 통합을 사용하여 이메일을 전송하는 데 필요한 모든 단계를 설명합니다.

먼저 Campaign Classic에서 트랜잭션 이메일 템플릿을 만듭니다. 그런 다음 Journey Orchestration에서 이벤트, 작업, 여정을 디자인합니다.

Campaign Classic 통합에 대한 자세한 내용은 다음 페이지를 참조하십시오.

* [Campaign Classic 작업 만들기](../action/acc-action.md)
* [여정에서 작업 사용](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign Classic**

이 통합을 위해 Campaign Classic 인스턴스를 프로비저닝해야 합니다. 트랜잭션 메시지 기능을 구성해야 합니다.

1. Campaign Classic 제어 인스턴스에 로그인합니다.

1. **관리** > **플랫폼** > **열거형**&#x200B;에서 **이벤트 유형** (eventType) 열거형을 선택합니다. 새 이벤트 유형(이 예제에서는 &quot;여정-event&quot;)을 만듭니다. 나중에 JSON 파일을 작성할 때 이벤트 유형의 내부 이름을 사용해야 합니다.

   ![](../assets/accintegration-uc-1.png)

1. 생성을 유효하게 하려면 인스턴스 연결을 끊고 인스턴스에 다시 연결합니다.

1. **메시지 센터** > **트랜잭션 메시지 템플릿**&#x200B;에서 이전에 만든 이벤트 유형을 기반으로 새 이메일 템플릿을 만듭니다.

   ![](../assets/accintegration-uc-2.png)

1. 템플릿을 디자인합니다. 이 예에서는 프로필의 이름과 주문 번호에 개인화를 사용합니다. 이름은 Adobe Experience Platform 데이터 소스에 있고 순서 번호는 Journey Orchestration 이벤트의 필드입니다. Campaign Classic에서 올바른 필드 이름을 사용해야 합니다.

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
* 이메일 주소는 변수가 되므로 모든 레이블을 입력할 수 있습니다.
* ctx에서 개인화 필드도 변수입니다.

**Journey Orchestration**

1. 먼저 이벤트를 만들어야 합니다. purchaseOrderNumber 필드를 포함해야 합니다.

   ![](../assets/accintegration-uc-5.png)

1. 그런 다음 Journey Orchestration에서 Campaign Classic 템플릿에 해당하는 작업을 만들어야 합니다. **작업 유형** 드롭다운에서 **Adobe Campaign Classic**&#x200B;을 선택합니다.

   ![](../assets/accintegration-uc-6.png)

1. **페이로드 필드**&#x200B;를 클릭하고 이전에 만든 JSON을 붙여 넣습니다.

   ![](../assets/accintegration-uc-7.png)

1. 이메일 주소와 두 개인화 필드의 경우 **상수**&#x200B;를 **변수**&#x200B;로 변경하십시오.

   ![](../assets/accintegration-uc-8.png)

1. 이제 새 여정을 만들고 이전에 만든 이벤트로 시작합니다.

   ![](../assets/accintegration-uc-9.png)

1. 작업을 추가하고 각 필드를 Journey Orchestration의 올바른 필드에 매핑합니다.

   ![](../assets/accintegration-uc-10.png)

1. **종료** 활동을 추가하고 여정을 테스트합니다.

   ![](../assets/accintegration-uc-11.png)

1. 이제 여정을 게시할 수 있습니다.
