---
product: adobe campaign
title: 고급 사용 사례 정보
description: 여정 고급 사용 사례에 더 많이 의존하십시오.
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 2%

---

# 고급 사용 사례 정보{#concept_vzy_ncy_w2b}

## 용도 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어 보자. 호텔 내에는 로비, 바닥, 레스토랑, 체육관, 수영장 등 모든 전략적 지역 근처에 비콘 장치를 배치했습니다.

>[!NOTE]
>
>이 사용 사례에서는 Adobe Campaign Standard을 사용하여 메시지를 보냅니다.

이 사용 사례에서는 고객이 특정 비콘 근처에 있을 때 개인화된 메시지를 실시간으로 고객에게 보내는 방법을 알아봅니다.

우선 말튼 호텔에 들어가는 즉시 메시지를 보내려고 합니다. 지난 24시간 이내에 당사로부터 어떠한 연락도 받지 못한 경우에만 메시지를 보내려고 합니다.

그런 다음 두 가지 조건을 확인합니다.

* 이 사람이 충성도 멤버가 아닌 경우 충성도 멤버십 오퍼에 참여하기 위해 이메일을 보냅니다.
* 이 사람이 이미 충성도 멤버인 경우 룸 예약이 있는지 확인합니다.
   * 그렇지 않으면 객실 요금과 함께 푸시 알림을 보내드립니다.
   * 푸시 알림이 있으면 환영 푸시 알림을 보냅니다. 그리고 앞으로 6시간 이내에 식당에 들어오면 식사 할인이 포함된 푸시 알림을 보냅니다.

![](../assets/journeyuc2_29.png)

이 사용 사례에서는 두 개의 이벤트를 만들어야 합니다([이 페이지](../usecase/configuring-the-events.md) 참조).

* 고객이 호텔에 입장할 때 시스템에 푸시되는 로비 비콘 이벤트.
* 고객이 레스토랑에 입장할 때 푸시되는 레스토랑 비콘 이벤트입니다.

두 데이터 원본에 대한 연결을 구성해야 합니다([이 페이지](../usecase/configuring-the-data-sources.md) 참조).

* 두 조건(충성도 멤버십 및 마지막 연락 날짜)에 대한 정보와 메시지 개인화 정보를 검색할 수 있는 기본 제공 Adobe Experience Platform 데이터 소스입니다.
* 호텔 예약 시스템, 예약 상태 정보 검색.

## 전제 조건 {#prerequisites}

사용 사례에서는 세 가지 Adobe Campaign Standard 트랜잭션 메시지 템플릿을 디자인했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ko)를 참조하세요.

Adobe Campaign Standard은 이메일 및 푸시 알림을 보내도록 구성되어 있습니다.

Experience Cloud ID는 호텔 예약 시스템에서 고객을 식별하기 위한 키로 사용된다.

이벤트가 비콘 근처에서 감지되면 고객의 휴대폰에서 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송할 모바일 애플리케이션을 디자인해야 합니다.

충성도 멤버 필드는 사용자 지정 필드이며 특정 조직 ID에 대한 XDM에 추가되었습니다.
