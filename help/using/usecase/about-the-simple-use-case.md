---
product: adobe campaign
title: 단순 사용 사례 정보
description: 여정의 간단한 사용 사례에 더 많이 의존하십시오.
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 6%

---

# 단순 사용 사례 정보{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


## 용도 {#purpose}

말튼이라는 호텔 브랜드를 예로 들어 보자. 호텔 내에는 로비, 바닥, 레스토랑, 체육관, 수영장 등 모든 전략적 지역 근처에 비콘 장치를 배치했습니다.

이 사용 사례에서는 스파 근처에 있는 비콘 옆에 걷는 사람에게 개인화된 메시지를 실시간으로 보내는 방법을 알아봅니다.

우리는 그 사람이 여자일 경우에만 메시지를 보내고 싶습니다. 메시지는 초 내에 수신해야 합니다.

![](../assets/journeyuc1_16.png)

## 전제 조건 {#prerequisites}

사용 사례로는 Adobe Campaign Standard에서 이메일 트랜잭션 메시지 템플릿 1개를 설계했습니다. 이벤트 트랜잭션 메시지 템플릿을 사용하고 있습니다. 이 [페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ko)를 참조하세요.

Adobe Campaign Standard이 이메일을 보내도록 구성되어 있습니다.

이벤트는 비콘 근처에서 감지되면 고객의 휴대폰에서 전송됩니다. 고객의 휴대폰에서 Mobile SDK으로 이벤트를 전송할 모바일 애플리케이션을 디자인해야 합니다.
