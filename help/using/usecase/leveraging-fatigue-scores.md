---
product: adobe campaign
title: 피로 점수 활용
description: 여정에서 피로도 점수를 활용하는 방법 알아보기
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 12%

---


# 경로 AI 활용 {#concept_dsh_1ry_wfb}

이 사용 사례에서는 여정에서 고객에게 과도한 요청을 하지 않도록 피로도 점수를 활용하는 방법을 보여 줍니다.

>[!NOTE]
>
>예측 피로도 점수 기능은 를 사용하는 고객에게만 제공됩니다. [Adobe Experience Platform 데이터 커넥터](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## 이벤트 구성 {#section_ptb_ws1_ffb}

에 설명된 단계를 수행합니다 [이 페이지](../event/about-events.md).

## 데이터 소스 구성 {#section_o3n_4yy_wfb}

기본 제공 데이터 소스에서 피로도 점수 필드를 선택하려면 다음 단계를 수행하십시오.

1. 메뉴 창에서 다음을 선택합니다. **[!UICONTROL Admin]**. **[!UICONTROL Data sources]** 섹션에서 **[!UICONTROL Manage]**&#x200B;을(를) 클릭합니다.
1. 기본 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 사용 사례에 필요한 필드를 선택했는지 확인합니다.
1. 클릭 **[!UICONTROL Add a New Field Group]**&#x200B;를 선택하고 **[!UICONTROL Profiles]** 모델을 만들고 추가 **[!UICONTROL fatigueLevel]** 및 **[!UICONTROL fatigueScore]** 필드(아래) _journeyAI > emailScore > 피로도_).

   ![](../assets/journeyuc3_1.png)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 여정 구축 {#section_uzm_pyy_wfb}

여정을 만들고, 유효성을 검사하고, 게시하려면 다음에 설명된 단계를 수행합니다 [이 페이지](../building-journeys/journey.md).

사용 사례에서는 **[!UICONTROL fatigueLevel]** 필드. 다음을 사용할 수도 있습니다 **[!UICONTROL fatigueScore]** 필드.

여정의 피로도 수준을 활용하려면 다음 단계를 수행하십시오.

1. 여정에 이벤트와 조건을 추가합니다.

   ![](../assets/journeyuc2_14.png)

1. **[!UICONTROL Data Source Condition]** 유형을 선택하고 **[!UICONTROL Expression]** 필드를 클릭합니다. 

   ![](../assets/journeyuc3_2.png)

1. 단순 표현식 편집기를 사용하여 **[!UICONTROL fatigueLevel]** 필드 (_ExperiencePlatformDataSource > JourneyAIScores > 프로필 > journeyAI > emailScore > 피로도_), 오른쪽에 두고 다음 조건을 만듭니다. &quot;fatigueLevel이 &quot;Low&quot;와 같습니다. **[!UICONTROL Ok]**&#x200B;을(를) 클릭합니다.

   ![](../assets/journeyuc3_3.png)

   고급 표현식:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 조건에서 보통 및 높은 피로도 수준에 대한 다른 두 경로를 만듭니다.

   ![](../assets/journeyuc3_4.png)

1. 이제 각 피로도 수준에 대해 서로 다른 작업을 추가할 수 있습니다.

   ![](../assets/journeyuc3_5.png)
