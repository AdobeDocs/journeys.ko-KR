---
product: adobe campaign
solution: Journey Orchestration
title: 피로 점수 활용
description: 여정 중 피로도를 활용하는 방법 살펴보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# 경로 AI 활용 {#concept_dsh_1ry_wfb}

이 사용 사례에서는 피로 점수를 활용하여 고객이 과도한 구매를 하지 않도록 하는 방법을 보여줍니다.

>[!NOTE]
>
>예측 유무 점수 기능은 [Adobe Experience Platform 데이터 커넥터를 사용하는 고객에게만 제공됩니다](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

## 이벤트 구성 {#section_ptb_ws1_ffb}

이 페이지에 설명된 단계 [를 따릅니다](../event/about-events.md).

## 데이터 소스 구성 {#section_o3n_4yy_wfb}

내장 데이터 소스에서 피로 점수 필드를 선택하려면 다음 단계를 수행하십시오.

1. 상단 메뉴에서 **[!UICONTROL Data Sources]** 탭을 클릭하고 내장 Adobe Experience Platform 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 사용 사례에 필요한 필드가 선택되었는지 확인합니다.
1. 를 **[!UICONTROL Add a New Field Group]**&#x200B;클릭하고 **[!UICONTROL Profiles]** 모델을 선택한 다음 **[!UICONTROL fatigueLevel]** 및 **[!UICONTROL fatigueScore]** 필드를 추가합니다( _여정AI > 이메일 점수 > 사용 유무_).

   ![](../assets/journeyuc3_1.png)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 여정 구축 {#section_uzm_pyy_wfb}

여정을 만들고, 유효성을 확인하고, 게시하려면 [이 페이지에 설명된 단계를 따릅니다](../building-journeys/journey.md).

사용 사례에서는 **[!UICONTROL fatigueLevel]** 분야를 활용하고 있습니다. 필드를 사용할 수도 **[!UICONTROL fatigueScore]** 있습니다.

다음 단계를 수행하여 여정의 피로도를 활용하십시오.

1. 여정에서 이벤트와 조건을 추가합니다.

   ![](../assets/journeyuc2_14.png)

1. **[!UICONTROL Data Source Condition]** 유형을 선택하고 **[!UICONTROL Expression]** 필드를 클릭합니다. 

   ![](../assets/journeyuc3_2.png)

1. 간단한 표현식 편집기를 사용하여 **[!UICONTROL fatigueLevel]** 필드를 찾아(_ExperiencePlatformDataSource > JourneyAIScore > 프로필 > JourneyAI > emailScore > 피로도_) 오른쪽으로 삭제한 다음 조건을 만듭니다.&quot;피로도가 &quot;낮음&quot;과 같습니다. **[!UICONTROL Ok]**&#x200B;을(를) 클릭합니다.

   ![](../assets/journeyuc3_3.png)

   고급 표현식:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 이 경우 중고 및 고피로도를 위한 다른 두 개의 경로를 만듭니다.

   ![](../assets/journeyuc3_4.png)

1. 이제 각 피로 수준에 대해 다른 작업을 추가할 수 있습니다.

   ![](../assets/journeyuc3_5.png)
