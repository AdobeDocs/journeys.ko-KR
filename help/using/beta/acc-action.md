---
product: adobe campaign
title: Campaign Classic 통합 기본 정보
description: Campaign Classic 통합에 대해 알아보기
hide: true
hidefromtoc: true
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 2%

---

# Adobe Campaign Classic과 통합 {#integrating-with-adobe-campaign-classic}

이 통합을 사용하면 Adobe Campaign Classic 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 전송할 수 있습니다.

Journey Orchestration 인스턴스와 Campaign Classic 인스턴스 간의 연결은 프로비저닝 시 Adobe에 의해 설정됩니다.

>[!CAUTION]
>
> 이 통합은 비공개 베타로 출시됩니다. 모든 Journey Orchestration 고객이 이용할 수 있는 것은 아닙니다.

## 중요 정보

* 메시지 제한이 없습니다. 현재 Campaign Classic SLA를 기준으로 50,000시간 동안 전송할 수 있는 메시지 수를 제한합니다. 따라서 여정 오케스트레이션은 단일 사용 사례(세그먼트가 아닌 개별 이벤트)에서만 사용해야 합니다.

* 사용하려는 템플릿당 캔버스에서 한 개의 작업을 구성해야 합니다.

* 진행 중인 다른 Campaign Classic 작업에 영향을 주지 않도록 이 통합을 위해 호스팅되는 전용 메시지 센터 인스턴스를 사용하는 것이 좋습니다. 마케팅 서버는 호스팅 또는 온프레미스할 수 있습니다. 필요한 빌드는 21.1 릴리스 후보자입니다.

* 페이로드 또는 Campaign Classic 메시지가 올바른지 확인하지 않습니다.

* 세그먼트 자격이 있는 Campaign Classic 작업은 사용할 수 없습니다.

## 필수 구성 요소

Campaign Classic에서 트랜잭션 메시지와 관련 이벤트를 만들고 게시해야 합니다. [Adobe Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)를 참조하십시오.

각 메시지에 해당하는 JSON 페이로드를 가져오려면 Adobe에 문의하십시오. 그런 다음 Journey Orchestration에서 작업을 구성할 때 이 페이로드를 붙여 넣습니다(아래 참조).

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

## 작업 구성

Journey Orchestration에서 트랜잭션 메시지당 하나의 작업을 구성해야 합니다. 다음 단계를 수행합니다.

1. 새 작업을 만듭니다. 이 [섹션](../action/action.md)을 참조하십시오.
1. 이름과 설명을 입력합니다.
1. **작업 유형** 필드에서 **Adobe Campaign Classic**&#x200B;을 선택합니다.
1. **페이로드** 필드를 클릭하고 Campaign Classic 메시지에 해당하는 JSON 페이로드의 예제를 붙여넣습니다. 이 페이로드를 가져오려면 Adobe에 문의하십시오.
1. 다양한 필드를 조정합니다. 채널 매개 변수 및 개인화 필드(ctx)와 같은 특정 필드는 변수로 정의해야 합니다.
1. **저장**&#x200B;을 클릭합니다.

![](../assets/accintegration1.png)

구성된 각 작업에 대해 여정 디자이너 팔레트에서 작업 활동을 사용할 수 있습니다.

## 여정에서 메시지 추가

1. 이벤트를 시작으로 여정을 디자인합니다. 이 [섹션](../building-journeys/journey.md)을 참조하십시오.
1. 팔레트의 **작업** 섹션에서 Campaign Classic 작업을 선택하고 여정에 추가합니다.
1. **작업 매개 변수**&#x200B;에 메시지 페이로드에서 예상되는 모든 필드가 표시됩니다. 이벤트 또는 데이터 소스에서 사용할 필드에 이러한 각 필드를 매핑해야 합니다. 이는 사용자 지정 작업과 유사합니다. 이 [섹션](../building-journeys/using-custom-actions.md)을 참조하십시오.

![](../assets/accintegration2.png)
