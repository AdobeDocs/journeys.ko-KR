---
title: 고객 여정 단계 공유 개요
description: 고객 여정 단계 공유 개요
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
source-git-commit: 26246bd44407a818afba8b80513cb62da9cf6ebd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---


# 고객 여정 단계 공유 개요{#sharing-overview}

고객 여정 운영(Journey Orchestration)은 Adobe Experience Platform으로 고객 여정 성능 데이터를 자동으로 전송하므로 다른 데이터와 결합하여 분석할 수 있습니다.

예를 들어, 여러 개의 이메일을 전송하는 경로를 설정했습니다. 이 기능을 사용하면 전환 발생 횟수, 웹 사이트에서 발생한 참여 횟수, 스토어에서 발생한 트랜잭션 수와 같은 다운스트림 이벤트 데이터와 고객 여정 오케스트레이션 데이터를 결합할 수 있습니다. 고객 여정 정보는 다른 디지털 속성이나 오프라인 속성에서 플랫폼의 데이터와 결합하여 보다 포괄적인 성능 보기를 제공합니다.

고객 여정 운영(Journey Orchestration)은 개별 고객이 한 번에 거치는 각 단계를 위해 필요한 스키마와 데이터 세트에 스트림을 자동으로 생성합니다. 단계 이벤트는 경로의 한 노드에서 다른 노드로 이동하는 개별 이벤트에 해당합니다. 예를 들어, 이벤트, 조건 및 작업이 있는 여행에서는 세 개의 단계 이벤트가 플랫폼으로 전송됩니다.

전달된 XDM 필드 목록은 포괄적입니다. 일부는 시스템 생성 코드를 포함하며 다른 일부는 읽을 수 있는 친근한 이름을 가지고 있다. 여기에는 경로 활동의 레이블이나 단계 상태가 포함됩니다. 작업 시간이 초과되었거나 오류로 종료된 횟수입니다.

>[!CAUTION]
>
>기본적으로 데이터 세트는 실시간 프로필 서비스에 대해 활성화되지 않습니다. 프로필 서비스에서 데이터 세트를 사용하려면 데이터 세트를 활성화해야 합니다(**프로필** 전환). 많은 양의 이벤트가 할당량의 저장 공간을 차지한다는 점을 주의하십시오. 프로필에 대한 데이터 세트를 활성화하기 전에 주의해서 진행하십시오
>
>![](../assets/sharing4.png)

Journey는 데이터 발생 시 스트리밍 방식으로 데이터를 전송합니다. 쿼리 서비스를 사용하여 이 데이터를 쿼리할 수 있습니다. 고객 경로 분석 또는 기타 BI 도구에 연결하여 이러한 단계와 관련된 데이터를 볼 수 있습니다.

다음 스키마가 생성됩니다.

* 여정 오케스트레이션을 위한 여정 단계 프로필 이벤트 스키마 - 개별 경로 참가자에 매핑하는 데 사용할 ID 맵과 함께 여정에서 수행한 단계에 대한 경험 이벤트.
* 여정 편성 - 경로 지정 메타데이터에 연결된 여정 단계 이벤트.
* 여정 통합 관리를 위한 경로 필드가 포함된 여정 스키마 - 여정 메타데이터를 사용하여 여정 경로를 설명할 수 있습니다.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

다음 데이터 집합이 전달됩니다.

* 여정 관리 편성을 위한 여정 단계 프로필 이벤트 스키마
* 고객 여정 단계 이벤트
* 여정

![](../assets/sharing3.png)

플랫폼에 전달되는 XDM 필드 목록은 다음과 같습니다.

* [journeySteps events 일반 필드](../building-journeys/sharing-common-fields.md)
* [journeyStep events 작업 실행 필드](../building-journeys/sharing-execution-fields.md)
* [journeyStep 이벤트 데이터 가져오기 필드](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 이벤트 ID 필드](../building-journeys/sharing-identity-fields.md)
* [경로 필드](../building-journeys/sharing-journey-fields.md)

