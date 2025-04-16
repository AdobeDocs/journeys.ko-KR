---
product: adobe campaign
title: 이벤트 정보
description: 이벤트에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# 일반 원칙 {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer를 찾고 계신가요**? [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하여 Journey Optimizer 설명서를 확인할 수 있습니다.
>
>
>_이 설명서는 Journey Optimizer로 대체된 이전 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="이벤트 정보"
>abstract="특정 사용자에게 연결되는 이벤트는 한 사람의 행동 또는 한 사람과 연관되어 일어나는 일에 관한 것입니다. [!DNL Journey Orchestration]은 여정에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다."

특정 사용자에게 연결되는 이벤트는 이는 사람의 행동(예: 제품 구매, 매장 방문, 웹 사이트 종료 등) 또는 사람과 관련된 일(예: 로열티 포인트 10,000점 도달)과 관련이 있습니다. [!DNL Journey Orchestration]은 여정에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다.

[!DNL Journey Orchestration]은 이벤트를 수신하도록 설계되어 있으므로 이 구성은 **필수** 작업이며, 항상 **기술 사용자**&#x200B;가 수행해야 합니다.

이벤트 구성에서는 [!DNL Journey Orchestration]이 이벤트로 수신할 정보를 정의할 수 있습니다. 여정의 각 단계에서 여러 이벤트를 사용할 수 있으며, 여러 여정에서 같은 이벤트를 사용할 수도 있습니다.

초안 또는 라이브 여정에서 사용되는 이벤트를 편집할 때는 이름, 설명 또는 페이로드 필드만 변경할 수 있습니다. 여정 손상 방지를 위해 초안 또는 라이브 여정 편집은 엄격히 제한됩니다.

다음과 같은 두 가지 유형의 이벤트를 정의할 수 있습니다.

* **규칙 기반** 이벤트: 이 유형의 이벤트는 eventID를 생성하지 않습니다. 간단한 표현식 편집기를 사용하면 시스템에서 여정을 트리거할 관련 이벤트를 식별하는 데 사용할 규칙을 간단히 정의할 수 있습니다. 이 규칙은 프로필의 위치 또는 프로필의 장바구니에 추가한 항목 수와 같은 이벤트 페이로드에서 사용할 수 있는 필드를 기반으로 할 수 있습니다.

  >[!CAUTION]
  >
  >상한 설정 규칙은 규칙 기반 이벤트에 대해 정의됩니다. 여정이 주어진 조직(ORG)에 대해 처리할 수 있는 적격한 이벤트 수를 초당 5000개로 제한합니다. Journey Orchestration SLA에 해당합니다. 이 [페이지](https://helpx.adobe.com/kr/legal/product-descriptions/journey-orchestration.html)를 참조하십시오.

* **시스템 생성** 이벤트: 이러한 이벤트에는 eventID가 필요합니다. 이 eventID 필드는 이벤트를 만들 때 자동으로 생성됩니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 전달해야 합니다.

Journey Orchestration을 사용하려면 이벤트를 스트리밍하거나 Adobe Experience Platform으로 배치해야 합니다. 이 데이터가 반드시 실시간 프로필로 이동할 필요는 없습니다. 별도의 여정에서 세그멘테이션 또는 조회에 이벤트를 사용하려면 프로필에 데이터 세트를 활성화하는 것이 좋습니다.

이벤트를 만드는 방법에 대해 알아보려면 이 [페이지](../event/about-creating.md)를 참조하십시오.
