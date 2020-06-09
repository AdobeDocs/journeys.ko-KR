---
title: 이벤트
description: 이벤트 구성 방법 알아보기
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 74%

---


# 이벤트 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="이벤트"
>abstract="특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

This configuration is **mandatory**, as [!DNL Journey Orchestration] is designed to listen to events, and always performed by a **technical user**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. 경로의 각 단계에서 여러 이벤트를 사용할 수 있으며, 여러 경로에서 같은 이벤트를 사용할 수도 있습니다.

초안 또는 라이브 경로에서 사용되는 이벤트를 편집할 때는 이름, 설명 또는 페이로드 필드만 변경할 수 있습니다. 경로 손상 방지를 위해 초안 또는 라이브 경로 편집은 엄격히 제한됩니다.

## 일반 원칙 {#section_r1f_xqt_pgb}

POST API 호출인 이벤트는 스트리밍 수집 API를 통해 Adobe Experience Cloud 데이터 플랫폼으로 전송됩니다. 트랜잭션 메시징 API를 통해 전송되는 이벤트의 URL 대상은 &quot;인렛&quot;입니다. 이벤트의 페이로드는 XDM 형식을 따릅니다.

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). 스트리밍 수집에는 인증/미인증의 두 가지 모드가 있습니다. 스트리밍 수집 API에 대한 자세한 내용은 [이 링크](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/api/getting-started.html)를 참조하십시오.

스트리밍 수집 API를 통과하여 대상에 도착한 이벤트는 내부 서비스(파이프라인)와 데이터 플랫폼으로 이동합니다. 이벤트 스키마에 실시간 고객 프로필 서비스 플래그가 설정되어 있고, 역시 실시간 고객 프로필 태그가 설정된 데이터 세트 ID도 포함되어 있으면 이벤트는 실시간 고객 프로필 서비스로 이동합니다.

The Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.

## 새 이벤트 만들기 {#section_tbk_5qt_pgb}

새 이벤트를 구성하는 주요 단계는 다음과 같습니다.

1. 상단 메뉴에서 **[!UICONTROL Events]** 탭을 클릭합니다. 그러면 이벤트 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [](../about/user-interface.md)를 참조하십시오.

   ![](../assets/journey5.png)

1. 새 이벤트를 만들려면 **[!UICONTROL Add]**&#x200B;를 클릭합니다. 그러면 화면 오른쪽에 이벤트 구성 창이 열립니다.

   ![](../assets/journey6.png)

1. 이벤트의 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. 원하는 경우 이벤트에 설명을 추가합니다.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. 그러면 이 정보를 경로에 사용할 수 있습니다. [](../event/defining-the-payload-fields.md)를 참조하십시오.
1. 이 이벤트를 사용하는 경로 수가 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 아이콘을 클릭하여 이 이벤트를 사용하는 경로 목록을 표시할 수 있습니다.
1. 네임스페이스를 추가합니다. 이 단계는 원하는 경우에만 수행하면 되지만, 네임스페이스를 추가하면 실시간 고객 프로필 서비스에 저장된 정보를 활용할 수 있습니다. 이 정보에 따라 이벤트의 키 유형이 정의됩니다. [](../event/selecting-the-namespace.md)를 참조하십시오.
1. 키를 정의합니다. 페이로드 필드에서 필드를 선택하거나 공식을 정의하여 이벤트와 연관된 사용자를 지정합니다. 이 키는 네임스페이스를 선택하면 자동으로 설정되지만 편집할 수 있습니다. Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). [](../event/defining-the-event-key.md)를 참조하십시오.
1. 원하는 경우 조건을 추가합니다. 조건을 추가하면 시스템은 조건을 충족하는 이벤트만 처리합니다. 조건은 이벤트에 포함된 정보를 기준으로만 추가할 수 있습니다. [](../event/adding-a-condition.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을 클릭합니다.

   ![](../assets/journey7.png)

   이제 이벤트가 구성되었으며 경로에 추가할 수 있는 상태가 되었습니다. 이벤트를 수신하려면 추가 구성 단계를 수행해야 합니다. [](../event/additional-steps-to-send-events-to-journey-orchestration.md)를 참조하십시오.
