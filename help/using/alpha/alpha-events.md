---
title: 규칙 기반 이벤트
description: 규칙 기반 이벤트에 대해 자세히 알아보십시오.
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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%

---


# 규칙 기반 이벤트{#simplified-events}

경험 이벤트를 설정하는 방법을 간소화했습니다. eventID를 사용할 필요가 없는 새 메서드가 도입되었습니다. 이제 Journey Orchestration에서 이벤트를 설정할 때 규칙 기반 이벤트를 정의할 수 있습니다.

이 새로운 유형의 이벤트는 eventID를 생성하지 않습니다. 간단한 표현식 편집기를 사용하면 시스템에서 사용자의 여정을 트리거할 관련 이벤트를 식별하는 데 사용할 규칙을 간단하게 정의할 수 있습니다. 이 규칙은 이벤트 페이로드에서 사용할 수 있는 필드(예: 프로필의 위치 또는 프로필 장바구니에 추가된 항목 수)를 기반으로 할 수 있습니다.

이 새 방법은 대부분 사용자에게 투명하게 표시됩니다. 이벤트 정의 화면의 새 필드만 변경됩니다.

1. 왼쪽 메뉴에서 **관리** 아이콘을 클릭한 다음 **이벤트를 클릭합니다**. 그러면 이벤트 목록이 표시됩니다.

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. 그러면 화면 오른쪽에 이벤트 구성 창이 열립니다.

   ![](../assets/alpha-event2.png)

1. 이벤트 이름을 입력합니다. 설명을 추가할 수도 있습니다.

   ![](../assets/alpha-event3.png)

1. 새 **이벤트 ID 유형** 필드에서 규칙 기반 **을 선택합니다**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >시스템 **생성** 유형은 eventID가 필요한 기존 메서드입니다. 이 [섹션을 참조하십시오](../event/about-events.md).

1. 스키마 **및 페이로드** 필드를 **정의합니다**. 이 [섹션을 참조하십시오](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >시스템 생성 유형 **을**&#x200B;선택하면 eventID 유형 mixin이 있는 스키마만 사용할 수 있습니다. 규칙 기반 **유형을** 선택하면 모든 경험 이벤트 스키마를 사용할 수 있습니다.

1. [ **이벤트 ID 조건** ] 필드 내부를 클릭합니다. 간단한 표현식 편집기를 사용하여, 시스템이 여정을 트리거할 이벤트를 식별하는 데 사용할 조건을 정의합니다.

   ![](../assets/alpha-event6.png)

   우리의 예에서, 우리는 프로필의 도시를 근거로 조건들을 작성했습니다. 즉, 시스템이 이 조건(**City** 필드 및 **Paris** 값)과 일치하는 이벤트를 받을 때마다 Journey Orchestration에 전달됩니다.

1. 네임스페이스 **와** 키를 **정의합니다**. 네임스페이스 [선택](../event/selecting-the-namespace.md) 및 이벤트 키 [정의를 참조하십시오](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

이벤트 구성 및 경로 생성에 대한 다른 단계는 변경되지 않습니다.

이제 이벤트가 구성되고 다른 이벤트와 마찬가지로 여정으로 이동할 준비가 되었습니다. 규칙과 일치하는 이벤트가 시스템에 전송될 때마다 Journey Orchestration으로 전달되어 사용자의 여행을 트리거합니다.

