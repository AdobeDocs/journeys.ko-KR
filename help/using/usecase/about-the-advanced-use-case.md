---
title: 고급 사용 사례 정보
description: 고급 활용 사례 활용 사례
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 고급 사용 사례 정보{#concept_vzy_ncy_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔에서는, 그들은 모든 전략 지역 근처에 비콘 장치를 배치했습니다.로비, 바닥, 레스토랑, 체육관, 수영장 등

>[!NOTE]
>
>이 경우 Adobe Campaign Standard를 사용하여 메시지를 보냅니다.

이 사용 사례에서는 고객이 특정 비콘 근처에 있을 때 개인화된 메시지를 실시간으로 보내는 방법을 확인할 수 있습니다.

우선, 우리는 사람이 말튼 호텔에 들어가자마자 메시지를 보내고 싶다. 지난 24시간 이내에 본사로부터 어떠한 연락도 받지 못한 경우에만 메시지를 보내려고 합니다.

그런 다음 두 가지 조건을 확인합니다.

* 이 사람이 충성도 회원이 아닌 경우 충성도 멤버십 프로모션에 참여하기 위해 이메일을 보냅니다.
* 이 사람이 이미 충성도 회원인 경우 예약자가 있는지 확인합니다.
   * 그렇지 않으면 숙박료가 포함된 푸시 알림을 보내드리겠습니다
   * 만약 그렇다면, 우리는 그에게 환영 푸시 알림을 보냅니다. 그리고 그 사람이 6시간 내에 식당에 들어가면 식사할 때 할인율이 적용되는 푸시 알림을 보내드립니다.

![](../assets/journeyuc2_29.png)

이 사용 사례의 경우 다음 두 개의 이벤트를 만들어야 합니다( [](../usecase/configuring-the-events.md)참조).

* 고객이 호텔로 들어올 때 시스템으로 푸시될 로비 비콘 이벤트입니다.
* 고객이 식당에 들어올 때 푸시될 레스토랑 비콘 이벤트입니다.

다음 두 데이터 소스에 대한 연결을 구성해야 합니다( [](../usecase/configuring-the-data-sources.md)참조).

* Adobe의 두 가지 조건(충성도 멤버십 및 마지막 연락처 날짜)과 메시지 개인화 정보에 대한 정보를 검색할 수 있는 내장된 경험 플랫폼 데이터 소스입니다.
* 예약 상태 정보를 찾기 위해 호텔 예약 시스템

## 전제 조건 {#prerequisites}

사용 사례를 위해 Adobe는 세 개의 Adobe Campaign Standard 트랜잭션 메시지 템플릿을 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지를](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)참조하십시오.

Adobe Campaign Standard는 이메일 및 푸시 알림을 전송하도록 구성되어 있습니다.

Experience Cloud ID는 호텔 예약 시스템에서 고객을 식별하는 키로 사용됩니다.

이벤트는 고객의 휴대폰에서 신호 정보 근처에서 감지되면 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송하려면 모바일 애플리케이션을 설계해야 합니다.

충성도 회원 필드는 사용자 지정 필드이며 특정 조직 ID에 대해 XDM에 추가되었습니다.
