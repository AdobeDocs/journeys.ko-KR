---
product: adobe campaign
title: 대기 활동
description: 대기 활동에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 7%

---

# 대기 활동{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 여기를[&#128279;](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"} 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._



경로에서 다음 활동을 실행하기 전에 대기하려면 활동을 사용할 **[!UICONTROL Wait]** 수 있습니다. 이를 통해 다음 활동이 실행되는 시점을 정의할 수 있습니다. 다음 세 가지 옵션을 사용할 수 있습니다.

* [기간](#duration)
* [사용자 지정](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## 대기 활동 정보{#about_wait}

여러 대기를 병렬로 사용할 때 대기의 우선 순위를 지정하는 방법은 다음과 같습니다. 시간 구성이 동일하고 조건이 다르지만 겹치는 경우 위에 배치된 대기가 우선 순위가 지정됩니다. 예를 들어, 첫 번째 대기의 조건은 &quot;여성&quot;이고 두 번째 대기의 병행 조건은 &quot;VIP&quot;입니다. 첫 번째 대기 활동의 우선 순위가 지정됩니다.

또한 두 개의 서로 다른 대기가 동시에 있는 경우 수직 위치에 관계없이 먼저 발생하는 대기가 우선 순위가 지정됩니다. 예를 들어 1시간 대기 시간이 위 시간이고 30분 대기 시간이 아래 시간인 경우 30분 후 30분 대기가 처리됩니다.

>[!NOTE]
>
>최대 대기 기간은 30일입니다.
>
>테스트 모드에서 **[!UICONTROL Wait time in test]** 매개 변수를 사용하면 각 대기 활동이 지속되는 시간을 정의할 수 있습니다. 기본 시간은 10초입니다. 이렇게 하면 테스트 결과를 빠르게 얻을 수 있습니다. 이 페이지 참조 [&#128279;](../building-journeys/testing-the-journey.md)

## 기간 대기{#duration}

다음 활동을 실행하기 전에 대기할 기간을 선택합니다.

![](../assets/journey55.png)

## 사용자 지정 대기{#custom}

이 옵션을 사용하면 이벤트 또는 데이터 소스 출신의 필드를 기반으로 고급 표현식을 사용하여 사용자 지정 날짜(예: 2020년 7월 12일 오후 5시)를 정의할 수 있습니다. 사용자 지정 기간(예: 7일)을 정의할 수는 없습니다. 표현식 편집기 의 표현식은 dateTimeOnly 포맷 형식을 제공해야 합니다. 이 페이지 페이지를[&#128279;](../expression/expressionadvanced.md) 참조하십시오. dateTimeOnly 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

>[!NOTE]
>
>dateTimeOnly 식을 활용하거나 함수를 사용하여 dateTimeOnly로 변환할 수 있습니다. 예: toDateTimeOnly(@{Event.offerOpened.activity.endTime}). 이벤트의 필드는 양식 2016-08-12T09:46:06Z입니다.
>
>표준 시간대&#x200B;**는**&#x200B;여정의 속성에 필요합니다. 따라서 현재 인터페이스에서 전체 ISO-8601 타임스탬프 혼합 시간 및 시간대 오프셋 좋아요 2016-08-12T09:46:06.982-05를 직접 가리킬 수 없습니다. [이 페이지](../building-journeys/timezone-management.md)를 참조하십시오.

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
