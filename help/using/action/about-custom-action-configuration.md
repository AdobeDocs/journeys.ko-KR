---
product: adobe campaign
title: 사용자 지정 작업 구성 정보
description: 사용자 지정 작업을 구성하는 방법 알아보기
feature: 여정
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# 사용자 지정 작업 구성 정보 {#concept_sxy_bzs_dgb}

서드파티 시스템을 사용하여 메시지를 보내거나 [!DNL Journey Orchestration]이 서드파티 시스템에 API 호출을 전송하도록 하려면 여기서 [!DNL Journey Orchestration]에 대한 연결을 구성합니다. 기술 사용자가 정의한 사용자 정의 작업은 여정 왼쪽 팔레트의 **[!UICONTROL Action]** 범주에서 사용할 수 있습니다( [이 페이지](../building-journeys/about-action-activities.md) 참조). 다음은 사용자 지정 작업에 연결할 수 있는 시스템의 몇 가지 예입니다. Epsilon, Facebook, Adobe.io, Firebase 등
제한 사항은 [이 페이지](../about/limitations.md)에 나열되어 있습니다.

사용자 지정 작업을 구성하는 데 필요한 주요 단계는 다음과 같습니다.

1. **[!UICONTROL Actions]** 목록에서 **[!UICONTROL Add]** 를 클릭하여 새 작업을 만듭니다. 화면 오른쪽에 작업 구성 창이 열립니다.

   ![](../assets/custom2.png)

1. 작업의 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. 작업에 설명을 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 이 작업을 사용하는 여정 수가 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 단추를 클릭하여 이 작업을 사용하는 여정 목록을 표시할 수 있습니다.
1. 다른 **[!UICONTROL URL Configuration]** 매개 변수를 정의합니다. [이 페이지](../action/url-configuration.md)를 참조하십시오.
1. **[!UICONTROL Authentication]** 섹션을 구성합니다. 이 구성은 데이터 소스와 동일합니다.  [이 섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)을 참조하십시오.
1. **[!UICONTROL Message parameters]**&#x200B;을(를) 정의합니다. [이 페이지](../action/defining-the-message-parameters.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   이제 사용자 지정 작업이 구성되었으며 여정에서 사용할 준비가 되었습니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

   >[!NOTE]
   >
   >여정에서 사용자 지정 작업을 사용하면 대부분의 매개 변수가 읽기 전용입니다. **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** 필드 및 **[!UICONTROL Authentication]** 섹션만 수정할 수 있습니다.
