---
product: adobe campaign
title: 이벤트 만들기
description: 이벤트를 만드는 방법을 알아봅니다
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 78c758c75825c0f85788190c4526fa5c743c6673
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 63%

---

# 새 이벤트 만들기 {#section_tbk_5qt_pgb}

새 이벤트를 구성하는 주요 단계는 다음과 같습니다.

1. 상단 메뉴에서 **[!UICONTROL Events]** 탭을 클릭합니다. 그러면 이벤트 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [이 페이지](../about/user-interface.md)를 참조하십시오.

   ![](../assets/journey5.png)

1. 새 이벤트를 만들려면 **[!UICONTROL Add]**&#x200B;를 클릭합니다. 그러면 화면 오른쪽에 이벤트 구성 창이 열립니다. 이벤트의 이름을 입력합니다. 설명을 추가할 수도 있습니다.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. **[!UICONTROL Event ID type]** 필드에서 사용할 이벤트 유형을 선택합니다.

   ![](../assets/journey6bis.png)

   * **규칙 기반** 이벤트: 이 유형의 이벤트는 eventID를 생성하지 않습니다. **이벤트 ID 조건** 필드에서 여정을 트리거할 관련 이벤트를 식별하는 데 사용할 규칙을 간단히 정의합니다. 이 규칙은 프로필의 위치 또는 프로필의 장바구니에 추가한 항목 수와 같은 이벤트 페이로드에서 사용할 수 있는 필드를 기반으로 할 수 있습니다.

   * **시스템** 생성 장치:이 유형에는 eventID가 필요합니다. 이 eventID 필드는 이벤트를 만들 때 자동으로 생성되어 페이로드 미리 보기에 추가됩니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 전달해야 합니다. [이 섹션](../event/previewing-the-payload.md)을 참조하십시오.
   >[!NOTE]
   >
   >[이 섹션](../event/about-events.md)의 이벤트 유형에 대해 자세히 알아보십시오.
1. 이 이벤트를 사용하는 경로 수가 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 아이콘을 클릭하여 이 이벤트를 사용하는 경로 목록을 표시할 수 있습니다.
1. 스키마 및 페이로드 필드를 정의합니다. 이 단계에서 [!DNL Journey Orchestration]이 수신하도록 할 이벤트 정보(대개 페이로드)를 선택합니다. 그러면 이 정보를 경로에 사용할 수 있습니다. [이 페이지](../event/defining-the-payload-fields.md)를 참조하십시오.
   >[!NOTE]
   >
   >**[!UICONTROL System Generated]** 유형을 선택하면 eventID 유형 mixin이 있는 스키마만 사용할 수 있습니다. **[!UICONTROL Rule Based]** 유형을 선택하면 모든 Experience Event 스키마를 사용할 수 있습니다.

1. 규칙 기반 이벤트의 경우 **[!UICONTROL Event ID condition]** 필드 내부를 클릭합니다. 단순 표현식 편집기를 사용하여 시스템에서 여정을 트리거할 이벤트를 식별하는 데 사용할 조건을 정의합니다.
   ![](../assets/alpha-event6.png)

   이 예제에서는 프로필의 도시를 기반으로 조건을 작성했습니다. 즉, 시스템에서 이 조건(**[!UICONTROL City]** 필드 및 **[!UICONTROL Paris]** 값)과 일치하는 이벤트를 수신할 때마다 Journey Orchestration에 전달됩니다.

   >[!NOTE]
   >
   >**[!UICONTROL Event ID condition]**&#x200B;을(를) 정의할 때는 고급 표현식 편집기를 사용할 수 없습니다.

1. 네임스페이스를 추가합니다. 이 단계는 원하는 경우에만 수행하면 되지만, 네임스페이스를 추가하면 실시간 고객 프로필 서비스에 저장된 정보를 활용할 수 있습니다. 이 정보에 따라 이벤트의 키 유형이 정의됩니다. [이 페이지](../event/selecting-the-namespace.md)를 참조하십시오.
1. 키를 정의합니다. 페이로드 필드에서 필드를 선택하거나 공식을 정의하여 이벤트와 연관된 사용자를 지정합니다. 이 키는 네임스페이스를 선택하면 자동으로 설정되지만 편집할 수 있습니다. 네임스페이스에 해당하는 키는 [!DNL Journey Orchestration]에서 자동으로 선택됩니다. 예를 들어 이메일 네임스페이스를 선택하면 이메일 키가 선택됩니다. [이 페이지](../event/defining-the-event-key.md)를 참조하십시오.
1. 시스템 생성 이벤트의 경우 조건을 추가할 수 있습니다. 조건을 추가합니다. 조건을 추가하면 시스템은 조건을 충족하는 이벤트만 처리합니다. 조건은 이벤트에 포함된 정보를 기준으로만 추가할 수 있습니다. [이 페이지](../event/adding-a-condition.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을 클릭합니다.

   ![](../assets/journey7.png)

   이제 이벤트가 구성되었으며 경로에 추가할 수 있는 상태가 되었습니다. 이벤트를 수신하려면 추가 구성 단계를 수행해야 합니다. [이 페이지](../event/additional-steps-to-send-events-to-journey-orchestration.md)를 참조하십시오.
