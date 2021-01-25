---
product: adobe campaign
solution: Journey Orchestration
title: 이벤트
description: 이벤트에 대해 알아보기
translation-type: ht
source-git-commit: 3dd7cd4dc4e4398b029dd1becd11c8dd7e7c3542
workflow-type: ht
source-wordcount: '374'
ht-degree: 100%

---


# 일반 원칙 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="이벤트"
>abstract="특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. [!DNL Journey Orchestration]은 여정에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다."

특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. [!DNL Journey Orchestration]은 여정에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다.

[!DNL Journey Orchestration]은 이벤트를 수신하도록 설계되어 있으므로 이 구성은 **필수** 작업이며, 항상 **기술 사용자**&#x200B;가 수행해야 합니다.

이벤트 구성에서는 [!DNL Journey Orchestration]이 이벤트로 수신할 정보를 정의할 수 있습니다. 여정의 각 단계에서 여러 이벤트를 사용할 수 있으며, 여러 여정에서 같은 이벤트를 사용할 수도 있습니다.

초안 또는 라이브 여정에서 사용되는 이벤트를 편집할 때는 이름, 설명 또는 페이로드 필드만 변경할 수 있습니다. 여정 손상 방지를 위해 초안 또는 라이브 여정 편집은 엄격히 제한됩니다.

다음과 같은 두 가지 유형의 이벤트를 정의할 수 있습니다.

* **규칙 기반** 이벤트: 이 유형의 이벤트는 eventID를 생성하지 않습니다. 간단한 표현식 편집기를 사용하면 시스템에서 여정을 트리거할 관련 이벤트를 식별하는 데 사용할 규칙을 간단히 정의할 수 있습니다. 이 규칙은 프로필의 위치 또는 프로필의 장바구니에 추가한 항목 수와 같은 이벤트 페이로드에서 사용할 수 있는 필드를 기반으로 할 수 있습니다.

   >[!CAUTION]
   >
   >최대 가용량 규칙은 규칙 기반 이벤트에 대해 정의됩니다. 여정이 주어진 조직(ORG)에 대해 처리할 수 있는 적격한 이벤트 수를 초당 5000개로 제한합니다. Journey Orchestration SLA에 해당합니다. 이 [페이지](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html)를 참조하십시오.

* **시스템 생성** 이벤트: 이러한 이벤트에는 eventID가 필요합니다. 이 eventID 필드는 이벤트를 만들 때 자동으로 생성됩니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 전달해야 합니다.

이벤트를 만드는 방법에 대해 알아보려면 이 [페이지](../event/about-creating.md)를 참조하십시오.

