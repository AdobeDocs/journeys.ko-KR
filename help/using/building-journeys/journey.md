---
product: adobe campaign
title: 여정 구축
description: 비즈니스 사용자는 이벤트, 오케스트레이션 및 작업 활동을 통합하여 여정을 구축하는 방법을 살펴봅니다.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 21%

---

# 여정 만들기 {#concept_gq5_sqt_52b}

이 단계는 **비즈니스 사용자**. 여기에서 여정을 만들 수 있습니다. 다양한 이벤트, 오케스트레이션 및 작업 활동을 조합하여 여러 단계로 구성된 크로스 채널 시나리오를 작성할 수 있습니다.

여정 인터페이스를 통해 팔레트에서 캔버스로 활동을 쉽게 드래그 앤 드롭할 수 있습니다. 활동을 더블 클릭하여 사용 가능한 다음 단계에서 캔버스에 추가할 수도 있습니다. 각 활동에는 프로세스에서 특정 역할과 위치가 있습니다. 활동의 순서가 지정됩니다. 활동이 완료되면, 플로우는 계속되고 다음 활동을 처리하는 등의 작업을 수행합니다.

네임스페이스는 여정 당 하나만 허용됩니다. 첫 번째 이벤트를 드롭하면 네임스페이스가 다른 이벤트가 회색으로 표시됩니다. 첫 번째 이벤트에 네임스페이스가 없으면 네임스페이스가 있는 모든 이벤트가 회색으로 표시됩니다. [이 페이지](../event/selecting-the-namespace.md)를 참조하십시오. 또한 여정에 네임스페이스가 없는 이벤트가 있는 경우 Adobe Experience Platform 필드 그룹이 회색으로 표시됩니다. 마지막으로, 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다.

새 여정을 시작할 때 첫 번째 단계로 캔버스에 놓을 수 없는 요소는 숨겨집니다. 이는 모든 작업, 조건 활동, 대기 및 반응과 관련되어 있습니다.

## 빠른 시작 {#creating_journey}

다음은 여정을 만들고 게시하는 주요 단계입니다.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭을 클릭합니다.

   여정 목록이 표시됩니다. 을(를) 참조하십시오 [이 페이지](../building-journeys/using-the-journey-designer.md) 를 참조하십시오.

   ![](../assets/journey30.png)

1. 클릭 **[!UICONTROL Create]** 새 여정 만들기

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 여정의 속성을 편집합니다. [이 페이지](../building-journeys/changing-properties.md)를 참조하십시오.

   ![](../assets/journey32.png)

1. 먼저 팔레트에서 캔버스로 이벤트 활동을 끌어다 놓습니다. 활동을 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journey33.png)

1. 다른 활동을 끌어다 놓고 구성합니다. 페이지를 참조하십시오 [이벤트 활동](../building-journeys/event-activities.md), [오케스트레이션 활동](../building-journeys/about-orchestration-activities.md) 및 [작업 활동 기본 정보](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. 여정이 자동으로 저장됩니다. 여정을 테스트하고 게시합니다. 다음을 참조하십시오 [여정 테스트](../building-journeys/testing-the-journey.md) 및 [여정 게시](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## 여정 종료 {#ending_a_journey}

여정은 다음 두 가지 이유로 개인에게 종료될 수 있습니다.

* 사용자가 경로의 마지막 활동에 도달합니다. 이 마지막 활동은 종료 활동이거나 다른 활동일 수 있습니다. 종료 활동으로 경로를 종료해야 하는 의무는 없습니다. [이 페이지](../building-journeys/end-activity.md)를 참조하십시오.
* 환자는 조건 활동(또는 조건이 있는 대기 활동)에 도달하며 조건과 일치하지 않습니다.

그런 다음 재입장이 허용되는 경우 여정에 다시 입장할 수 있습니다. [이 페이지](../building-journeys/changing-properties.md)를 참조하십시오.

다음 이유로 인해 여정이 닫힐 수 있습니다.

* 여정은 를 통해 수동으로 닫힙니다. **[!UICONTROL Close to new entrances]** 단추를 클릭합니다.
* 여정의 종료 날짜에 도달했습니다.

여정이 닫히면 (위의 경우) 상태가 됩니다 **[!UICONTROL Closed]**. 여정은 새로운 개인이 여정에 들어오도록 하는 것을 중단합니다. 이미 여정에 있는 사람은 여정을 정상적으로 완료합니다. 기본 전역 시간 제한 30일 후에 여정이 로 전환됩니다. **완료됨** 상태. 이 [섹션](../building-journeys/changing-properties.md#entrance)을 참조하세요.

여정 내 모든 개인의 진행을 중단해야 하는 경우에는 중단할 수 있습니다. 여정을 중지하면 여정의 모든 개인이 시간 초과됩니다.

여정을 수동으로 닫거나 중지하는 방법에 대해 알아보려면 다음을 참조하십시오. [섹션](../building-journeys/terminating-a-journey.md).
