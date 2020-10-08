---
title: 네임스페이스 선택
description: 네임스페이스를 선택하는 방법
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 11%

---


# 네임스페이스 선택 {#concept_ckb_3qt_52b}

이 네임스페이스를 통해 이벤트에 연결된 사람을 식별하는 데 사용되는 키 유형을 정의할 수 있습니다. 구성은 선택 사항입니다. 실시간 고객 프로파일에서 얻은 추가 정보를 검색하려는 경우 [필요합니다](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html). 사용자 지정 데이터 소스를 통해 타사 시스템에서 오는 데이터만 사용하는 경우에는 네임스페이스 정의가 필요하지 않습니다.

사전 정의된 항목 중 하나를 사용하거나 ID 네임스페이스 서비스를 사용하여 새 항목을 만들 수 있습니다. Refer to this [page](https://docs.adobe.com/content/help/ko-KR/experience-platform/identity/home.html).

기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드가 미리 채워집니다. ID가 정의되지 않은 경우 기본 키로 _identityMap > id_ 를 선택합니다. 그런 다음 네임스페이스를 선택해야 합니다. 그러면 **[!UICONTROL Namespace]** identityMap > id를 사용하여 키(필드 아래 _)가 미리 채워집니다_.

필드를 선택하면 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)


드롭다운 목록에서 네임스페이스를 선택합니다.

![](../assets/journey17.png)

여정당 하나의 네임스페이스만 허용됩니다. 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다. [](../building-journeys/journey.md)을(를) 참조하십시오.
