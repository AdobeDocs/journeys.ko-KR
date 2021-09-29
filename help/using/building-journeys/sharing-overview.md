---
product: adobe campaign
title: 여정 단계 공유 개요
description: 여정 단계 공유 개요
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: ec5337e6b2df126370b55e1466fc5027659441fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 7%

---

# 여정 단계 공유 개요{#sharing-overview}

[!DNL Journey Orchestration] 은(는) 여정 성능 데이터를 Adobe Experience Platform에 자동으로 전송하므로 분석 목적으로 다른 데이터와 결합할 수 있습니다.

>[!NOTE]
>
>이 기능은 여정 단계 이벤트를 위한 모든 인스턴스에서 기본적으로 활성화됩니다. 여정 프로필 단계 이벤트의 경우 활성화는 요청 시 수행됩니다. 단계 이벤트를 프로비전하는 동안 생성된 스키마 및 데이터 세트는 수정하거나 업데이트할 수 없습니다. 기본적으로 이러한 스키마와 데이터 세트는 읽기 전용 모드입니다.

예를 들어, 여러 개의 이메일을 보내는 여정을 설정했습니다. 이 기능을 사용하면 [!DNL Journey Orchestration] 데이터를 전환 발생 횟수, 웹 사이트에서 발생한 참여 횟수 또는 저장소에서 발생한 트랜잭션 수와 같은 다운스트림 이벤트 데이터와 결합할 수 있습니다. 여정 정보를 다른 디지털 속성에서 또는 오프라인 속성에서 Adobe Experience Platform의 데이터와 결합하여 보다 포괄적인 성능 보기를 제공할 수 있습니다.

[!DNL Journey Orchestration] 은(는) 개별 여정에서 취하는 각 단계에 대해 필요한 스키마와 스트림을 Adobe Experience Platform에 데이터 세트로 자동 만듭니다. 단계 이벤트는 여정에서 한 노드에서 다른 노드로 이동하는 개별 이벤트에 해당합니다. 예를 들어 이벤트, 조건 및 작업이 있는 여정에서 3단계 이벤트가 Adobe Experience Platform에 전송됩니다.

전달되는 XDM 필드 목록은 포괄적입니다. 일부는 시스템 생성 코드를 포함하고 나머지는 읽을 수 있는 친숙한 이름을 가지고 있습니다. 예를 들면 여정 활동의 레이블이나 단계 상태가 있습니다. 오류가 발생하여 작업 시간이 초과되거나 종료된 횟수입니다.

>[!CAUTION]
>
>실시간 프로필 서비스에 대해 데이터 세트를 설정할 수 없습니다. **[!UICONTROL Profile]** 토글이 꺼져 있는지 확인하십시오.

여정은 스트리밍 방식으로 데이터가 발생하는 대로 데이터를 전송합니다. 쿼리 서비스를 사용하여 이 데이터를 쿼리할 수 있습니다. Customer Journey Analytics 또는 기타 BI 도구에 연결하여 이러한 단계와 관련된 데이터를 볼 수 있습니다.

다음 스키마가 만들어집니다.

* [!DNL Journey Orchestration]에 대한 여정 단계 프로필 이벤트 스키마 - 개별 여정 참여자에 매핑하기 위해 사용할 ID 맵과 함께 여정에서 수행되는 단계에 대한 경험 이벤트입니다.
* [!DNL Journey Orchestration]에 대한 여정 단계 이벤트 스키마 - 여정 메타데이터에 연결된 여정 단계 이벤트입니다.
* [!DNL Journey Orchestration]에 대한 여정 필드가 있는 여정 스키마 - 여정을 설명하는 여정 메타데이터입니다.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

다음 데이터 세트가 전달됩니다.

* [!DNL Journey Orchestration]에 대한 여정 단계 프로필 이벤트 스키마
* 여정 단계 이벤트
* 여정

![](../assets/sharing3.png)

Adobe Experience Platform에 전달된 XDM 필드 목록은 여기에서 자세히 설명합니다.

* [journeySteps 이벤트 공통 필드](../building-journeys/sharing-common-fields.md)
* [journeyStep 이벤트 작업 실행 필드](../building-journeys/sharing-execution-fields.md)
* [journeyStep 이벤트 데이터 가져오기 필드](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 이벤트 ID 필드](../building-journeys/sharing-identity-fields.md)
* [여정 필드](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platform에 보고하는 단계 이벤트에 대한 자세한 내용은 이 [튜토리얼 비디오](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)를 시청하십시오.
