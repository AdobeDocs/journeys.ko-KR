---
product: adobe campaign
title: 이벤트 활동 정보
description: 이벤트 활동에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# 이벤트 활동 정보 {#concept_rws_1rt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 여기를](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"} 클릭하십시오[.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._


기술 사용자(이 페이지](../event/about-events.md) 참조[)가 구성한 이벤트는 모두 화면 왼쪽에 있는 팔레트의 첫 번째 범주에 표시됩니다.

![](../assets/journey43.png)

항상 이벤트 활동을 드래그 앤 드롭하여 여정을 시작하십시오. 두 번 클릭할 수도 있습니다.

![](../assets/journey44.png)

캔버스에서 이벤트 활동을 클릭하면 활동 구성 창이 표시됩니다. 기본적으로 동일한 이벤트를 여러 번 사용하면 캔버스의 이벤트 이름에 증가된 숫자가 추가됩니다. 또한 필드를 사용하여 **[!UICONTROL Label]** 캔버스의 활동 아래에 표시될 이벤트 이름에 접미사를 추가할 수 있습니다. 이는 특히 동일한 이벤트를 여러 번 사용하는 경우 캔버스에서 이벤트를 식별하는 데 유용합니다. 또한 오류 발생 시 디버깅이 더 쉬워지고 보고서를 더 쉽게 읽을 수 있습니다.

![](../assets/journey33.png)

## 특정 시간 동안 이벤트 듣기 {#listening}

여정에 있는 이벤트 활동은 무기한 이벤트를 수신합니다. 특정 시간 동안에만 이벤트를 수신하려면 이벤트에 대한 시간 제한을 구성해야 합니다.

그러면 여정은 시간 초과에 지정된 시간 동안 이벤트를 수신합니다. 해당 기간 동안 이벤트가 수신되면 그 사람은 이벤트 경로로 흐릅니다. 그렇지 않은 경우 고객은 시간 제한 경로(정의된 경우)로 이동하거나 해당 여정을 계속합니다. 시간 제한 경로가 정의되지 않은 경우 시간 제한 설정은 대기 활동으로 작동하여 프로필이 일정 시간 동안 대기하도록 하며, 해당 대기가 끝나기 전에 이벤트가 발생하면 중지될 수 있습니다. 시간 초과 후 해당 여정에서 프로필을 제외하려면 시간 초과 경로를 설정해야 합니다.

이벤트에 대한 시간 제한을 구성하려면 다음 단계를 팔로우하십시오.

1. 이벤트 속성에서 옵션을 활성화합니다 **[!UICONTROL Enable the event timeout]** .

1. 여정에서 이벤트를 기다리는 시간을 지정합니다.

1. 지정된 제한시간 내에 이벤트가 수신되지 않을 때 개인을 제한시간 경로로 보내려면 이 옵션을 활성화하십시오 **[!UICONTROL Set the timeout path]** . 이 옵션을 활성화하지 않으면 시간 초과에 도달하면 개인에 대해 여정이 계속됩니다.

   ![](../assets/event-timeout.png)

이 예에서 여정은 고객에게 첫 번째 환영 푸시를 보냅니다. 이어 다음날 고객이 식당에 입장할 경우에만 식사 할인 푸시를 발송한다. 따라서 레스토랑 이벤트를 1일 제한 시간으로 구성했습니다.

* 환영 푸시 후 1일 이내에 레스토랑 이벤트가 수신되면 식사 할인 푸시 활동이 전송됩니다.
* 다음 날 이내에 레스토랑 이벤트가 수신되지 않으면 해당 사용자가 시간 초과 경로를 통해 이동합니다.

활동 뒤에 **[!UICONTROL Wait]** 배치된 여러 이벤트에 대한 시간 제한을 구성하려면 이러한 이벤트 중 하나에 대해서만 시간 제한을 구성해야 합니다.

시간 초과는 활동 뒤에 **[!UICONTROL Wait]** 배치된 모든 이벤트에 적용됩니다. 지정된 시간 초과 전에 이벤트가 수신되지 않으면 개인은 하나의 단일 시간 초과 경로로 이동하거나 해당 시간 초과 설정이 정의된 활동을 종료하는 분기 경로를 통해 해당 여정을 계속합니다.

![](../assets/event-timeout-group.png)
