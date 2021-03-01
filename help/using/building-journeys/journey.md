---
product: adobe campaign
solution: Journey Orchestration
title: 여정 구축
description: 비즈니스 사용자는 이벤트, 오케스트레이션 및 작업 활동을 통합하여 여정을 구축하는 방법을 살펴봅니다.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---


# 여정 만들기 {#concept_gq5_sqt_52b}

이 단계는 **비즈니스 사용자**&#x200B;에 의해 수행됩니다. 여기에서 여정을 만듭니다. 다양한 이벤트, 오케스트레이션 및 작업 활동을 조합하여 여러 단계로 구성된 크로스 채널 시나리오를 작성할 수 있습니다.

여정 인터페이스를 사용하면 팔레트에서 캔버스로 활동을 쉽게 드래그하여 놓을 수 있습니다. 활동을 두 번 클릭하여 다음 단계에서 캔버스에 추가할 수도 있습니다. 각 활동에는 특정 역할과 위치가 있습니다. 활동은 순차적인 것입니다. 활동이 끝나면 흐름이 계속 진행되어 다음 활동을 처리하는 등의 작업을 수행합니다.

여정당 하나의 네임스페이스만 허용됩니다. 첫 번째 이벤트를 놓으면 네임스페이스가 다른 이벤트가 회색으로 표시됩니다. 첫 번째 이벤트에 네임스페이스가 없으면 네임스페이스가 있는 모든 이벤트가 회색으로 표시됩니다. [이 페이지](../event/selecting-the-namespace.md)를 참조하십시오. 또한 여정에 네임스페이스가 없는 이벤트가 있는 경우 Adobe Experience Platform 필드 그룹이 회색으로 표시됩니다. 마지막으로 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다.

## 빠른 시작 {#creating_journey}

여정을 만들고 게시하는 주요 단계는 다음과 같습니다.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭을 클릭합니다.

   여정 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [이 페이지](../building-journeys/using-the-journey-designer.md)를 참조하십시오.

   ![](../assets/journey30.png)

1. **[!UICONTROL Create]**&#x200B;을 클릭하여 새 여정을 만듭니다.

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 여정의 속성을 편집합니다. [이 페이지](../building-journeys/changing-properties.md)를 참조하십시오.

   ![](../assets/journey32.png)

1. 팔레트의 이벤트 활동을 캔버스로 드래그하여 놓는 방식으로 시작합니다. 활동을 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journey33.png)

1. 다른 활동을 드래그하여 놓고 구성합니다. [이벤트 활동](../building-journeys/event-activities.md), [오케스트레이션 활동 정보](../building-journeys/about-orchestration-activities.md) 및 [작업 활동 정보](../building-journeys/about-action-activities.md) 페이지를 참조하십시오.

   ![](../assets/journey34.png)

1. 여정이 자동으로 저장됩니다. 여정을 테스트하고 게시합니다. [여정 테스트](../building-journeys/testing-the-journey.md) 및 [여정 게시](../building-journeys/publishing-the-journey.md)를 참조하십시오.

   ![](../assets/journey36.png)

## 여정 {#ending_a_journey} 종료

두 가지 방법으로 여정을 종료할 수 있습니다.

* 사람은 경로의 마지막 활동에 도착한다. 이 마지막 활동은 종료 활동이나 다른 활동일 수 있습니다. 최종 활동으로 경로를 종료할 의무는 없습니다. [이 페이지](../building-journeys/end-activity.md)를 참조하십시오.
* 이 사람은 조건 활동(또는 조건이 있는 대기 활동)에 도착하며 조건이 일치하지 않습니다.

그런 다음 다시 입장할 수 있는 경우 여정에 다시 입장할 수 있습니다. [이 페이지](../building-journeys/changing-properties.md)를 참조하십시오.
