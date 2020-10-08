---
title: 고급 사용 사례
description: 고급 활용 사례 활용 사례 보기
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
source-wordcount: '414'
ht-degree: 5%

---


# 고급 사용 사례{#concept_vzy_ncy_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 이들 호텔들은 모든 전략적 지역에 비콘 장비를 배치했다.로비, 바닥, 레스토랑, 체육관, 수영장 등

>[!NOTE]
>
>이 경우에는 Adobe Campaign Standard을 사용하여 메시지를 보냅니다.

이 경우 고객에게 특정 비콘 가까이 이동할 때 개인화된 메시지를 실시간으로 보내는 방법을 확인할 수 있습니다.

먼저 말보로 호텔에 도착하자마자 메시지를 보내자. Adobe는 지난 24시간 이내에 Adobe로부터 어떠한 연락도 받지 못한 경우에만 메시지를 보내려고 합니다.

그런 다음 두 가지 조건을 확인합니다.

* 이 사람이 충성도 멤버가 아닌 경우 충성도 멤버십 혜택에 가입하기 위한 이메일을 보냅니다.
* 이 사람이 이미 충성도 회원인 경우, 방 예약이 있는지 확인합니다.
   * 그렇지 않다면, 우리는 그에게 숙박료가 포함된 푸시 알림을 보낸다.
   * 만약 있다면, 우리는 그에게 환영 푸시 알림을 보냅니다. 그리고 그 사람이 6시간 내에 식당에 들어가면 식사 할인이 포함된 푸시 알림을 보내드립니다.

![](../assets/journeyuc2_29.png)

이 사용 사례의 경우 다음 두 개의 이벤트를 만들어야 합니다(참조 [](../usecase/configuring-the-events.md)).

* 고객이 호텔에 들어갈 때 시스템으로 보내질 로비 비콘 이벤트.
* 손님이 식당에 들어오면 푸시될 레스토랑 비콘 이벤트.

두 데이터 소스에 대한 연결을 구성해야 합니다(참조 [](../usecase/configuring-the-data-sources.md)).

* 메시지 개인화 정보는 물론, Adobe의 두 가지 조건(충성도 멤버십과 마지막 연락처 날짜)에 대한 정보를 검색하기 위한 내장 Adobe Experience Platform 데이터 소스입니다.
* 예약상태 정보를 찾기 위한 호텔 예약 시스템.

## 사전 요구 사항 {#prerequisites}

사용 사례를 위해 3개의 Adobe Campaign Standard 트랜잭션 메시지 템플릿을 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. Refer to this [page](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard은 이메일 및 푸시 알림을 전송하도록 구성되어 있습니다.

Experience Cloud ID는 호텔 예약 시스템에서 고객을 식별하는 열쇠로 사용됩니다.

이벤트는 고객의 휴대폰에서 비콘 근처에서 감지되면 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송하려면 모바일 애플리케이션을 설계해야 합니다.

충성도 회원 필드는 사용자 지정 필드이며 특정 조직 ID에 대해 XDM에 추가되었습니다.
