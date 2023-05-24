---
product: adobe campaign
title: 사용자 지정 작업 구성 정보
description: 사용자 지정 작업을 구성하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# 사용자 지정 작업 구성 정보 {#concept_sxy_bzs_dgb}

서드파티 시스템을 사용하여 메시지를 보내거나 원하는 경우 [!DNL Journey Orchestration] api 호출을 서드파티 시스템으로 전송하려면에 대한 연결을 구성하십시오 [!DNL Journey Orchestration]. 그러면 기술 사용자가 정의한 사용자 지정 작업을 여정 왼쪽 팔레트의 **[!UICONTROL Action]** 범주(참조) [이 페이지](../building-journeys/about-action-activities.md). 다음은 사용자 지정 작업으로 연결할 수 있는 시스템의 몇 가지 예입니다. Epsilon, Facebook, Adobe.io, Firebase 등

제한 사항은에 나열되어 있습니다. [이 페이지](../about/limitations.md).

사용자 지정 작업 매개 변수에서 간단한 컬렉션과 개체 컬렉션을 전달할 수 있습니다. 제한 사항에 대해서는 을 참조하십시오. [이 페이지](../usecase/collections.md#limitations). 또한 매개 변수에는 예상 형식(예: 문자열, 십진수 등)이 있습니다. 이러한 예상 형식을 준수하도록 주의해야 합니다. 다음을 참조하십시오. [사용 사례](../usecase/collections.md).

사용자 지정 작업을 구성하는 데 필요한 주요 단계는 다음과 같습니다.

1. 다음에서 **[!UICONTROL Actions]** 목록, 클릭 **[!UICONTROL Add]** 새 작업을 만듭니다. 작업 구성 창이 화면 오른쪽에 열립니다.

   ![](../assets/custom2.png)

1. 작업 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 말고 이름은 30자까지만 입력하십시오.

1. 작업에 설명을 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 이 작업을 사용하는 여정 수는 **[!UICONTROL Used in]** 필드. 다음을 클릭할 수 있습니다 **[!UICONTROL View journeys]** 단추를 클릭하여 이 작업을 사용하는 여정 목록을 표시합니다.
1. 다른 항목 정의 **[!UICONTROL URL Configuration]** 매개 변수. [이 페이지](../action/url-configuration.md)를 참조하십시오.
1. 구성 **[!UICONTROL Authentication]** 섹션. 이 구성은 데이터 소스의 경우와 동일합니다.  [이 섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)을 참조하십시오.
1. 다음을 정의합니다. **[!UICONTROL Action parameters]**. [이 페이지](../action/defining-the-message-parameters.md)를 참조하십시오.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   이제 사용자 지정 작업이 구성되었으며 여정에서 사용할 준비가 되었습니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

   >[!NOTE]
   >
   >여정에서 사용자 지정 작업을 사용하는 경우 대부분의 매개 변수는 읽기 전용입니다. 다음 작업만 수정할 수 있습니다. **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** 필드 및 **[!UICONTROL Authentication]** 섹션.
