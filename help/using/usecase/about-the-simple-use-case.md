---
product: adobe campaign
title: 단순 사용 사례
description: 여정 단순 사용 사례에 대해 자세히 알아보기
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 3af822bacfd1a5a53ec7280dff1136d77b90c809
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 6%

---

# 단순 사용 사례{#concept_grh_vby_w2b}

## 목적 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어보자. 그들의 호텔들에서, 그들은 모든 전략적 지역들 근처에 비콘 장치들을 배치했습니다.로비, 바닥, 레스토랑, 체육관, 수영장 등

이 사용 사례에서는 spa 근처에 있는 비콘 옆에 있는 사람에게 개인화된 메시지를 실시간으로 보내는 방법을 살펴봅니다.

우리는 그 사람이 여성일 경우에만 메시지를 보내고 싶습니다. 메시지를 몇 초 이내에 수신해야 합니다.

![](../assets/journeyuc1_16.png)

## 사전 요구 사항 {#prerequisites}

사용 사례를 위해 Adobe Campaign Standard에 이메일 트랜잭션 메시지 템플릿 1개를 디자인했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html)을 참조하십시오.

Adobe Campaign Standard이 이메일을 보내도록 구성되어 있습니다.

이벤트가 비콘 근처에서 감지되면 고객의 휴대폰에서 전송됩니다. 고객의 휴대폰에서 Mobile SDK로 이벤트를 전송하려면 모바일 애플리케이션을 설계해야 합니다.
