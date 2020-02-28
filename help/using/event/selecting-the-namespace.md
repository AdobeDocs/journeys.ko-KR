---
title: 네임스페이스 선택
description: 네임스페이스를 선택하는 방법 살펴보기
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
source-git-commit: 411ecf0ec4dc6a87c4e129b40f2918799bef54bf

---


# 네임스페이스 선택 {#concept_ckb_3qt_52b}

이 네임스페이스를 사용하면 이벤트에 연결된 사람을 식별하는 데 사용되는 키 유형을 정의할 수 있습니다. 구성 옵션은 선택 사항입니다. 실시간 고객 프로필에서 오는 추가 정보를 검색하려는 경우 [필요합니다](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md). 사용자 지정 데이터 소스를 통해 타사 시스템에서 오는 데이터만 사용하는 경우에는 네임스페이스 정의가 필요하지 않습니다.

사전 정의된 항목 중 하나를 사용하거나 ID 네임스페이스 서비스를 사용하여 새 네임스페이스 서비스를 만들 수 있습니다. 이 [페이지를](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md)참조하십시오.

기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드가 미리 채워집니다. ID가 정의되지 않은 경우 기본 _키로 identityMap > id_ 를 선택합니다. 그런 다음 네임스페이스를 선택해야 합니다. 그러면 **[!UICONTROL Namespace]** idMap > id를 사용하여 키가 미리 _채워집니다_.

필드를 선택하면 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)


드롭다운 목록에서 네임스페이스를 선택합니다.

![](../assets/journey17.png)

여정당 하나의 네임스페이스만 허용됩니다. 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다. 을 [](../building-journeys/journey.md)참조하십시오.
