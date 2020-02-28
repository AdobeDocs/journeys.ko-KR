---
title: 고객 여정 구축 정보
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
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec

---



# 고객 여정 만들기 {#concept_gq5_sqt_52b}

이 단계는 **비즈니스 사용자가**&#x200B;수행합니다. 여기에서 여행을 만들 수 있습니다. 다양한 이벤트, 통합 운영 및 작업 활동을 결합하여 여러 단계로 구성된 크로스채널 시나리오를 구축할 수 있습니다.

여정 인터페이스를 사용하면 팔레트의 활동을 캔버스로 손쉽게 드래그하여 놓을 수 있습니다. 활동을 두 번 클릭하여 다음 단계에서 캔버스에 추가할 수도 있습니다. 각 활동에는 특정 역할과 위치가 있습니다. 활동은 순차적 순서를 따릅니다. 활동이 완료되면 흐름이 계속되어 다음 활동을 처리합니다.

여정당 하나의 네임스페이스만 허용됩니다. 첫 번째 이벤트를 삭제하면 네임스페이스가 다른 이벤트가 회색으로 표시됩니다. 첫 번째 이벤트에 네임스페이스가 없으면 네임스페이스가 있는 모든 이벤트가 회색으로 표시됩니다. 을 [](../event/selecting-the-namespace.md)참조하십시오. 또한 여정에서 네임스페이스 없는 이벤트가 있는 경우 경험 플랫폼 필드 그룹이 회색으로 표시됩니다. 마지막으로, 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다.

## Quick start {#creating_journey}

여정을 만들고 게시하는 주요 단계는 다음과 같습니다.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭을 클릭합니다.

   여행 목록이 표시됩니다. 인터페이스에 [](../building-journeys/using-the-journey-designer.md) 대한 자세한 내용은 을 참조하십시오.

   ![](../assets/journey30.png)

1. 을 **[!UICONTROL Create]** 클릭하여 새 경로를 만듭니다.

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 경로의 속성을 편집합니다. 을 [](../building-journeys/changing-properties.md)참조하십시오.

   ![](../assets/journey32.png)

1. 먼저 팔레트의 이벤트 활동을 캔버스로 드래그하여 놓습니다. 활동을 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journey33.png)

1. 다른 활동을 드래그하여 놓고 구성합니다. 을 [](../building-journeys/event-activities.md)참조하십시오. [](../building-journeys/about-orchestration-activities.md) 및 [](../building-journeys/about-action-activities.md)을 참조하십시오.

   ![](../assets/journey34.png)

1. 고객 여정이 자동으로 저장됩니다. 고객 여정 테스트 및 퍼블리싱 를 [](../building-journeys/testing-the-journey.md) 참조하십시오 [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## 고객 여정 종료 {#ending_a_journey}

다음 두 가지 방법으로 여행을 종료할 수 있습니다.

* 이 사람은 경로의 마지막 활동에 도착합니다. 이 마지막 활동은 종료 활동이나 다른 활동이 될 수 있습니다. 최종 활동으로 경로를 종료해야 할 의무는 없습니다. 을 [](../building-journeys/end-activity.md)참조하십시오.
* 이 사람은 조건 활동(또는 조건이 있는 대기 활동)에 도달하고 조건이 일치하지 않습니다.

그런 다음, 다시 입장할 수 있다면, 그 사람은 그 여행에 다시 들어갈 수 있습니다. 을 [](../building-journeys/changing-properties.md)참조하십시오.
