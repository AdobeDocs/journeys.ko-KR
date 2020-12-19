---
product: adobe campaign
solution: Journey Orchestration
title: 'Adobe Experience Platform 데이터 소스 '
description: 'Adobe Experience Platform 데이터 소스를 구성하는 방법에 대해 알아봅니다. '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Adobe Experience Platform 데이터 소스 {#concept_zrb_nqt_52b}

Adobe Experience Platform 데이터 소스는 실시간 고객 프로필 서비스 연결을 정의합니다. 이 데이터 소스는 내장 및 사전 구성되어 있습니다. 삭제할 수 없습니다. 이 데이터 소스는 실시간 고객 프로필 서비스에서 데이터를 검색하고 사용하도록 설계되었습니다(예: 방문에 참여한 사람이 여성인지 확인). 프로필 데이터와 경험 이벤트 데이터를 사용할 수 있습니다. 실시간 고객 프로필 서비스에 대한 자세한 내용은 이 [페이지](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html)를 참조하십시오.

>[!NOTE]
>
>1년 전에 만든 1000개의 최신 경험 이벤트를 검색할 수 있습니다.

실시간 고객 프로필 서비스에 연결할 수 있도록 하려면 키를 사용하여 개인을 식별하고 키를 컨텍스트에 두는 네임스페이스를 사용해야 합니다. 따라서 키와 네임스페이스가 포함된 이벤트로 시작하는 경우에만 이 데이터 소스를 사용할 수 있습니다. [이 페이지](../building-journeys/journey.md)를 참조하십시오.

&quot;ProfileFieldGroup&quot;이라는 사전 구성된 필드 그룹을 편집하고, 새 필드 그룹을 추가하고, 초안 또는 라이브 여정에서 사용되지 않는 필드 그룹을 제거할 수 있습니다. [이 페이지](../datasource/field-groups.md)를 참조하십시오.

다음은 필드 그룹을 빌드 인 데이터 소스에 추가하는 기본 단계입니다.

1. 데이터 소스 목록에서 내장 Adobe Experience Platform 데이터 소스를 선택합니다.

   화면 오른쪽에 데이터 소스 구성 창이 열립니다.

   ![](../assets/journey23.png)

1. 검색할 새 일련의 필드를 정의하려면 **[!UICONTROL Add a New Field Group]**&#x200B;을 클릭합니다. [이 페이지](../datasource/field-groups.md)를 참조하십시오.

   ![](../assets/journey24.png)

1. **[!UICONTROL Schema]** 드롭다운에서 스키마를 선택합니다. 이 필드는 Adobe Experience Platform에서 사용할 수 있는 프로필 및 경험 이벤트 스키마를 나열합니다. [!DNL Journey Orchestration]에서 스키마 만들기가 수행되지 않습니다. Adobe Experience Platform에서 수행됩니다.
1. 사용할 필드를 선택합니다.
1. 캐시 지속 시간을 정의합니다.
1. **[!UICONTROL Save]**&#x200B;을 클릭합니다.

필드 그룹 이름에 커서를 두면 오른쪽에 2개의 아이콘이 표시됩니다. 필드 그룹을 삭제하고 복제할 수 있습니다. **[!UICONTROL Delete]** 아이콘은 필드 그룹이 라이브 또는 초안 경로(**[!UICONTROL Used in]** 필드에 표시된 정보)에서 사용되지 않는 경우에만 사용할 수 있습니다.
