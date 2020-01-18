---
title: 'Adobe Experience Platform 데이터 소스 '
description: 'Adobe Experience Platform 데이터 소스를 구성하는 방법 살펴보기 '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Adobe Experience Platform 데이터 소스 {#concept_zrb_nqt_52b}

경험 플랫폼 데이터 소스는 실시간 고객 프로필 서비스에 대한 연결을 정의합니다. 이 데이터 소스는 기본 제공 및 사전 구성되어 있습니다. 삭제할 수 없습니다. 이 데이터 소스는 실시간 고객 프로필 서비스에서 데이터를 검색하고 사용하기 위해 고안되었습니다(예: 여행 입력한 사람이 여성인지 확인). 프로필 데이터와 경험 이벤트 데이터를 사용할 수 있습니다. 실시간 고객 프로필 서비스에 대한 자세한 내용은 이 [페이지를](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)참조하십시오.

>[!NOTE]
>
>1년 전에 만든 1,000개의 최신 경험 이벤트를 검색할 수 있습니다.

실시간 고객 프로필 서비스에 연결할 수 있도록 하려면 키를 사용하여 사용자를 식별하고 키에 맞는 네임스페이스를 사용해야 합니다. 따라서, 키와 네임스페이스가 포함된 이벤트로 시작되는 경우에만 이 데이터 소스를 사용할 수 있습니다. 을 [](../building-journeys/journey.md)참조하십시오.

&quot;ProfileFieldGroup&quot;이라는 사전 구성된 필드 그룹을 편집하고, 새 필드 그룹을 추가하고, 초안 또는 라이브 여정에서 사용되지 않는 필드 그룹을 제거할 수 있습니다. 을 [](../datasource/field-groups.md)참조하십시오.

다음은 필드 그룹을 내장 데이터 소스에 추가하는 기본 단계입니다.

1. 데이터 소스 목록에서 내장된 경험 플랫폼 데이터 소스를 선택합니다.

   화면의 오른쪽에 데이터 소스 구성 창이 열립니다.

   ![](../assets/journey23.png)

1. 검색할 새 일련의 필드를 **[!UICONTROL Add a New Field Group]**정의하려면 클릭합니다. 을[](../datasource/field-groups.md)참조하십시오.

   ![](../assets/journey24.png)

1. 드롭다운에서 스키마를 **[!UICONTROL Schema]**선택합니다. 이 필드에는 플랫폼에서 사용할 수 있는 프로필 및 경험 이벤트 스키마가 나열됩니다. 스키마 만들기가 경로 지정 오케스트레이션에서 수행되지 않습니다. 데이터 플랫폼에서 수행됩니다.
1. 사용할 필드를 선택합니다.
1. 캐시 지속 시간을 정의합니다.
1. 을 **[!UICONTROL Save]**클릭합니다.

필드 그룹 이름에 커서를 두면 오른쪽에 두 개의 아이콘이 표시됩니다. 이러한 기능을 사용하면 필드 그룹을 삭제하고 복제할 수 있습니다. 이 **[!UICONTROL Delete]**아이콘은 필드 그룹이 라이브 경로 또는 초안 경로(**[!UICONTROL Used in]** 필드에 표시된 정보)에서 사용되지 않는 경우에만 사용할 수 있습니다.
