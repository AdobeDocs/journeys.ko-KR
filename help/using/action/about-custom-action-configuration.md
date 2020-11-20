---
product: adobe campaign
solution: Journey Orchestration
title: 사용자 지정 작업 구성
description: 사용자 지정 작업을 구성하는 방법 학습
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# 사용자 지정 작업 구성 {#concept_sxy_bzs_dgb}

제3자 시스템을 사용하여 메시지를 전송하거나 API 호출 [!DNL Journey Orchestration] 을 제3자 시스템에 전송하려는 경우 여기에서 연결을 구성합니다 [!DNL Journey Orchestration]. 그러면 기술 사용자가 정의한 사용자 지정 작업을 경로의 왼쪽 팔레트에서 **[!UICONTROL Action]** 카테고리( [이 페이지](../building-journeys/about-action-activities.md)참조)로 사용할 수 있습니다. 다음은 사용자 정의 동작과 연결할 수 있는 시스템의 몇 가지 예입니다.Epsilon, Facebook, Adobe.io, Firebase 등
제한 사항은 [이 페이지에 나열되어 있습니다](../about/limitations.md).

사용자 지정 작업을 구성하는 데 필요한 기본 단계는 다음과 같습니다.

1. 목록에서 **[!UICONTROL Actions]** 을 클릭하여 새 작업 **[!UICONTROL Add]** 을 만듭니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/custom2.png)

1. 작업 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. 작업에 설명을 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. [이 페이지](../action/url-configuration.md)를 참조하십시오.
1. 섹션을 **[!UICONTROL Authentication]** 구성합니다. 이 구성은 데이터 소스의 경우와 동일합니다.  [이 섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)을 참조하십시오.
1. 를 **[!UICONTROL Message parameters]**&#x200B;정의합니다. [이 페이지](../action/defining-the-message-parameters.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   이제 사용자 지정 작업이 구성되고 여정에 사용할 준비가 되었습니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

   >[!NOTE]
   >
   >사용자 지정 작업이 여정에서 사용될 경우 대부분의 매개 변수는 읽기 전용입니다. 단, **[!UICONTROL Name]**, **[!UICONTROL Description]**&#x200B;필드 **[!UICONTROL URL]** 및 **[!UICONTROL Authentication]** 섹션만 수정할 수 있습니다.
