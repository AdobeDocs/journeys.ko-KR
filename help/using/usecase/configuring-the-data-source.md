---
title: 데이터 소스 구성
description: 간단한 사용 사례의 데이터 소스를 구성하는 방법 살펴보기
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 6%

---


# 데이터 소스 구성{#concept_ax3_bcy_w2b}

사용 사례에서는 개인화 데이터를 메시지에 사용하고 싶습니다. 우리는 또한 그 사람이 여성이라는 것을 확인할 필요가 있습니다. 이 정보는 실시간 고객 프로필 데이터베이스에 저장됩니다. 이 **기술 사용자는** 해당 필드가 내장 Adobe Experience Platform 데이터 소스에 정의되어 있는지 확인해야 합니다.

데이터 소스 구성에 대한 자세한 내용은 을 참조하십시오 [](../datasource/about-data-sources.md).

1. 상단 메뉴에서 **[!UICONTROL Data Sources]** 탭을 클릭하고 내장 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 필드 그룹에서 다음 필드가 선택되어 있는지 확인합니다.

   * _사람 > 이름 > 이름_
   * _사람 > 이름 > 성_
   * _사람 > 성별_
   * _personalEmail > 주소_

1. **[!UICONTROL Save]**&#x200B;을 클릭합니다.

이제 데이터 소스가 구성되고 여정에서 사용할 준비가 되었습니다.
