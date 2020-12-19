---
product: adobe campaign
solution: Journey Orchestration
title: 사용자 지정 작업 구성
description: 사용자 지정 작업을 구성하는 방법 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# 사용자 지정 작업 구성 {#concept_sxy_bzs_dgb}

제3자 시스템을 사용하여 메시지를 보내거나 [!DNL Journey Orchestration]에서 API 호출을 제3자 시스템으로 보내려면 [!DNL Journey Orchestration]에 대한 연결을 구성합니다. 그러면 기술 사용자가 정의한 사용자 지정 작업은 **[!UICONTROL Action]** 카테고리의 왼쪽 팔레트에서 사용할 수 있습니다([이 페이지](../building-journeys/about-action-activities.md) 참조). 다음은 사용자 정의 동작으로 연결할 수 있는 시스템의 몇 가지 예입니다.Epsilon, Facebook, Adobe.io, Firebase 등
제한 사항은 [이 페이지](../about/limitations.md)에 나열됩니다.

사용자 지정 작업을 구성하는 데 필요한 기본 단계는 다음과 같습니다.

1. **[!UICONTROL Actions]** 목록에서 **[!UICONTROL Add]**&#x200B;을 클릭하여 새 작업을 만듭니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/custom2.png)

1. 작업 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. 액션에 설명을 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 이 작업을 사용하는 여정 수는 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 단추를 클릭하여 이 작업을 사용하는 여행 목록을 표시할 수 있습니다.
1. 다른 **[!UICONTROL URL Configuration]** 매개 변수를 정의합니다. [이 페이지](../action/url-configuration.md)를 참조하십시오.
1. **[!UICONTROL Authentication]** 섹션을 구성합니다. 이 구성은 데이터 소스의 구성과 동일합니다.  [이 섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)을 참조하십시오.
1. **[!UICONTROL Message parameters]**&#x200B;을(를) 정의합니다. [이 페이지](../action/defining-the-message-parameters.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   이제 사용자 지정 작업이 구성된 후 여정에서 사용할 준비가 되었습니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

   >[!NOTE]
   >
   >사용자 정의 액션이 여정에서 사용될 경우 대부분의 매개 변수는 읽기 전용입니다. **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** 필드 및 **[!UICONTROL Authentication]** 섹션만 수정할 수 있습니다.
