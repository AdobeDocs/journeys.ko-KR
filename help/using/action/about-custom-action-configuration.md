---
title: 사용자 지정 작업 구성 정보
description: 사용자 지정 작업을 구성하는 방법 학습
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 사용자 지정 작업 구성 정보 {#concept_sxy_bzs_dgb}

타사 시스템을 사용하여 메시지를 전송하거나 여정 오케스트레이션이 타사 시스템으로 API 호출을 전송하도록 하려는 경우, 여정 오케스트레이션에 대한 연결을 구성합니다. 기술 사용자가 정의한 사용자 지정 작업은 **[!UICONTROL Action]**카테고리의 왼쪽 팔레트에서 사용할 수 있습니다(참조[](../building-journeys/about-action-activities.md)). 다음은 사용자 지정 동작과 연결할 수 있는 시스템의 몇 가지 예입니다.Epsilon, Facebook, Adobe.io, Firebase 등
제한 사항은 다음과 같습니다.[](../action/custom-action-limitations.md)Adobe

다음은 사용자 지정 작업을 구성하는 데 필요한 기본 단계입니다.

1. 목록에서 **[!UICONTROL Actions]**아이콘을 클릭하여 새 작업을**[!UICONTROL Add]** 만듭니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/custom2.png)

1. 작업 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 마십시오. 30자를 초과하여 사용하지 마십시오.

1. 작업에 설명을 추가합니다. 이 단계는 선택 사항입니다.
1. 이 동작을 사용하는 여정 수가 **[!UICONTROL Used in]**필드에 표시됩니다. 이 동작을 사용하는 여행 목록을 표시하려면**[!UICONTROL View journeys]** 단추를 클릭합니다.
1. 다른 **[!UICONTROL URL Configuration]**매개 변수를 정의합니다. 을[](../action/url-configuration.md)참조하십시오.
1. 섹션을 **[!UICONTROL Authentication]**구성합니다. 이 구성은 데이터 소스의 경우와 동일합니다.  을[](../datasource/external-data-sources.md#section_wjp_nl5_nhb)참조하십시오.
1. 를 **[!UICONTROL Message parameters]**정의합니다. 을[](../action/defining-the-message-parameters.md)참조하십시오.
1. 클릭 **[!UICONTROL Save]**.

   이제 사용자 지정 작업이 구성되고 여정에서 사용할 준비가 되었습니다. 을 [](../building-journeys/about-action-activities.md)참조하십시오.

   >[!NOTE]
   >
   >사용자 지정 작업이 경로 버전에서 사용될 경우 대부분의 매개 변수는 읽기 전용입니다. 이름 및 설명 필드만 수정할 수 있습니다.
