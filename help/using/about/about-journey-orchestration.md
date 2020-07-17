---
title: Journey Orchestration
description: Journey Orchestration에 대해 자세히 알아보십시오
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 13%

---


# 정보 [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

이벤트나 데이터 소스에 저장된 상황별 데이터를 활용하여 실시간 오케스트레이션 사용 사례를 작성할 수 있습니다.

[!DNL Journey Orchestration] 는 Adobe Experience Platform과 통합된 응용 프로그램 서비스입니다.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] 이벤트, Adobe Experience Platform의 정보 또는 타사 API 서비스의 데이터를 기반으로 컨텍스트 기반의 실시간 오케스트레이션을 구현할 수 있습니다. 타사 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 구성할 수 있습니다. Adobe Campaign Standard이 있는 경우 Adobe Campaign Standard의 [트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 전송할 수 있습니다](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

이벤트 구성 탭에서 **기술 사용자가** 여정에서 예상 이벤트를 구성합니다. 들어오는 이벤트의 데이터는 XDM(Adobe Experience Data Model)에 따라 표준화됩니다. 이벤트는 인증된 이벤트와 인증되지 않은 이벤트(예: Adobe Mobile SDK 이벤트)에 대한 스트리밍 통합 API에서 가져옵니다.

데이터 소스 구성 탭에서 **기술 사용자가** 구성합니다.

* 조건 구축 및 개인화를 위해 고객 여정 디자이너의 Adobe Experience Platform에서 노출된 다양한 필드
* 고객 여정 디자이너의 데이터 활용 사용자 지정 데이터 소스는 API를 통해 타사 시스템 [!DNL Journey Orchestration] 또는 서비스 간의 연결입니다. 충성도 시스템과 같은 타사 시스템을 연결할 수 있습니다. 예를 들어 날씨 API와 같은 타사 서비스가 있을 수 있습니다.

고객 여정 디자이너를 사용하면 **비즈니스** 사용자는 시작 이벤트를 드래그 앤 드롭하고 조건을 추가하고 수행할 작업을 쉽게 지정할 수 있습니다.

그런 다음 다음을 기준으로 조건을 만듭니다.

* time
* 이벤트 페이로드에서 오는 데이터
* 데이터 소스에서 정보 수집: 실시간 고객 프로필 데이터 소스 또는 사용자 지정 데이터 소스

분할된 조건을 사용하여 여행중인 사람들을 다른 방향으로 보낼 수 있습니다.

그런 다음 작업 활동을 사용하여 타사 시스템을 통해 메시지를 보낼 수 있습니다. Adobe Campaign Standard이 있는 경우 실시간으로 개인화된 SMS, 푸시 알림 또는 이메일을 전송할 수 있습니다.

여러 단계 [!DNL Journey Orchestration] 와 마찬가지로 고급 시나리오를 만들 수 있습니다. 예를 들어 첫 번째 이벤트와 작업 후에 다른 이벤트를 드래그할 수 있습니다. 그런 다음 두 번째 작업을 추가하고 대기 활동을 지정하여 잠시 기다렸다가 분할 조건을 추가하여 사람들을 두 개의 다른 경로로 푸시하고 다른 메시지를 전송할 수 있습니다.

>[!NOTE]
>
>이 설명서는 제품의 최근 변경 사항을 반영하여 자주 업데이트됩니다. 그러나 실제 제품 인터페이스와 약간 다른 스크린샷도 있습니다.
