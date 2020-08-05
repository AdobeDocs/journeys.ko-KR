---
title: 여정 구축
description: 고객 여정 구축 방법 살펴보기
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 10%

---



# 여정 만들기 {#concept_gq5_sqt_52b}

This step is performed by the **business user**. 여기에서 여행을 만들어 보십시오. 다양한 이벤트, 오케스트레이션 및 작업 활동을 조합하여 여러 단계로 구성된 크로스 채널 시나리오를 작성할 수 있습니다.

경로 인터페이스를 사용하면 팔레트의 활동을 캔버스로 손쉽게 드래그하여 놓을 수 있습니다. 활동을 두 번 클릭하여 다음 단계에서 캔버스에 추가할 수도 있습니다. 각 활동에는 특정 역할과 위치가 있습니다. 활동은 순차적인 것입니다. 활동이 끝나면 흐름이 계속되어 다음 활동을 처리하는 등 다양한 작업을 수행합니다.

여정당 하나의 네임스페이스만 허용됩니다. 첫 번째 이벤트를 삭제하면 네임스페이스가 다른 이벤트가 회색으로 표시됩니다. 첫 번째 이벤트에 네임스페이스가 없으면 네임스페이스가 있는 모든 이벤트가 회색으로 표시됩니다. [](../event/selecting-the-namespace.md)을 참조하십시오. 또한, 여정에 네임스페이스가 없는 이벤트가 있는 경우 Adobe Experience Platform 필드 그룹이 회색으로 표시됩니다. 마지막으로 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다.

## Quick start {#creating_journey}

여정을 만들고 게시하는 주요 단계는 다음과 같습니다.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭을 클릭합니다.

   여정 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [](../building-journeys/using-the-journey-designer.md)를 참조하십시오.

   ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 경로 속성을 편집합니다. [](../building-journeys/changing-properties.md)을 참조하십시오.

   ![](../assets/journey32.png)

1. 먼저 팔레트에서 캔버스로 이벤트 활동을 드래그하여 놓습니다. 활동을 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journey33.png)

1. 다른 활동을 드래그하여 놓고 구성합니다. 참조 [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) 및 [](../building-journeys/about-action-activities.md)을 참조하십시오.

   ![](../assets/journey34.png)

1. 고객 여정은 자동으로 저장됩니다. 고객 여정 테스트 및 게시 및 [](../building-journeys/testing-the-journey.md) 을 참조하십시오 [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## 여정 종료 {#ending_a_journey}

다음 두 가지 방법으로 여행을 마무리할 수 있습니다.

* 그 사람은 경로의 마지막 활동에 도착한다. 이 마지막 활동은 종료 활동이나 다른 활동이 될 수 있습니다. 종료 활동으로 경로를 종료해야 할 의무는 없습니다. [](../building-journeys/end-activity.md)을 참조하십시오.
* 이 사람은 조건 활동(또는 조건이 있는 대기 활동)에 도착하며 조건이 일치하지 않습니다.

다시 입장할 수 있다면 다시 들어갈 수 있다. [](../building-journeys/changing-properties.md)을 참조하십시오.
