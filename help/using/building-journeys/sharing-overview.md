---
product: adobe campaign
solution: Journey Orchestration
title: 여정 단계 공유 개요
description: 여정 단계 공유 개요
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# 여정 단계 공유 개요{#sharing-overview}

[!DNL Journey Orchestration] 고객 여정 성능 데이터를 Adobe Experience Platform에 자동으로 전송하여 분석 목적으로 다른 데이터와 결합할 수 있습니다.

>[!NOTE]
>
>이 기능은 새로 배포된 모든 인스턴스에서 기본적으로 활성화되지 않습니다. 정품 인증은 요청 시 진행됩니다.

예를 들어, 여러 개의 이메일을 보내는 여행을 설정했습니다. 이 기능을 사용하면 [!DNL Journey Orchestration] 데이터를 전환 횟수, 웹 사이트에서 발생한 참여 횟수, 스토어에서 발생한 트랜잭션 수 등과 같은 다운스트림 이벤트 데이터와 결합할 수 있습니다. 고객 경로 정보는 다른 디지털 속성 또는 오프라인 속성에서 Adobe Experience Platform의 데이터와 결합하여 보다 포괄적인 성능 보기를 제공할 수 있습니다.

[!DNL Journey Orchestration] 자동으로 필요한 스키마와 스트림을 Adobe Experience Platform에 자동으로 생성하여 각 단계에서 개별 사용자가 이동할 때마다로 스트리밍할 수 있습니다. 단계 이벤트는 한 경로에서 한 노드에서 다른 노드로 이동하는 개별 노드에 해당합니다. 예를 들어 이벤트, 조건 및 작업이 있는 여행에서 3단계 이벤트가 Adobe Experience Platform으로 전송됩니다.

전달되는 XDM 필드 목록은 포괄적입니다. 어떤 것은 시스템 생성 코드를 포함하고 다른 것들은 사람이 읽을 수 있는 친근한 이름을 가지고 있다. 여기에는 경로 활동 레이블 또는 단계 상태가 포함됩니다.작업 시간이 초과되었거나 오류로 종료된 횟수입니다.

>[!CAUTION]
>
>실시간 프로필 서비스에 대해 데이터 세트를 설정할 수 없습니다. **[!UICONTROL Profile]** 토글이 꺼져 있는지 확인하십시오.

Journey는 데이터를 스트리밍하는 방식으로 제공합니다. 쿼리 서비스를 사용하여 이 데이터를 쿼리할 수 있습니다. Customer Journey Analytics 또는 다른 BI 도구에 연결하여 이러한 단계와 관련된 데이터를 볼 수 있습니다.

다음 스키마가 생성됩니다.

* [!DNL Journey Orchestration]에 대한 경로 단계 프로필 이벤트 스키마 - 개별 경로 참가자에 매핑하는 데 사용할 ID 맵과 함께 여정에서 수행한 단계에 대한 경험 이벤트.
* [!DNL Journey Orchestration]에 대한 경로 단계 이벤트 스키마 - 경로 메타데이터에 연결된 경로 단계 이벤트입니다.
* [!DNL Journey Orchestration]에 대한 경로 필드가 있는 경로 스키마 - 여행을 설명하는 경로 메타데이터.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

다음 데이터 세트가 전달됩니다.

* [!DNL Journey Orchestration]에 대한 경로 단계 프로필 이벤트 스키마
* 고객 여정 단계 이벤트
* 여정

![](../assets/sharing3.png)

Adobe Experience Platform에 전달된 XDM 필드 목록은 다음과 같습니다.

* [journeySteps 이벤트 공통 필드](../building-journeys/sharing-common-fields.md)
* [journeyStep 이벤트 작업 실행 필드](../building-journeys/sharing-execution-fields.md)
* [journeyStep 이벤트 데이터 가져오기 필드](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 이벤트 ID 필드](../building-journeys/sharing-identity-fields.md)
* [경로 필드](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platform에 대한 단계 이벤트 보고에 대한 자세한 내용은 이 [자습서 비디오](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)를 참조하십시오.
