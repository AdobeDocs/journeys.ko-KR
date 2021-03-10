---
product: adobe campaign
solution: Journey Orchestration
title: 페이로드 필드 정의
description: 페이로드 필드를 정의하는 방법에 대해 알아봅니다.
feature: 여정
role: 비즈니스 전문가
level: 중간
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 6%

---


# 페이로드 필드 정의 {#concept_yrw_3qt_52b}

페이로드 정의를 사용하면 시스템에서 여정의 이벤트에서 수신할 정보와 이벤트에 연결된 사람을 식별할 키를 선택할 수 있습니다. 페이로드가 Experience Cloud XDM 필드 정의를 기반으로 합니다. XDM에 대한 자세한 내용은 [이 페이지](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/home.html)를 참조하십시오.

1. 목록에서 XDM 스키마를 선택하고 **[!UICONTROL Payload]** 필드 또는 **[!UICONTROL Edit]** 아이콘을 클릭합니다.

   ![](../assets/journey8.png)

   스키마에 정의된 모든 필드가 표시됩니다. 필드 목록은 스키마마다 다릅니다. 특정 필드를 검색하거나 필터를 사용하여 모든 노드 및 필드를 표시하거나 선택한 필드만 표시할 수 있습니다. 스키마 정의에 따라 일부 필드는 필수일 수도 있고 미리 선택할 수도 있습니다. 선택 취소할 수 없습니다. Journey Orchestration에서 이벤트를 제대로 수신해야 하는 모든 필드는 기본적으로 선택됩니다.

   >[!NOTE]
   >
   >XDM 스키마에 &quot;오케스트레이션&quot; 믹싱을 추가해야 합니다. 이렇게 하면 스키마에 [!DNL Journey Orchestration]에서 작업하는 데 필요한 모든 정보가 포함되어 있습니다.

   ![](../assets/journey9.png)

1. 이벤트에서 받을 필드를 선택합니다. 비즈니스 사용자가 여정에서 활용할 필드입니다. 또한 이벤트에 연결된 사람을 식별하는 데 사용할 키를 포함해야 합니다([이 페이지](../event/defining-the-event-key.md) 참조).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >시스템에서 생성된 이벤트의 경우 **[!UICONTROL eventID]** 필드가 선택된 필드 목록에 자동으로 추가되므로 [!DNL Journey Orchestration] 는 이벤트를 식별할 수 있습니다. 이벤트를 실행하는 시스템은 ID를 생성하지 않아야 합니다. 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

1. 필요한 필드 선택이 끝나면 **[!UICONTROL Save]**&#x200B;을 클릭하거나 **[!UICONTROL Enter]**&#x200B;을(를) 누릅니다.

   ![](../assets/journey11.png)

   선택한 필드의 수가 **[!UICONTROL Payload]** 필드에 표시됩니다.

   ![](../assets/journey12.png)
