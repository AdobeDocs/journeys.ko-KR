---
product: adobe campaign
title: Campaign v7/v8 통합 기본 정보
description: Campaign v7/v8 통합에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 13%

---

# Adobe Campaign v7/v8 작업 {#integrating-with-adobe-campaign-classic}

이 통합은 21.1 릴리스부터 Adobe Campaign Classic v7 및 Adobe Campaign v8에서 사용할 수 있습니다. Adobe Campaign 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림, SMS를 전송할 수 있습니다.

Journey Orchestration 인스턴스와 Campaign 인스턴스 간의 연결은 프로비저닝 시 Adobe에 의해 설정됩니다.

이 [섹션](../usecase/campaign-classic-use-case.md)에 엔드 투 엔드 사용 사례가 표시됩니다.

구성된 각 작업에 대해 여정 디자이너 팔레트에서 작업 활동을 사용할 수 있습니다. 이 [섹션](../building-journeys/using-adobe-campaign-classic.md)을 참조하십시오.

## 중요 정보

* 메시지 제한이 없습니다. 현재 Campaign SLA를 기준으로 시간당 50,000개까지 보낼 수 있는 메시지 수를 제한합니다. 따라서 여정 오케스트레이션은 단일 사용 사례(세그먼트가 아닌 개별 이벤트)에만 사용해야 합니다.

* 사용하려는 템플릿당 캔버스에서 하나의 작업을 구성해야 합니다. Adobe Campaign에서 사용하려는 각 템플릿에 대해 Journey Orchestration 시 하나의 작업을 구성해야 합니다.

* 진행 중인 다른 Campaign 작업에 영향을 주지 않도록 이 통합을 위해 호스팅되는 전용 메시지 센터 인스턴스를 사용하는 것이 좋습니다. 마케팅 서버는 호스팅되거나 온프레미스가 될 수 있습니다. 필요한 빌드는 21.1 릴리스 후보 이상입니다.

* 페이로드 또는 캠페인 메시지가 올바른지 확인할 수 없습니다.

* 세그먼트 자격 이벤트에서 Campaign 작업을 사용할 수 없습니다.

## 전제 조건

Campaign에서는 트랜잭션 메시지와 관련 이벤트를 만들고 게시해야 합니다. [Adobe Campaign 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)를 참조하세요.

아래 패턴에 따라 각 메시지에 해당하는 JSON 페이로드를 빌드할 수 있습니다. 그런 다음 Journey Orchestration에서 작업을 구성할 때 이 페이로드를 붙여 넣습니다(아래 참조).

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

* **채널**: 캠페인 트랜잭션 템플릿에 대해 정의된 채널
* **eventType**: Campaign 이벤트의 내부 이름
* **ctx**: 메시지에 있는 개인화를 기반으로 하는 변수입니다.

## 작업 구성

Journey Orchestration에서 트랜잭션 메시지당 하나의 작업을 구성해야 합니다. 다음 단계를 수행하십시오.

1. 새 작업을 만듭니다. 이 [섹션](../action/action.md)을 참조하십시오.
1. 이름과 설명을 입력합니다.
1. **작업 유형** 필드에서 **Adobe Campaign Classic**&#x200B;을(를) 선택합니다.
1. **페이로드** 필드를 클릭하고 캠페인 메시지에 해당하는 JSON 페이로드의 예제를 붙여 넣습니다. 이 페이로드를 가져오려면 Adobe에게 문의하십시오.
1. 여정 캔버스에서 매핑할지 여부에 따라 다양한 필드를 정적 또는 변수로 조정합니다. 이메일 주소에 대한 채널 매개 변수 및 개인화 필드(ctx)와 같은 특정 필드는 여정 컨텍스트에서 매핑하기 위한 변수로 정의할 수 있습니다.
1. **저장**&#x200B;을 클릭합니다.

![](../assets/accintegration1.png)


