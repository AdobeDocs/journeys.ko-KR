---
product: adobe campaign
title: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마 정보 '
description: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마에 대해 알아봅니다 '
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 3a0fc5cd6b7bc4177ab50986b11b020a11a72c9b
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# 용 ExperienceEvent 스키마 [!DNL Journey Orchestration] 이벤트

[!DNL Journey Orchestration] 이벤트는 스트리밍 수집을 통해 Adobe Experience Platform으로 전송되는 XDM 경험 이벤트입니다.

그러므로, [!DNL Journey Orchestration] 는 Adobe Experience Platform의 Experience 데이터 모델(또는 XDM) 및 XDM 경험 이벤트 스키마를 구성하는 방법과 XDM 형식 데이터를 Adobe Experience Platform으로 스트리밍하는 방법에 대해 알고 있습니다.

## 스키마 요구 사항 [!DNL Journey Orchestration] 이벤트

에 대한 이벤트를 설정하는 첫 번째 단계입니다 [!DNL Journey Orchestration] 이벤트를 나타내기 위해 정의된 XDM 스키마와 Adobe Experience Platform에서 이벤트의 인스턴스를 기록하도록 만들어진 데이터 세트가 있는지 확인합니다. 이벤트에 대한 데이터 세트가 반드시 필요한 것은 아니지만 특정 데이터 세트에 이벤트를 보내면 향후 참조 및 분석을 위해 사용자의 이벤트 내역을 유지할 수 있으므로 항상 좋은 생각입니다. 이벤트에 적절한 스키마와 데이터 세트가 아직 없는 경우 Adobe Experience Platform 웹 인터페이스에서 이러한 두 작업을 모두 수행할 수 있습니다.

![](../assets/schema1.png)

에 사용될 모든 XDM 스키마 [!DNL Journey Orchestration] 이벤트는 다음 요구 사항을 충족해야 합니다.

* 스키마는 XDM ExperienceEvent 클래스여야 합니다.

   ![](../assets/schema2.png)

* 시스템에서 생성한 이벤트의 경우, 스키마에 Orchestration eventID mixin이 포함되어야 합니다. [!DNL Journey Orchestration] 이 필드를 사용하여 여정에 사용되는 이벤트를 식별합니다.

   ![](../assets/schema3.png)

* 이벤트의 제목을 식별할 ID 필드를 선언합니다. ID를 지정하지 않은 경우 ID 맵을 사용할 수 있습니다. 이러한 방법은 권장되지 않습니다.

   ![](../assets/schema4.png)

* 이 데이터를 여정에서 나중에 조회할 수 있게 하려면 해당 스키마 및 데이터 세트 프로필 을 표시합니다.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 사용자 정보, 이벤트가 생성된 장치, 위치 또는 이벤트와 관련된 기타 의미 있는 상황과 같이, 이벤트에 포함할 다른 컨텍스트 데이터를 캡처하려면 데이터 필드를 자유롭게 포함할 수 있습니다.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)

## 스키마 관계 활용{#leverage_schema_relationships}

Adobe Experience Platform을 사용하면 한 데이터 세트를 다른 데이터 세트에 대한 조회 테이블로 사용하기 위해 스키마 간의 관계를 정의할 수 있습니다.

브랜드 데이터 모델에 구매 스키마 캡처 가 있다고 가정합니다. 제품 카탈로그에 대한 스키마도 있습니다. 구매 스키마에서 제품 ID를 캡처하고 관계를 사용하여 제품 카탈로그에서 보다 완벽한 제품 세부 사항을 조회할 수 있습니다. 이를 통해 모든 랩톱 ID를 명시적으로 나열하거나 트랜잭션 시스템에서 모든 제품 세부 사항을 캡처하지 않고도 랩톱 컴퓨터를 구입한 모든 고객을 위해 세그먼트를 만들 수 있습니다.

관계를 정의하려면 소스 스키마에 전용 필드가 있어야 합니다. 이 경우 구매 스키마의 제품 ID 필드가 있어야 합니다. 이 필드는 대상 스키마의 제품 ID 필드를 참조해야 합니다. 프로필에 대해 소스 및 대상 테이블을 활성화해야 하며 대상 스키마에는 기본 ID로 정의된 공통 필드가 있어야 합니다.

다음은 제품 ID가 기본 ID로 정의된 프로필에 대해 활성화된 제품 카탈로그 스키마입니다.

![](../assets/schema9.png)

다음은 제품 ID 필드에 정의된 관계의 구매 스키마입니다.

![](../assets/schema10.png)

>[!NOTE]
>
>의 스키마 관계에 대해 자세히 알아보기 [Experience Platform 설명서](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=en).

그런 다음 Journey Orchestration에서 연결된 테이블의 모든 필드를 활용할 수 있습니다.

* 단일 이벤트 구성 시 [자세한 내용](../event/experience-event-schema.md#unitary_event_configuration)
* 여정에서 조건을 사용할 때, [자세한 내용](../event/experience-event-schema.md#journey_conditions_using_event_context)
* 사용자 지정 작업 개인화에서, [자세한 내용](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 단일 이벤트 구성{#unitary_event_configuration}

연결된 스키마 필드는 단일 이벤트 구성에서 사용할 수 있습니다.

* 이벤트 구성 화면에서 이벤트 스키마 필드를 검색할 때.
* 시스템 생성 이벤트에 대한 조건을 정의할 때.

![](../assets/schema11.png)

연결된 필드는 사용할 수 없습니다.

* 이벤트 키 공식
* 이벤트 id 조건(규칙 기반 이벤트)

단일 이벤트를 구성하는 방법에 대해 알아보려면 다음을 참조하십시오 [페이지](../event/about-creating.md).

### 이벤트 컨텍스트를 사용한 여정 조건{#journey_conditions_using_event_context}

조건 작성을 위한 여정에 사용된 이벤트에 연결된 조회 테이블의 데이터를 사용할 수 있습니다(표현식 편집기).

여정에 조건을 추가하고 표현식을 편집하고 표현식 편집기에서 이벤트 노드를 펼칩니다.

![](../assets/schema12.png)

여정 조건을 정의하는 방법에 대해 알아보려면 다음을 참조하십시오 [페이지](../building-journeys/condition-activity.md).

### 여정 이벤트 컨텍스트를 사용한 작업 개인화{#custom_action_personalization_with_journey_event_context}

연결된 필드는 여정 작업 활동의 작업 매개 변수를 구성할 때 사용할 수 있습니다.

![](../assets/schema13.png)

사용자 지정 작업을 사용하는 방법에 대해 알아보려면 다음을 참조하십시오 [페이지](../building-journeys/using-custom-actions.md).

