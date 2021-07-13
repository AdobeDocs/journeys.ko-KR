---
product: adobe campaign
title: 페이로드 필드 정의
description: 페이로드 필드를 정의하는 방법에 대해 알아봅니다
feature: 여정
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 6%

---

# 페이로드 필드 정의 {#concept_yrw_3qt_52b}

페이로드 정의를 사용하면 시스템에서 여정의 이벤트에서 받게 될 정보를 선택하고 키와 어떤 사람이 이벤트에 연결되어 있는지 식별할 수 있습니다. 페이로드는 Experience Cloud XDM 필드 정의를 기반으로 합니다. XDM에 대한 자세한 내용은 [이 페이지](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko)를 참조하십시오.

1. 목록에서 XDM 스키마를 선택하고 **[!UICONTROL Payload]** 필드 또는 **[!UICONTROL Edit]** 아이콘을 클릭합니다.

   ![](../assets/journey8.png)

   스키마에 정의된 모든 필드가 표시됩니다. 필드 목록은 스키마마다 다릅니다. 특정 필드를 검색하거나 필터를 사용하여 모든 노드와 필드를 표시하거나 선택한 필드만 표시할 수 있습니다. 스키마 정의에 따라 일부 필드는 필수 필드이며 미리 선택되어 있을 수 있습니다. 선택 취소할 수 없습니다. Journey Orchestration에서 이벤트를 제대로 수신하기 위해 필요한 모든 필드는 기본적으로 선택됩니다.

   >[!NOTE]
   >
   >XDM 스키마에 &quot;orchestration&quot; mixin을 추가해야 합니다. 이렇게 하면 스키마에 [!DNL Journey Orchestration]에서 작업하는 데 필요한 모든 정보가 포함됩니다.

   ![](../assets/journey9.png)

1. 이벤트에서 받을 필드를 선택합니다. 비즈니스 사용자가 여정에서 활용할 수 있는 필드입니다. 또한 이벤트와 연결된 사람을 식별하는 데 사용할 키도 포함해야 합니다( [이 페이지](../event/defining-the-event-key.md) 참조).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >시스템 생성 이벤트의 경우, **[!UICONTROL eventID]** 필드가 선택한 필드 목록에 자동으로 추가되어 [!DNL Journey Orchestration] 이 이벤트를 식별할 수 있습니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

1. 필요한 필드 선택을 완료했으면 **[!UICONTROL Save]** 을 클릭하거나 **[!UICONTROL Enter]** 키를 누릅니다.

   ![](../assets/journey11.png)

   선택한 필드 수가 **[!UICONTROL Payload]** 필드에 나타납니다.

   ![](../assets/journey12.png)
