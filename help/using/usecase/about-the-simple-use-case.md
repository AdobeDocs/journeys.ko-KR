---
product: adobe campaign
solution: Journey Orchestration
title: 단순 사용 사례
description: 여정의 간단한 사용 사례 자세히 보기
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 11%

---


# 단순 사용 사례{#concept_grh_vby_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔에서는, 그들은 모든 전략적 지역에 비콘 장치를 배치했다:로비, 바닥, 레스토랑, 체육관, 수영장 등

이 경우, 스파 근처에 위치한 비콘 옆에서 걷는 사람에게 개인화된 메시지를 실시간으로 보내는 방법을 확인할 수 있습니다.

우리는 그 사람이 여성일 경우에만 메시지를 보내고 싶다. 몇 초 내에 메시지를 수신해야 합니다.

![](../assets/journeyuc1_16.png)

## 사전 요구 사항 {#prerequisites}

Adobe는 Adobe Campaign Standard에서 이메일 트랜잭션 메시지 템플릿을 하나로 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)를 참조하십시오.

Adobe Campaign Standard은 이메일을 전송하도록 구성되어 있습니다.

이벤트는 고객의 휴대 전화에서 비콘 근처에서 감지되면 전송됩니다. 모바일 애플리케이션을 설계하여 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송해야 합니다.