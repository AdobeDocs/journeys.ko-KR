---
product: adobe campaign
solution: Journey Orchestration
title: 페이로드 필드 정의
description: 페이로드 필드를 정의하는 방법에 대해 알아봅니다.
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---


# 페이로드 필드 정의 {#concept_yrw_3qt_52b}

페이로드 정의를 사용하면 시스템이 여정의 이벤트에서 받게 될 정보와 해당 이벤트와 연관된 사람을 식별하는 키를 선택할 수 있습니다. 페이로드는 Experience Cloud XDM 필드 정의를 기반으로 합니다. For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/home.html).

1. 목록에서 XDM 스키마를 선택하고 필드 또는 아이콘을 **[!UICONTROL Payload]****[!UICONTROL Edit]** 클릭합니다.

   ![](../assets/journey8.png)

   스키마에 정의된 모든 필드가 표시됩니다. 필드 목록은 스키마마다 다릅니다. 특정 필드를 검색하거나 필터를 사용하여 모든 노드와 필드 또는 선택한 필드만 표시할 수 있습니다. 스키마 정의에 따라 일부 필드는 필수이며 미리 선택될 수 있습니다. 선택 취소할 수 없습니다.

   >[!NOTE]
   >
   >XDM 스키마에 &quot;오케스트레이션&quot; 혼합을 추가했는지 확인하십시오. 이렇게 하면 스키마에 작업에 필요한 정보가 모두 포함됩니다 [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. 이벤트에서 받을 필드를 선택합니다. 비즈니스 사용자가 여정 중에 활용할 수 있는 필드입니다. 또한 이벤트와 연관된 사람을 식별하는 데 사용할 키도 포함해야 합니다( [이 페이지](../event/defining-the-event-key.md)참조).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >시스템에서 생성된 이벤트의 경우, **[!UICONTROL eventID]** 필드는 선택한 필드 목록에 자동으로 추가되므로 이벤트를 식별할 [!DNL Journey Orchestration] 수 있습니다. 이벤트를 밀어 넣는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

1. 필요한 필드 선택이 끝나면 를 클릭하거나 **[!UICONTROL Save]** 누릅니다 **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   선택한 필드 수가 **[!UICONTROL Payload]** 필드에 표시됩니다.

   ![](../assets/journey12.png)
