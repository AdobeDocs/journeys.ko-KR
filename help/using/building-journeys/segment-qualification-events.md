---
product: adobe campaign
title: 세그먼트 자격 이벤트
description: 세그먼트 자격 이벤트에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 5%

---

# 세그먼트 자격 이벤트 {#segment-qualification}

## 세그먼트 자격 이벤트 기본 정보{#about-segment-qualification}

이 활동을 통해 Adobe Experience Platform 세그먼트의 프로필의 처음과 끝에서 의견을 수렴하여 개인 사용자가 여정으로 들어오거나 이동할 수 있습니다. 세그먼트 만들기에 대한 자세한 내용은 다음을 참조하십시오. [섹션](../segment/about-segments.md).

&quot;실버 고객&quot; 세그먼트가 있다고 가정해 보겠습니다. 이 활동을 사용하면 모든 신규 실버 고객이 여정을 입력하고 일련의 개인화된 메시지를 보내도록 할 수 있습니다.

이 유형의 이벤트는 여정에서 첫 번째 단계 또는 그 이후로 배치할 수 있습니다.

>[!IMPORTANT]
>
>Adobe Experience Platform 세그먼트는 하루에 한 번(**일괄 처리** 세그먼트) 또는 실시간(**스트리밍됨** 세그먼트, Adobe Experience Platform의 고빈도 대상 옵션 사용).
>
>선택한 세그먼트가 스트리밍되는 경우 이 세그먼트에 속하는 개인은 잠재적으로 실시간으로 여정에 입장할 수 있습니다. 세그먼트가 일괄 처리인 경우 Adobe Experience Platform에서 세그먼트 계산이 실행될 때 이 세그먼트에 대해 새로 자격을 얻은 사람이 여정에 들어올 수 있습니다.


1. 펼치기 **[!UICONTROL Events]** 범주 및 놓기 **[!UICONTROL Segment qualification]** 활동을 캔버스에 추가합니다.

   ![](../assets/segment5.png)

1. 추가 **[!UICONTROL Label]** 을 활동에 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.

1. 을(를) 클릭합니다. **[!UICONTROL Segment]** 을(를) 필드에 추가하고 활용할 세그먼트를 선택합니다.

   >[!NOTE]
   >
   >목록에 표시되는 열을 사용자 정의하고 정렬할 수 있습니다.

   ![](../assets/segment6.png)

   세그먼트가 추가되면 **[!UICONTROL Copy]** 버튼을 사용하면 해당 이름과 ID를 복사할 수 있습니다.

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 다음에서 **[!UICONTROL Behaviour]** 필드에서 세그먼트 시작, 종료 또는 둘 다 수신 여부를 선택합니다.

   >[!NOTE]
   >
   >참고: **[!UICONTROL Enter]** 및 **[!UICONTROL Exit]** 다음에 해당합니다. **실현됨** 및 **종료됨** Adobe Experience Platform의 세그먼트 기여도 상태. 세그먼트를 평가하는 방법에 대한 자세한 내용은 [세그먼테이션 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. 네임스페이스를 선택합니다. 이는 이벤트가 여정의 첫 번째 단계로 배치되는 경우에만 필요합니다.

   ![](../assets/segment7.png)

페이로드에는 조건 및 작업에서 사용할 수 있는 다음 컨텍스트 정보가 포함됩니다.

* 동작(시작, 종료)
* 자격 타임스탬프
* 세그먼트 id

다음에 오는 조건 또는 작업에서 표현식 편집기를 사용할 때 **[!UICONTROL Segment qualification]** 활동에 대해 다음에 대한 액세스 권한이 있습니다. **[!UICONTROL SegmentQualification]** 노드. 다음 중 하나를 선택할 수 있습니다. **[!UICONTROL Last qualification time]** 및 **[!UICONTROL status]** (시작 또는 종료).

다음을 참조하십시오 [조건 활동](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

세그먼트 자격 이벤트를 포함하는 새 여정은 게시한 후 10분 후에 작동합니다. 이 시간 간격은 전용 서비스의 캐시 새로 고침 간격에 해당합니다. 따라서 이 여정을 사용하기 전에 10분 정도 기다려야 합니다.

## 모범 사례 {#best-practices-segments}

다음 **[!UICONTROL Segment Qualification]** 활동을 통해 Adobe Experience Platform 세그먼트에서 자격을 얻거나 자격을 잃은 개인 여정을 즉시 입력할 수 있습니다.

이 정보는 수신 속도가 빠르다. 측정된 속도는 초당 수신된 10,000개의 이벤트의 속도를 보여준다. 그 결과, 가장 높은 수준의 출입이 발생할 수 있는 상황, 이러한 입구를 피하는 방법 및 이러한 입구를 위한 여정을 준비하는 방법을 이해해야 합니다.

### 세그먼트 일괄 처리{#batch-speed-segment-qualification}

배치 세그먼트에 대한 세그먼트 자격을 사용할 때 일일 계산 시 가장 높은 시작 시간이 발생합니다. 피크의 크기는 매일 세그먼트에 들어가는(또는 나가는) 개인들의 수에 의존할 것이다.

또한 배치 세그먼트를 새로 만들어 여정에서 즉시 사용하는 경우 첫 번째 계산 배치로 인해 매우 많은 개인이 여정에 들어갈 수 있습니다.

### 스트리밍된 세그먼트{#streamed-speed-segment-qualification}

스트리밍된 세그먼트에 대한 세그먼트 자격을 사용할 때, 세그먼트에 대한 지속적인 평가로 인해 큰 출입구 정점이 발생할 위험이 적다. 세그먼트 정의가 많은 수의 고객이 동시에 자격을 얻도록 만드는 경우에도 최고점이 있을 수 있습니다.

스트리밍 세분화에 대한 자세한 내용은 다음을 참조하십시오. [페이지](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### 오버로드를 방지하는 방법{#overloads-speed-segment-qualification}

다음은 여정에서 활용하는 시스템(데이터 소스, 사용자 지정 작업, Adobe Campaign Standard 작업)을 오버로드할 수 없도록 하는 몇 가지 모범 사례입니다.

에서 를 사용하지 마십시오. **[!UICONTROL Segment Qualification]** 활동: 작성 후 즉시 일괄 처리 세그먼트입니다. 첫 번째 계산 피크가 나타나지 않습니다. 계산된 적이 없는 세그먼트를 사용하려는 경우 여정 캔버스에 노란색 경고가 표시됩니다.

![](../assets/segment-error.png)

여정에서 사용되는 데이터 소스 및 작업에 대한 최대 가용량 규칙을 적용하여 오버로드를 방지합니다(이 참조). [섹션](../api/capping.md)). 최대 가용량 규칙에는 재시도가 없습니다. 다시 시도해야 하는 경우 상자를 선택하여 여정에서 대체 경로를 사용해야 합니다 **[!UICONTROL Add an alternative path in case of a timeout or an error]** 조건 또는 작업에서 을 참조하십시오.

프로덕션 여정에서 세그먼트를 사용하기 전에 항상 먼저 매일 이 세그먼트에 적합한 개인의 양을 평가하십시오. 이렇게 하려면 다음을 확인할 수 있습니다. **[!UICONTROL Segments]** Adobe Experience Platform 섹션을 참조하고 오른쪽에 있는 그래프를 살펴보십시오.

![](../assets/segment-overload.png)
