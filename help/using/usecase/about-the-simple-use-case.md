---
title: 간단한 사용 사례 정보
description: 간단한 사용 사례를 통한 고객 여정 강화
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


# 간단한 사용 사례 정보{#concept_grh_vby_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔에서는, 그들은 모든 전략 지역 근처에 비콘 장치를 배치했습니다.로비, 바닥, 레스토랑, 체육관, 수영장 등

이 사용 사례에서는 스파 근처에 위치한 비콘 옆에서 걷는 사람에게 개인화된 메시지를 실시간으로 보내는 방법을 확인할 수 있습니다.

우리는 그 사람이 여성일 경우에만 메시지를 보내고 싶습니다. 몇 초 내에 메시지를 수신해야 합니다.

![](../assets/journeyuc1_16.png)

## 전제 조건 {#prerequisites}

Adobe는 Adobe Campaign Standard에서 하나의 이메일 트랜잭션 메시지 템플릿을 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지를](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)참조하십시오.

Adobe Campaign Standard는 이메일을 전송하도록 구성되어 있습니다.

이벤트는 고객 휴대폰에서 비콘 근처에서 감지되면 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송하려면 모바일 애플리케이션을 설계해야 합니다.