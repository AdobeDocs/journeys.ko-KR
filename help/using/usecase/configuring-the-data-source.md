---
product: adobe campaign
title: 데이터 소스 구성
description: 여정 단순 사용 사례에 대한 데이터 소스 구성 방법에 대해 알아보십시오
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 5%

---

# 데이터 소스 구성{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Adobe Systems Journey Optimizer** 특가를 찾고 계십니까? Journey Optimizer 설명서를 보려면 여기를](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"} 클릭하십시오[.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._


이 사용 사례에서는 메시지에 개인화 데이터를 사용하려고 합니다. 우리는 또한 그 사람이 여성인지 확인해야 합니다. 이 정보는 실시간 고객 프로필 데이터베이스에 저장됩니다. **기술 사용자** 는 해당 필드가 내장된 Adobe Experience Platform 데이터 소스에 정의되어 있는지 확인해야 합니다.

데이터 소스 구성에 대한 자세한 내용은 이 페이지 페이지를](../datasource/about-data-sources.md) 참조하십시오[.

1. 메뉴 창에서 을 선택합니다 **[!UICONTROL Admin]**. **[!UICONTROL Data sources]** 섹션에서 을 클릭합니다&#x200B;**[!UICONTROL Manage]**.
1. 빌드 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 필드 그룹에서 다음 필드가 선택되어 있는지 확인합니다.

   * _person > name > firstName_
   * _person > name > lastName_
   * _성별> 사람_
   * _개인이메일 > 주소_

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

이제 데이터 소스 구성이 완료되었으며 여정에서 사용할 준비가 되었습니다.
