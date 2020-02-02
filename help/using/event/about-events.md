---
title: 이벤트 정보
description: 이벤트 구성 방법 학습
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
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# 이벤트 정보 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_events&quot;
>title=&quot;이벤트 정보&quot;
>abstract=&quot;이벤트는 사람에 연결됩니다. 이것은 개인의 행동과 관련이 있습니다(예: 제품을 구입하거나 가게를 방문하거나 웹 사이트를 나가는 사람 등). 또는 사람과 연결된 어떤 것(예: 한 사람이 10,000개의 충성도 포인트에 도달함) 이는 여정 오케스트레이션이 최상의 다음 동작을 구성할 수 있도록 귀담아 들을 것입니다.&quot;

이벤트는 개인에게 연결됩니다. 이것은 개인의 행동과 관련이 있습니다(예: 제품을 구입하거나 가게를 방문하거나 웹 사이트를 나가는 사람 등). 또는 사람과 연결된 어떤 것(예: 한 사람이 10,000개의 충성도 포인트에 도달함) 이는 고객 여정 통합 관리가 향후 최고의 동작을 구성할 수 있도록 귀기울일 것입니다.

고객 여정 **오케스트레이션은 이벤트를 수신하도록 설계되고**&#x200B;기술 사용자가 **항상 수행하므로 이 구성은**&#x200B;필수입니다.

이벤트 구성을 사용하여 경로 오케스트레이션이 이벤트로 수신할 정보를 정의할 수 있습니다. 여러 이벤트(경로의 다른 단계)를 사용할 수 있으며 여러 여정은 동일한 이벤트를 사용할 수 있습니다.

초안 또는 라이브 여정에서 사용되는 이벤트를 편집하는 경우 이름, 설명 또는 페이로드 필드만 변경할 수 있습니다. 우리는 여행을 떠나는 것을 막기 위해 초본이나 생선의 여행을 엄격하게 제한한다.

## 일반 원칙 {#section_r1f_xqt_pgb}

이벤트는 POST API 호출입니다. 이벤트는 스트리밍 통합 API를 통해 Adobe Experience Cloud 데이터 플랫폼으로 전송됩니다. 트랜잭션 메시징 API를 통해 전송된 이벤트의 URL 대상을 &quot;유입&quot;이라고 합니다. XDM 형식 다음에 이벤트 페이로드가 발생합니다.

페이로드에는 스트리밍 통합 API가 작동하기 위해(헤더에서) 필요한 정보와 경로 오케스트레이션이 작동하는 데 필요한 정보(이벤트 ID, 페이로드 본문의 일부) 및 여정(예를 들어, 본문)에서 사용할 정보가 포함되어 있습니다. 스트리밍 통합, 인증 및 인증되지 않은 두 가지 모드가 있습니다. 스트리밍 통합 API에 대한 자세한 내용은 [이 링크를](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)참조하십시오.

Streaming Ingestion API를 통해 도착한 후 이벤트는 Pipeline이라는 내부 서비스로 이동한 다음 데이터 플랫폼에서 진행됩니다. 이벤트 스키마에 실시간 고객 프로필 서비스 플래그가 활성화되어 있고 실시간 고객 프로필 플래그도 있는 데이터 세트 ID가 있는 경우 실시간 고객 프로필 서비스로 전송됩니다.

파이프라인은 경로 지정 오케스트레이션에서 제공하고 이벤트 페이로드에 포함된 경로 관리 이벤트 ID가 포함된 페이로드가 있는 이벤트를 필터링합니다(아래 이벤트 생성 프로세스 참조). 이러한 이벤트는 고객 여정 오케스트레이션에서 수신되며 해당 여정이 트리거됩니다.

## 새 이벤트 만들기 {#section_tbk_5qt_pgb}

다음은 새 이벤트를 구성하는 기본 단계입니다.

1. 상단 메뉴에서 **[!UICONTROL Events]**탭을 클릭합니다. 이벤트 목록이 표시됩니다. 인터페이스에[](../about/user-interface.md)대한 자세한 내용은 을 참조하십시오.

   ![](../assets/journey5.png)

1. 아이콘을 **[!UICONTROL Add]**클릭하여 새 이벤트를 만듭니다. 화면 오른쪽에 이벤트 구성 창이 열립니다.

   ![](../assets/journey6.png)

1. 이벤트의 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 마십시오. 30자를 초과하여 사용하지 마십시오.

1. 이벤트에 설명을 추가합니다. 이 단계는 선택 사항입니다.
1. 스키마 및 페이로드 필드를 정의합니다.이 페이지에서 여정 오케스트레이션에서 수신할 이벤트 정보(일반적으로 페이로드라고 함)를 선택합니다. 그러면 이 정보를 여정에서 사용할 수 있습니다. 을 [](../event/defining-the-payload-fields.md)참조하십시오.
1. 이 이벤트를 사용하는 여정 수가 **[!UICONTROL Used in]**필드에 표시됩니다. 이**[!UICONTROL View journeys]** 아이콘을 클릭하여 이 이벤트를 사용하는 여행 목록을 표시할 수 있습니다.
1. 네임스페이스를 추가합니다. 이 단계는 선택 사항이지만 네임스페이스를 추가하면 실시간 고객 프로필 서비스에 저장된 정보를 활용할 수 있습니다. 이벤트가 가지는 키 유형을 정의합니다. 을 [](../event/selecting-the-namespace.md)참조하십시오.
1. 키 정의:페이로드 필드에서 필드를 선택하거나 공식을 정의하여 이벤트와 연관된 개인을 식별합니다. 네임스페이스를 선택하면 이 키가 자동으로 설정되지만 편집할 수는 있습니다. 실제로 여정 오케스트레이션은 네임스페이스에 해당하는 키를 선택합니다(예: 이메일 네임스페이스를 선택하면 이메일 키가 선택됩니다). 을 [](../event/defining-the-event-key.md)참조하십시오.
1. 조건을 추가합니다. 이 단계는 선택 사항입니다. 따라서 시스템은 조건을 충족하는 이벤트만 처리할 수 있습니다. 조건은 이벤트에 포함된 정보만 기반으로 할 수 있습니다. 을 [](../event/adding-a-condition.md)참조하십시오.
1. 클릭 **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   이제 이벤트가 구성되고 여정으로 이동할 준비가 되었습니다. 이벤트를 수신하려면 추가 구성 단계가 필요합니다. 을 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)참조하십시오.
