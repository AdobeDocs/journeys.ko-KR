---
product: adobe campaign
title: 페이로드 필드 정의
description: 페이로드 필드를 정의하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 4%

---

# 페이로드 필드 정의 {#concept_yrw_3qt_52b}

페이로드 정의를 사용하면 여정의 이벤트에서 시스템이 받을 것으로 예상되는 정보와 해당 이벤트와 연관된 사용자를 식별하는 키를 선택할 수 있습니다. 페이로드는 Experience Cloud XDM 필드 정의를 기반으로 합니다. XDM에 대한 자세한 내용은 [이 페이지](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR)를 참조하세요.

1. 목록에서 XDM 스키마를 선택하고 **[!UICONTROL Payload]** 필드 또는 **[!UICONTROL Edit]** 아이콘을 클릭합니다.

   ![](../assets/journey8.png)

   스키마에 정의된 모든 필드가 표시됩니다. 필드 목록은 스키마마다 다릅니다. 특정 필드를 검색하거나 필터를 사용하여 모든 노드 및 필드를 표시하거나 선택한 필드만 표시할 수 있습니다. 스키마 정의에 따라 일부 필드는 필수이고 미리 선택될 수 있습니다. 선택을 취소할 수 없습니다. Journey Orchestration에서 이벤트를 제대로 수신하기 위해 반드시 필요한 모든 필드가 기본적으로 선택됩니다.

   >[!NOTE]
   >
   >XDM 스키마에 &quot;orchestration&quot; mixin을 추가했는지 확인합니다. 이렇게 하면 스키마에 [!DNL Journey Orchestration] 작업에 필요한 모든 정보가 포함됩니다.

   ![](../assets/journey9.png)

1. 이벤트에서 수신할 필드를 선택합니다. 비즈니스 사용자가 여정 시 활용할 필드입니다. 이벤트에 연결된 사용자를 식별하는 데 사용할 키도 포함해야 합니다([이 페이지](../event/defining-the-event-key.md) 참조).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >시스템 생성 이벤트의 경우 [!DNL Journey Orchestration]에서 이벤트를 식별할 수 있도록 선택한 필드 목록에 **[!UICONTROL eventID]** 필드가 자동으로 추가됩니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

1. 필요한 필드를 모두 선택했으면 **[!UICONTROL Save]**&#x200B;을(를) 클릭하거나 **[!UICONTROL Enter]**&#x200B;을(를) 누르십시오.

   ![](../assets/journey11.png)

   선택한 필드 수가 **[!UICONTROL Payload]** 필드에 나타납니다.

   ![](../assets/journey12.png)
