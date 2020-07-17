---
title: 대기 활동
description: 대기 활동에 대한 자세한 내용
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 1%

---


# 대기 활동{#section_rlm_nft_dgb}

경로에서 다음 활동을 실행하기 전에 기다리려면 **[!UICONTROL Wait]** 활동을 사용할 수 있습니다. 이를 통해 다음 활동이 실행될 시간을 정의할 수 있습니다. 다음 네 가지 옵션을 사용할 수 있습니다.

* [지속 시간](#duration)
* [고정 날짜](#fixed_date)
* [사용자 지정](#custom)
* [이메일 전송 시간 최적화](#email_send_time_optimization)

## 대기 활동 정보{#about_wait}

다음은 여러 개의 대기를 동시에 사용할 때 대기의 우선 순위가 지정되는 방법입니다. 동일한 시간 구성과 겹치는 조건이 서로 다른 경우 위에 배치된 대기 시간이 우선 순위가 지정됩니다. 예를 들어 첫 번째 대기 조건이 &quot;여성이 되는 것&quot;이고 두 번째 대기 조건이 &quot;VIP&quot;입니다. 첫 번째 대기 활동이 우선 순위가 지정됩니다.

또한 두 개의 서로 다른 대기가 동시에 있는 경우 먼저 발생하는 대기가 세로 위치에 관계없이 우선 순위가 지정됩니다. 예를 들어 1시간 대기 시간이 초과이고 30분 대기 시간이 30분 이후인 경우 30분 대기 시간이 처리됩니다.

특정 모집단으로의 대기를 제한하려면 조건을 정의할 수 있습니다.

>[!NOTE]
>
>최대 대기 기간은 30일입니다.
>
>테스트 모드에서 매개 변수를 사용하면 각 대기 활동이 지속될 시간을 정의할 수 **[!UICONTROL Wait time in test]** 있습니다. 기본 시간은 10초입니다. 그러면 테스트 결과가 빠르게 나올 수 있습니다. See [](../building-journeys/testing-the-journey.md)

## 기간 대기{#duration}

다음 활동을 실행하기 전 대기 시간을 선택합니다.

![](../assets/journey55.png)

## 고정 날짜 대기{#fixed_date}

다음 활동을 실행할 날짜를 선택합니다.

![](../assets/journey56.png)

## 사용자 지정 대기{#custom}

이 옵션을 사용하면 이벤트 또는 데이터 소스에서 온 필드를 기반으로 하는 고급 표현식을 사용하여 사용자 지정 날짜(예: 2020년 7월 12일 오후 5시)를 정의할 수 있습니다. 사용자 지정 기간(예: 7일)을 정의할 수 없습니다. 식 편집기의 표현식은 dateTimeOnly 형식을 제공해야 합니다. [](../expression/expressionadvanced.md)을 참조하십시오. dateTimeOnly 형식에 대한 자세한 내용은 을 참조하십시오 [](../expression/data-types.md).

>[!NOTE]
>
>dateTimeOnly 식을 활용하거나 함수를 사용하여 dateTimeOnly로 변환할 수 있습니다. 예: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), 2016-08-12T09:46:06 형식의 이벤트의 필드입니다.
>
>여정의 **속성에는 시간대가** 필요합니다. 따라서 인터페이스에서는 2016-08-12T09:46:06.982-05와 같은 전체 ISO-8601 타임스탬프 믹싱 시간 및 시간대 오프셋을 직접 가리키도록 할 수 없습니다. [](../building-journeys/timezone-management.md)을 참조하십시오.

![](../assets/journey57.png)

## 이메일 전송 시간 최적화{#email_send_time_optimization}

>[!CAUTION]
>
>이메일 전송 시간 최적화 기능은 Adobe Campaign Standard 데이터 서비스 기능을 사용하는 고객에게만 제공됩니다.

이 대기 유형은 Adobe Experience Platform에서 계산된 점수를 사용합니다. 점수는 과거 행동을 기반으로 향후 이메일을 클릭하거나 여는 경향을 계산합니다. 점수를 계산하는 알고리즘에는 일정 양의 데이터가 필요합니다. 따라서 데이터가 충분하지 않으면 기본 대기 시간이 적용됩니다. 발행 시 기본 시간이 적용된다는 알림이 표시됩니다.

>[!NOTE]
>
>경로의 첫 번째 이벤트에는 네임스페이스가 있어야 합니다.
>
>이 기능은 **[!UICONTROL Email]** 활동 후에만 사용할 수 있습니다. Adobe Campaign Standard이 필요합니다

1. 필드에서 이메일 전송을 최적화할 수 있는 시간을 **[!UICONTROL Amount of time]** 정의합니다.
1. 필드에서 **[!UICONTROL Optimization type]** 클릭 수를 늘리거나 열지 여부를 선택합니다.
1. 예측 전송 시간 점수를 사용할 수 없는 경우 이 **[!UICONTROL Default time]** 필드에서 대기할 기본 시간을 정의합니다.

   >[!NOTE]
   >
   >계산을 수행할 데이터가 충분하지 않기 때문에 전송 시간 점수를 사용할 수 없습니다. 이 경우, 게시 시 기본 시간이 적용된다는 메시지가 표시됩니다.

![](../assets/journey57bis.png)
