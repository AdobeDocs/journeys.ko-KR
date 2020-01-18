---
title: 여정 통합 운영 정보
description: 고객 여정 통합 운영에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 여정 통합 운영 정보{#concept_nd3_mqt_52b}

이벤트 또는 데이터 소스에 저장된 컨텍스트 데이터를 활용하여 실시간 통합 활용 사례를 구축할 수 있습니다.

Journey Orchestration은 경험 플랫폼과 통합된 애플리케이션 서비스입니다.

![](../assets/journeydiagram.png)

고객 여정 통합 운영을 통해 이벤트, Adobe Experience Platform의 정보 또는 타사 API 서비스의 데이터를 기반으로 한 컨텍스트 기반의 실시간 통합 기능을 사용할 수 있습니다. 타사 시스템을 사용하여 메시지를 전송하는 경우 사용자 지정 작업을 구성할 수 있습니다. Adobe Campaign Standard가 있는 경우 Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS를 보낼 [수](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)있습니다.

이벤트 구성 탭에서 **기술 사용자가** 여정에서 예상되는 이벤트를 구성합니다. 들어오는 이벤트의 데이터는 XDM(Adobe Experience Data Model)에 따라 표준화됩니다. 이벤트는 인증되고 인증되지 않은 이벤트(예: Adobe Mobile SDK 이벤트)에 대한 스트리밍 통합 API에서 가져옵니다.

데이터 소스 구성 탭에서 **기술 사용자가** 구성합니다.

* 고객 여정 디자이너의 Adobe Experience Platform에서 제공하는 다양한 필드가 고객 경험 구축 및 개인화 목적으로 제공됩니다.
* 고객 여정 디자이너에서 활용할 수 있는 추가 사용자 지정 데이터 소스입니다. 사용자 지정 데이터 소스는 API를 통한 고객 여정 통합 운영 및 타사 시스템 또는 서비스 간의 연결입니다. 충성도 시스템과 같은 타사 시스템을 연결할 수 있습니다. 예를 들어 타사 서비스는 날씨 API일 수 있습니다.

고객 여정 디자이너를 통해 **비즈니스 사용자는** 시작 이벤트를 손쉽게 드래그 앤 드롭하고 조건을 추가하고 수행할 작업을 지정할 수 있습니다.

그런 다음 다음을 기준으로 조건을 만듭니다.

* time
* 이벤트 페이로드에서 가져오는 데이터
* 데이터 소스로부터 오는 정보:실시간 고객 프로파일 데이터 소스 또는 사용자 지정 데이터 소스

분할된 조건을 사용하여 여행중인 사람을 다른 방향으로 보낼 수 있습니다.

그런 다음 작업 활동을 사용하여 타사 시스템을 통해 메시지를 보낼 수 있습니다. Adobe Campaign Standard가 있는 경우 실시간으로 개인화된 SMS, 푸시 알림 또는 이메일을 전송할 수 있습니다.

고객 여정 통합 관리가 여러 단계로 이루어져 있으므로 고급 시나리오를 만들 수 있습니다. 예를 들어 첫 번째 이벤트와 작업 후에 다른 이벤트를 드래그할 수 있습니다. 그런 다음 두 번째 작업을 추가하고 대기 활동을 지정하여 잠시 기다렸다가 분할 조건을 추가하여 다른 두 개의 경로로 사람들을 푸시한 다음 다른 메시지를 전송할 수 있습니다.

>[!NOTE]
>
>이 설명서는 제품의 최근 변경 사항을 반영하도록 자주 업데이트됩니다. 그러나 일부 스크린샷은 제품의 인터페이스와 약간 다를 수 있습니다.

