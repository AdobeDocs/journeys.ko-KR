---
title: 이벤트 활동 정보
description: 이벤트 활동에 대한 자세한 내용
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# 이벤트 활동 정보 {#concept_rws_1rt_52b}

기술 사용자가 구성한 이벤트(참조 [](../event/about-events.md))는 모두 화면의 왼쪽에 있는 팔레트의 첫 번째 범주에 표시됩니다.

![](../assets/journey43.png)

항상 이벤트 활동을 드래그 앤 드롭하여 이동을 시작합니다. 두 번 클릭할 수도 있습니다.

![](../assets/journey44.png)

캔버스에서 이벤트 활동을 클릭하면 활동 구성 창이 표시됩니다. 기본적으로 동일한 이벤트를 여러 번 사용하면 캔버스의 이벤트 이름에 증분되는 번호가 추가됩니다. 또한 이 **[!UICONTROL Label]** 필드를 사용하여 캔버스의 활동 아래에 표시되는 이벤트 이름에 접미사를 추가할 수 있습니다. 이는 캔버스에서 이벤트를 식별하는 데 유용합니다. 특히 동일한 이벤트를 여러 번 사용하는 경우 유용합니다. 또한 오류 발생 시 보다 쉽게 디버깅할 수 있으며 보고서를 보다 쉽게 읽을 수 있습니다.

![](../assets/journey33.png)

## 고급 사용: 동시에 대기하는 이벤트{#section_vxv_h25_pgb}

**어떻게 특정 시간 동안에만 이벤트를 들을 수 있습니까?**

여정에 배치된 이벤트 활동은 무한정 이벤트를 수신합니다. 특정 시간 동안에만 이벤트를 수신하려면 이벤트 경로와 유사한 대기 활동을 추가해야 합니다. 그러면 대기 활동에 지정된 시간 동안 여정이 이벤트를 수신하게 됩니다. 해당 기간 동안 이벤트가 수신되면 해당 사람은 이벤트 경로로 이동합니다. 그렇지 않으면 고객이 대기 경로로 이동합니다.

예를 들어 고객에게 환영 메시지를 먼저 보냈고 고객이 6시간 내에 해당 식당에 입장하는 경우에만 식사 할인 푸시를 보내려고 합니다. 이를 위해 6시간 대기 활동이 있는 두 번째 경로(레스토랑 이벤트 1과 평행)를 만듭니다. 레스토랑 이벤트가 환영 푸시 후 6시간 이내에 수신되면 식사 할인 푸시 활동이 전송됩니다. 6시간 이내에 받은 레스토랑 이벤트가 없을 경우 사람은 대기 경로로 이동합니다.

![](../assets/journeyuc2_31.png)
