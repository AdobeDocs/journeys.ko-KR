---
product: adobe campaign
title: 데이터 소스 구성
description: 여정 고급 사용 사례에 맞게 데이터 소스를 구성하는 방법에 대해 알아봅니다
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 12%

---

# 데이터 소스 구성 {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


사용 사례에서는 메시지에 개인화 데이터를 사용하려고 합니다. 또한 충성도 멤버이며 지난 24시간 동안 연락을 하지 않았는지 확인해야 합니다. 이 정보는 실시간 고객 프로필 데이터베이스에 저장됩니다. **기술 사용자**&#x200B;가 해당 필드를 검색하도록 Adobe Experience Platform 데이터 원본을 구성해야 합니다.

데이터 원본 구성에 대한 자세한 내용은 [이 페이지](../datasource/about-data-sources.md)를 참조하세요.

1. 메뉴 창에서 **[!UICONTROL Admin]**&#x200B;을(를) 선택합니다. **[!UICONTROL Data sources]** 섹션에서 **[!UICONTROL Manage]**&#x200B;을(를) 클릭합니다.
1. 기본 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 사전 구성된 그룹 필드에서 다음 필드가 선택되어 있는지 확인합니다.

   * _사용자 > 이름 > 이름_
   * _사용자 > 이름 > 성_
   * _개인 전자 메일 > 주소_

1. **[!UICONTROL Add a New Field Group]**&#x200B;을(를) 클릭하고 **[!UICONTROL Profiles]** 스키마를 선택한 다음 조건에 대한 **충성도 멤버** 필드를 추가하십시오. **충성도 멤버** 필드는 사용자 지정 필드이며 XDM에 추가되었습니다. &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. **[!UICONTROL Add a New Field Group]**&#x200B;을(를) 클릭하고 **[!UICONTROL ExperienceEvent]** 스키마를 선택한 다음 지정된 기간에 보낸 메시지 수에 따라 조건에 필요한 필드를 선택합니다. 해당 날짜의 경우 _타임스탬프_, 보낸 메시지 수의 경우 _directMarketing > 보낸 사람 > 값_.

   ![](../assets/journeyuc2_7.png)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

호텔 예약 시스템에서도 예약자가 있는지 확인해야 합니다. **기술 사용자**&#x200B;가 이 필드를 검색하려면 두 번째 데이터 원본을 구성해야 합니다.

1. 데이터 원본 목록에서 **[!UICONTROL Add]**&#x200B;을(를) 클릭하여 새 외부 데이터 원본을 추가하여 호텔 예약 시스템에 대한 연결을 정의합니다.

   ![](../assets/journeyuc2_9.png)

1. 데이터 소스의 이름과 외부 서비스의 URL을 입력하십시오(예: _https://marlton.com/reservation_).

   >[!CAUTION]
   >
   >보안상의 이유로 HTTPS를 사용하는 것이 좋습니다.

1. 외부 서비스 구성에 따라 인증을 구성합니다. **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]**, **[!UICONTROL API key]** 중에서 선택할 수 있습니다. 이 예제에서는 유형에 대해 &quot;Basic&quot;을 선택하고 API 호출에 대한 사용자 이름과 암호를 지정합니다.

   ![](../assets/journeyuc2_10.png)

1. 검색할 정보 및 API 매개 변수를 정의하려면 **[!UICONTROL Add a New Field Group]**&#x200B;을(를) 클릭하십시오. 이 예제에는 매개 변수(id)가 하나만 있으므로 다음 정보를 사용하여 필드 그룹을 하나 만들어야 합니다.

   * **[!UICONTROL Method]**: POST 또는 GET 메서드를 선택합니다. 여기서는 GET 메서드를 선택합니다.
   * **[!UICONTROL Response Payload]**: **[!UICONTROL Payload]** 필드 내부를 클릭하고 페이로드의 예제를 붙여 넣습니다. 필드 유형이 올바른지 확인합니다. API를 호출할 때마다 시스템은 페이로드 예제에 포함된 모든 필드를 검색합니다. 이 예제에서 페이로드는 예약 상태만 포함합니다.

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: 각 고객을 식별하는 데 사용되는 키에 해당하는 매개 변수를 입력합니다. 이 예제에서는 &quot;id&quot;를 입력합니다. 이 매개 변수의 값은 여정에서 정의됩니다.

   ![](../assets/journeyuc2_11.png)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   이제 데이터 소스가 구성되었으며 여정에서 사용할 수 있는 상태가 되었습니다.
