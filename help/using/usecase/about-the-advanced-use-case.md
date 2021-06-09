---
product: adobe campaign
title: 고급 사용 사례
description: 여정 고급 사용 사례에 대해 자세히 알아보십시오
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 3af822bacfd1a5a53ec7280dff1136d77b90c809
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 2%

---

# 고급 사용 사례{#concept_vzy_ncy_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔들에서, 그들은 모든 전략적 지역들 근처에 비콘 장치들을 배치했습니다.로비, 바닥, 레스토랑, 체육관, 수영장 등

>[!NOTE]
>
>이 사용 사례에서는 Adobe Campaign Standard을 사용하여 메시지를 보냅니다.

이 사용 사례에서는 고객이 특정 비콘 근처를 걸을 때 개인화된 메시지를 실시간으로 고객에게 전송하는 방법을 살펴봅니다.

우선 말보로 호텔에 들어가는 즉시 메시지를 보내겠습니다. 지난 24시간 내에 연락이 없는 경우에만 메시지를 보내려고 합니다.

그런 다음 두 가지 조건을 확인합니다.

* 이 사람이 충성도 멤버가 아닌 경우 충성도 멤버십 오퍼에 참여하기 위한 이메일을 보냅니다.
* 이 사람이 이미 충성도 멤버인 경우 객실 예약이 있는지 확인합니다.
   * 그렇지 않으면 숙박료가 포함된 푸시 알림을 보냅니다.
   * 이 경우 환영 푸시 알림을 보냅니다. 그리고 6시간 내에 레스토랑에 입장하면 식사 할인이 있는 푸시 알림을 보내드립니다.

![](../assets/journeyuc2_29.png)

이 사용 사례에서는 두 개의 이벤트를 만들어야 합니다( [이 페이지](../usecase/configuring-the-events.md) 참조).

* 고객이 호텔로 들어올 때 시스템에 푸시될 로비 비콘 이벤트입니다.
* 고객이 레스토랑에 입장할 때 푸시되는 레스토랑 비콘 이벤트입니다.

두 데이터 소스에 대한 연결을 구성해야 합니다( [이 페이지](../usecase/configuring-the-data-sources.md) 참조).

* 기본 제공 Adobe Experience Platform 데이터 소스는 두 가지 조건(충성도 멤버십 및 마지막 연락처 날짜)과 메시지 개인화 정보를 검색할 수 있도록 해줍니다.
* 예약 상태 정보를 검색하기 위한 호텔 예약 시스템.

## 사전 요구 사항 {#prerequisites}

사용 사례를 위해 세 개의 Adobe Campaign Standard 트랜잭션 메시지 템플릿을 디자인했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html)을 참조하십시오.

Adobe Campaign Standard은 이메일 및 푸시 알림을 전송하도록 구성되어 있습니다.

Experience Cloud ID는 호텔 예약 시스템에서 고객을 식별하는 키로 사용됩니다.

이벤트가 비콘 근처에서 감지되면 고객의 휴대폰에서 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송하려면 모바일 애플리케이션을 설계해야 합니다.

충성도 멤버 필드는 사용자 지정 필드이며 특정 조직 ID에 대해 XDM에 추가되었습니다.
