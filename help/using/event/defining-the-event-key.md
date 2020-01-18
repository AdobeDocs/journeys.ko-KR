---
title: 이벤트 키 정의
description: 이벤트 키 정의 방법 학습
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 이벤트 키 정의 {#concept_ond_hqt_52b}

키는 이벤트 페이로드 데이터의 필드나 필드 조합이 이벤트 페이로드 데이터의 일부이며, 시스템에서 이벤트와 연관된 사람을 식별할 수 있도록 합니다. 키(예: Experience Cloud ID, CRM ID 또는 이메일 주소)는

실시간 고객 프로파일 데이터베이스에 저장된 데이터를 활용하려면 실시간 고객 프로파일 서비스에서 프로파일 ID로 정의한 정보를 이벤트 키로 선택해야 [합니다](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

그러면 시스템이 이벤트와 개인의 프로필 간의 조정을 수행할 수 있습니다. 기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]**및**[!UICONTROL Namespace]** 필드가 미리 채워집니다. ID가 정의되지 않은 경우 기본 _키로 identityMap > id_ 를 선택합니다. 그런 다음 네임스페이스를 선택해야 합니다. 그러면 **[!UICONTROL Namespace]**idMap > id를 사용하여 키가 미리&#x200B;_채워집니다_.

CRM ID 또는 이메일 주소와 같은 다른 키를 사용해야 하는 경우 수동으로 추가해야 합니다.

1. 필드 안이나 연필 아이콘을 **[!UICONTROL Key]**클릭합니다.

   ![](../assets/journey16.png)

1. 페이로드 필드 목록에서 키로 선택한 필드를 선택합니다. 고급 표현식 편집기로 전환하여 보다 복잡한 키(예: 이벤트의 두 필드 연결)를 만들 수도 있습니다. 아래 섹션을 참조하십시오.

   ![](../assets/journey20.png)

이벤트가 수신되면 키 값을 통해 시스템에서 이벤트와 연결된 사람을 식별할 수 있습니다. 네임스페이스와 연결된 키( [](../event/selecting-the-namespace.md)참조)를 사용하여 Adobe Experience Platform에서 쿼리를 수행할 수 있습니다. 을 [](../building-journeys/about-orchestration-activities.md)참조하십시오.
열쇠는 또한 한 사람이 여행 중에 있는지 확인하는 데 사용됩니다. 사실, 사람은 같은 여행에서 두 개의 다른 장소에 있을 수 없습니다. 따라서, 시스템은 같은 키(예: 키 CRMID=3224)를 동일한 여정에서 다른 위치에 둘 수 없습니다.

추가 조작을 수행하려면 고급 표현식 함수(**[!UICONTROL Advanced mode]**)에 액세스할 수도 있습니다. 이러한 함수를 사용하면 필드의 일부(예: 첫 번째 문자 10개)만 고려하여, 형식 변경, 필드 연결 수행 등 특정 쿼리를 수행하는 데 사용되는 값을 조작할 수 있습니다. 을[](../expression/expressionadvanced.md)참조하십시오.
