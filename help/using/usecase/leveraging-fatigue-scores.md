---
title: 피로 점수 활용
description: 여정의 피로 점수를 활용하는 방법 살펴보기
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 피로 점수 활용 {#concept_dsh_1ry_wfb}

이 활용 사례는 피로 점수를 활용하여 여행 중 고객의 과도한 구매를 방지하는 방법을 보여줍니다.

>[!CAUTION]
>
>예측 피로 점수 기능은 Adobe Campaign Standard 데이터 서비스 기능을 사용하는 고객에게만 제공됩니다.

## 이벤트 구성 {#section_ptb_ws1_ffb}

에 설명된 단계를 [](../event/about-events.md)수행합니다.

## 데이터 소스 구성 {#section_o3n_4yy_wfb}

내장 데이터 소스에서 피로 점수 필드를 선택하려면 다음 단계를 수행하십시오.

1. 상단 메뉴에서 **[!UICONTROL Data Sources]**탭을 클릭하고 내장된 경험 플랫폼 데이터 소스를 선택합니다.

   ![](../assets/journey23.png)

1. 사용 사례에 필요한 필드가 선택되었는지 확인합니다.
1. 을 **[!UICONTROL Add a New Field Group]**클릭하고**[!UICONTROL Profiles]** 모델을 선택하고 **[!UICONTROL fatigueLevel]**및**[!UICONTROL fatigueScore]** 필드를 추가합니다(여정AI > 이메일 점수 > 사용 유무 __).

   ![](../assets/journeyuc3_1.png)

1. 클릭 **[!UICONTROL Save]**.

## 고객 여정 구축 {#section_uzm_pyy_wfb}

여정을 만들고, 유효성을 확인하고, 게시하려면 에 설명된 단계를 따르십시오 [](../building-journeys/journey.md).

사용 사례에서 Adobe는 이 **[!UICONTROL fatigueLevel]**분야를 활용하고 있습니다. 필드를 사용할 수도**[!UICONTROL fatigueScore]** 있습니다.

다음 단계를 수행하여 여정의 피로 수준을 활용하십시오.

1. 여정에서 이벤트와 조건을 추가합니다.

   ![](../assets/journeyuc2_14.png)

1. 유형을 **[!UICONTROL Data Source Condition]**선택하고**[!UICONTROL Expression]** 필드를 클릭합니다.

   ![](../assets/journeyuc3_2.png)

1. 간단한 표현식 편집기를 사용하여 **[!UICONTROL fatigueLevel]**필드를 찾습니다(_ExperiencePlatformDataSource > JourneyAIScore > 프로필 > JourneyAI > emailScore > features_). 그런 다음 오른쪽으로 드롭하여 다음 조건을 만듭니다.&quot;featuresLevel은 &quot;낮음&quot;과 같습니다. 클릭**[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   고급 표현식은 다음과 같습니다.

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 이 경우 중고 및 고피로도를 위한 다른 두 가지 경로를 만듭니다.

   ![](../assets/journeyuc3_4.png)

1. 이제 각 피로 수준에 대해 다른 작업을 추가할 수 있습니다.

   ![](../assets/journeyuc3_5.png)
