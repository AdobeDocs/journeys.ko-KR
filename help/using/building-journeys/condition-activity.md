---
title: 조건 활동
description: 조건 활동에 대한 자세한 내용
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
source-git-commit: 11c266b035bc1bb83cccf4e3958e54e1eb00e9f4
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---


# 조건 활동{#section_e2n_pft_dgb}

4가지 유형의 조건을 사용할 수 있습니다.

* [데이터 소스 조건](#data_source_condition)
* [시간 조건](#time_condition)
* [비율 분할](#percentage_split)
* [날짜 조건](#date_condition)

![](../assets/journey49.png)

## 조건 활동 정보 {#about_condition}

여러 조건을 정의하려면 **[!UICONTROL Add a path]** 클릭합니다. 각 조건에 대해 활동 후에 캔버스에 새 경로가 추가됩니다.

![](../assets/journey47.png)

여정의 디자인은 기능적으로 영향을 미친다. 조건 후에 여러 경로가 정의되면 첫 번째 적격한 경로만 실행됩니다. 즉, 경로의 우선 순위를 서로 위나 아래에 배치하여 변경할 수 있습니다. 예를 들어, 첫 번째 경로의 조건이 &quot;The person is a VIP&quot;이고 두 번째 경로의 조건은 &quot;The person is a male&quot;인 경우. 두 조건을 모두 충족하는 사람(VIP인 남성)이 이 이 단계를 통과하면 첫 번째 경로가 &quot;위&quot;이기 때문에 두 번째 경로에도 해당되더라도 첫 번째 경로가 선택됩니다. 이 우선 순위를 변경하려면 활동을 다른 세로 순서로 이동합니다.

![](../assets/journey48.png)

정의된 조건에 해당되지 않는 대상에 대해 확인란을 선택하여 다른 경로를 만들 수 있습니다 **[!UICONTROL Show path for other cases than the one(s) above]**. 분할 조건에서는 이 옵션을 사용할 수 없습니다. 백분율 [분할을 참조하십시오](#percentage_split).

단순 모드에서는 필드 조합을 기반으로 간단한 쿼리를 수행할 수 있습니다. 사용 가능한 모든 필드가 화면 왼쪽에 표시됩니다. 필드를 주 영역으로 드래그하여 놓습니다. 서로 다른 요소를 결합하려면 요소를 서로 인터록하여 다양한 그룹 및/또는 그룹 수준을 만듭니다. 그런 다음 논리 연산자를 선택하여 동일한 수준에서 요소를 결합할 수 있습니다.

* AND: 두 가지 기준이 교차하는 점. 모든 기준과 일치하는 요소만 고려됩니다.
* OR: 두 가지 기준의 결합. 두 기준 중 하나 이상에 맞는 요소가 고려됩니다.

![](../assets/journey64.png)

플랫폼 세그멘테이션 서비스를 사용하여 [세그먼트를](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) 만드는 경우 고객 여정 조건에서 이러한 세그먼트를 활용할 수 있습니다. 조건에 [세그먼트 사용을 참조하십시오](../segment/using-a-segment.md).


>[!NOTE]
>
>단순 편집기를 사용하여 시간 시리즈(예: 구매 목록, 메시지 클릭 수)에서 쿼리를 수행할 수 없습니다. 이를 위해서는 고급 편집기를 사용해야 합니다. [](../expression/expressionadvanced.md)을 참조하십시오.

## 데이터 소스 조건 {#data_source_condition}

이렇게 하면 데이터 소스의 필드 또는 이전에 여정에 배치된 이벤트를 기반으로 조건을 정의할 수 있습니다. 표현식 편집기 사용 방법을 알려면 을 참조하십시오 [](../expression/expressionadvanced.md). 고급 표현식 편집기를 사용하면 컬렉션을 조작하거나 매개 변수를 전달해야 하는 데이터 소스를 사용하여 더 많은 고급 조건을 설정할 수 있습니다. [](../datasource/external-data-sources.md)을 참조하십시오.

![](../assets/journey50.png)

## 시간 조건{#time_condition}

이렇게 하면 하루 중 시간 및/또는 요일에 따라 다른 작업을 수행할 수 있습니다. 예를 들어 주중에는 낮에 SMS 메시지를 보내고 밤에는 낮에 이메일을 보내도록 결정할 수 있습니다.

>[!NOTE]
>
>시간대는 더 이상 조건에 한정되지 않으며 이제 경로 속성의 경로 수준에서 정의됩니다. [](../building-journeys/timezone-management.md)을 참조하십시오.

![](../assets/journey51.png)

## 비율 분할 {#percentage_split}

이 옵션을 사용하면 임의로 대상을 분할하여 각 그룹에 대해 다른 작업을 정의할 수 있습니다. 각 경로에 대해 분할 수와 재분할 횟수를 정의합니다. 시스템이 여정의 이 활동에서 얼마나 많은 사람들이 오는지 예측할 수 없기 때문에, 분할 계산은 통계적이다. 그 결과, 분할의 오차 여백이 매우 낮습니다. 이 함수는 Java 임의 메커니즘을 기반으로 합니다(이 [페이지](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)참조).

>[!NOTE]
>
>비율 분할 조건에 경로를 추가할 단추가 없습니다. 경로 수는 분할 수에 따라 달라집니다. 분할 조건에서는 다른 사례에 대한 경로를 추가할 수 없으므로 추가할 수 없습니다. 사람들은 항상 갈려가는 길 중 하나로 갈 것이다.


![](../assets/journey52.png)

## 날짜 조건 {#date_condition}

날짜를 기준으로 다른 흐름을 정의할 수 있습니다. 예를 들어, 사용자가 &quot;판매&quot; 기간 동안 단계를 시작하는 경우 특정 메시지를 보냅니다. 남은 1년 동안, 다른 메시지를 보낼 수 있습니다.

>[!NOTE]
>
>시간대는 더 이상 조건에 한정되지 않으며 이제 경로 속성의 경로 수준에서 정의됩니다. [](../building-journeys/timezone-management.md)을 참조하십시오.

![](../assets/journey53.png)
