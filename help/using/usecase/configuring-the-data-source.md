---
product: adobe campaign
title: 데이터 소스 구성
description: 여정 단순 사용 사례에 대한 데이터 소스를 구성하는 방법을 알아봅니다
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 6%

---

# 데이터 소스 구성{#concept_ax3_bcy_w2b}

사용 사례에서는 메시지에 개인화 데이터를 사용하려고 합니다. 우리는 또한 그 사람이 여성인지 확인할 필요가 있습니다. 이 정보는 실시간 고객 프로필 데이터베이스에 저장됩니다. 다음 **기술 사용자** 에서는 이러한 필드가 기본 제공 Adobe Experience Platform 데이터 소스에 정의되어 있는지 확인해야 합니다.

데이터 소스 구성에 대한 자세한 내용은 [이 페이지](../datasource/about-data-sources.md).

1. 메뉴 창에서 **[!UICONTROL Admin]**. 에서 **[!UICONTROL Data sources]** 섹션을 클릭합니다. **[!UICONTROL Manage]**.
1. 기본 제공 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 필드 그룹에서 다음 필드가 선택되어 있는지 확인합니다.

   * _person > name > firstName_
   * _person > name > lastName_
   * _사람 > 성별_
   * _personalEmail > address_

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

이제 데이터 소스가 구성되었으며 여정에서 사용할 준비가 되었습니다.
