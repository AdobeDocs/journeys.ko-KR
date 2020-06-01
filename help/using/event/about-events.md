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
translation-type: ht
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: ht
source-wordcount: '735'
ht-degree: 100%

---


# 이벤트 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="이벤트"
>abstract="특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. Journey Orchestration는 경로에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다."

특정 사용자에게 연결되는 이벤트는 해당 사용자의 제품 구매, 상점 방문, 웹 사이트 종료와 같은 행동과 관련된 항목일 수도 있고 해당 사용자와 관련하여 발생하는 상황일 수도 있습니다. 사용자가 충성도 점수 10,000점을 달성하는 등의 경우를 예로 들 수 있습니다. Journey Orchestration는 경로에서 이러한 이벤트를 수신하여 최적의 다음 작업을 조율합니다.

Journey Orchestration은 이벤트를 수신하도록 설계되어 있으므로 이 구성은 **필수** 작업이며, 항상 **기술 사용자**&#x200B;가 수행해야 합니다.

이벤트 구성에서는 Journey Orchestration이 이벤트로 수신할 정보를 정의할 수 있습니다. 경로의 각 단계에서 여러 이벤트를 사용할 수 있으며, 여러 경로에서 같은 이벤트를 사용할 수도 있습니다.

초안 또는 라이브 경로에서 사용되는 이벤트를 편집할 때는 이름, 설명 또는 페이로드 필드만 변경할 수 있습니다. 경로 손상 방지를 위해 초안 또는 라이브 경로 편집은 엄격히 제한됩니다.

## 일반 원칙 {#section_r1f_xqt_pgb}

POST API 호출인 이벤트는 스트리밍 수집 API를 통해 Adobe Experience Cloud 데이터 플랫폼으로 전송됩니다. 트랜잭션 메시징 API를 통해 전송되는 이벤트의 URL 대상은 &quot;인렛&quot;입니다. 이벤트의 페이로드는 XDM 형식을 따릅니다.

페이로드의 헤더에는 스트리밍 수집 API의 작동에 필요한 정보가, 이벤트 ID와 페이로드 본분의 일부분에는 Journey Orchestration의 작동에 필요한 정보가 포함되어 있습니다. 그리고 본문에는 경로에 사용할 정보(예: 쇼핑을 중단한 카트의 금액)가 포함되어 있습니다. 스트리밍 수집에는 인증/미인증의 두 가지 모드가 있습니다. 스트리밍 수집 API에 대한 자세한 내용은 [이 링크](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/api/getting-started.html)를 참조하십시오.

스트리밍 수집 API를 통과하여 대상에 도착한 이벤트는 내부 서비스(파이프라인)와 데이터 플랫폼으로 이동합니다. 이벤트 스키마에 실시간 고객 프로필 서비스 플래그가 설정되어 있고, 역시 실시간 고객 프로필 태그가 설정된 데이터 세트 ID도 포함되어 있으면 이벤트는 실시간 고객 프로필 서비스로 이동합니다.

파이프라인은 Journey Orchestration 이벤트 ID(Journey Orchestration에서 제공하며 이벤트 페이로드에 포함됨)가 들어 있는 페이로드가 포함된 이벤트를 필터링합니다. 아래 이벤트 만들기 프로세스를 참조하십시오. Journey Orchestration에서 이러한 이벤트를 수신하면 해당하는 경로가 트리거됩니다.

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
1. 스키마 및 페이로드 필드를 정의합니다. 이 단계에서 Journey Orchestration이 수신하도록 할 이벤트 정보(대개 페이로드)를 선택합니다. 그러면 이 정보를 경로에 사용할 수 있습니다. [](../event/defining-the-payload-fields.md)를 참조하십시오.
1. 이 이벤트를 사용하는 경로 수가 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 아이콘을 클릭하여 이 이벤트를 사용하는 경로 목록을 표시할 수 있습니다.
1. 네임스페이스를 추가합니다. 이 단계는 원하는 경우에만 수행하면 되지만, 네임스페이스를 추가하면 실시간 고객 프로필 서비스에 저장된 정보를 활용할 수 있습니다. 이 정보에 따라 이벤트의 키 유형이 정의됩니다. [](../event/selecting-the-namespace.md)를 참조하십시오.
1. 키를 정의합니다. 페이로드 필드에서 필드를 선택하거나 공식을 정의하여 이벤트와 연관된 사용자를 지정합니다. 이 키는 네임스페이스를 선택하면 자동으로 설정되지만 편집할 수 있습니다. 네임스페이스에 해당하는 키는 Journey Orchestration에서 자동으로 선택됩니다. 예를 들어 이메일 네임스페이스를 선택하면 이메일 키가 선택됩니다. [](../event/defining-the-event-key.md)를 참조하십시오.
1. 원하는 경우 조건을 추가합니다. 조건을 추가하면 시스템은 조건을 충족하는 이벤트만 처리합니다. 조건은 이벤트에 포함된 정보를 기준으로만 추가할 수 있습니다. [](../event/adding-a-condition.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을 클릭합니다.

   ![](../assets/journey7.png)

   이제 이벤트가 구성되었으며 경로에 추가할 수 있는 상태가 되었습니다. 이벤트를 수신하려면 추가 구성 단계를 수행해야 합니다. [](../event/additional-steps-to-send-events-to-journey-orchestration.md)를 참조하십시오.
