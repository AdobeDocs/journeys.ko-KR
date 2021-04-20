---
product: adobe campaign
solution: Journey Orchestration
title: 고급 사용 사례
description: 여정 고급 활용 사례에 더 많은 정보 추가
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 4%

---


# 고급 사용 사례{#concept_vzy_ncy_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔에서는, 그들은 모든 전략적 지역에 비콘 장치를 배치했다:로비, 바닥, 레스토랑, 체육관, 수영장 등

>[!NOTE]
>
>이 경우 Adobe Campaign Standard을 사용하여 메시지를 보냅니다.

이 경우 고객에게 특정 비콘 근처를 통해 개인화된 메시지를 실시간으로 보내는 방법을 확인할 수 있습니다.

우선, 우리는 누군가가 말튼 호텔에 들어가는 즉시 메시지를 보내고 싶다. Adobe는 해당 사람이 지난 24시간 이내에 Adobe로부터 어떠한 연락도 받지 못한 경우에만 메시지를 보내려고 합니다.

그런 다음 두 가지 조건을 확인합니다.

* 이 사용자가 충성도 높은 멤버가 아닌 경우 충성도 멤버십 혜택에 가입할 수 있는 이메일을 보내드립니다.
* 이 사람이 이미 충성도 회원인 경우, 예약자가 있는지 확인합니다.
   * 그렇지 않으면 숙박료를 포함한 푸시 알림을 보냅니다.
   * 이 경우 환영 푸시 알림을 보냅니다. 그리고 그가 그 다음 6시간 내에 식당에 들어가면, 우리는 식사 할인이 포함된 푸시 알림을 그에게 보냅니다.

![](../assets/journeyuc2_29.png)

이 사용 사례를 보려면 두 개의 이벤트를 만들어야 합니다([이 페이지](../usecase/configuring-the-events.md) 참조).

* 고객이 호텔에 들어올 때 시스템으로 푸시될 로비 비콘 이벤트.
* 손님이 식당에 들어가면 푸시되는 레스토랑 비콘 이벤트.

두 데이터 소스에 대한 연결을 구성해야 합니다([이 페이지](../usecase/configuring-the-data-sources.md) 참조).

* 빌드-인 Adobe Experience Platform 데이터 소스로, 2가지 조건(충성도 멤버십과 마지막 연락처 날짜)에 대한 정보와 메시지 개인화 정보를 검색할 수 있습니다.
* 예약상태 정보를 찾기 위한 호텔 예약 시스템.

## 사전 요구 사항 {#prerequisites}

사용 사례를 위해 Adobe는 3개의 Adobe Campaign Standard 트랜잭션 메시지 템플릿을 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)를 참조하십시오.

Adobe Campaign Standard은 이메일 및 푸시 알림을 전송하도록 구성되어 있습니다.

Experience Cloud ID는 호텔 예약 시스템에서 고객을 식별하는 열쇠로 사용됩니다.

이벤트는 고객의 휴대 전화에서 비콘 근처에서 감지되면 전송됩니다. 모바일 애플리케이션을 설계하여 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송해야 합니다.

충성도 회원 필드는 사용자 지정 필드이며 특정 조직 ID에 대해 XDM에 추가되었습니다.
