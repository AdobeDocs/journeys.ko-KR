---
product: adobe campaign
title: 세그먼트 선별 이벤트
description: 세그먼트 자격 이벤트에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 1%

---

# 세그먼트 선별 이벤트 {#segment-qualification}


>[!CAUTION]
>
>**Adobe Systems Journey Optimizer** 특가를 찾고 계십니까? Journey Optimizer 설명서를 보려면 여기를[&#128279;](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home) 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._



## 세그먼트 자격 행사 정보{#about-segment-qualification}

이 활동을 통해 여정에서 Adobe Experience Platform 세그먼트에서 프로필의 입장 및 퇴장을 수신하여 개인이 여정에 들어가거나 앞으로 이동하도록 할 수 있습니다. 세그먼트 생성에 대한 자세한 내용은 이 [섹션을](../segment/about-segments.md) 참조하십시오.

&quot;실버 고객&quot; 세그먼트 가 있다고 가정해 보겠습니다. 이 활동을 통해 모든 신규 실버 고객이 여정을 입력하고 일련의 개인화된 메시지를 보내도록 할 수 있습니다.

이러한 유형의 이벤트는 여정의 첫 번째 단계 또는 나중에 배치할 수 있습니다.

>[!IMPORTANT]
>
>Adobe Experience Platform 세그먼트는 하루에 한 번(**일괄 처리** 세그먼트) 또는 실시간으로(**스트리밍됨** 세그먼트(Adobe Experience Platform의 High Frequency Audiences 옵션 사용) 계산됩니다.
>
>선택한 세그먼트가 스트리밍되는 경우 이 세그먼트에 속하는 개인은 잠재적으로 실시간으로 여정에 입장할 수 있습니다. 세그먼트가 배치인 경우 이 세그먼트에 대해 새로 자격이 있는 사용자는 세그먼트 계산이 Adobe Experience Platform에서 실행될 때 잠재적으로 여정에 들어갈 수 있습니다.


1. 카테고리를 **[!UICONTROL Events]** 펼치고 활동을 캔버스에 놓 **[!UICONTROL Segment qualification]** 습니다.

   ![](../assets/segment5.png)

1. 활동에 A **[!UICONTROL Label]** 를 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.

1. **[!UICONTROL Segment]** 필드를 클릭하고 활용 할 세그먼트를 선택하십시오.

   >[!NOTE]
   >
   >목록에 표시되는 열을 사용자 지정하고 정렬할 수 있습니다.

   ![](../assets/segment6.png)

   세그먼트 추가되면 버튼 을 **[!UICONTROL Copy]** 사용하여 이름과 ID를 복사할 수 있습니다.

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 필드에서 **[!UICONTROL Behaviour]** 세그먼트 시작, 출구 또는 둘 다를 수신할지 여부를 선택합니다.

   >[!NOTE]
   >
   >**[!UICONTROL Enter]** 는 **[!UICONTROL Exit]** Adobe Experience Platform의 실현됨&#x200B;**및**&#x200B;종료됨&#x200B;**세그먼트 참여 상태에 해당**&#x200B;합니다. 세그먼트 평가 방법에 대한 자세한 내용은 [세그멘테이션 서비스 설명서를](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results) 참조하십시오.

1. 네임스페이스를 선택합니다. 이벤트가 여정의 첫 번째 단계로 배치된 경우에만 필요합니다.

   ![](../assets/segment7.png)

페이로드에는 조건 및 작업에서 사용할 수 있는 다음 컨텍스트 정보가 포함되어 있습니다.

* 행동(입구, 출구)
* 자격의 타임스탬프
* 세그먼트 ID입니다

활동 뒤에 **[!UICONTROL Segment qualification]** 오는 조건이나 작업에서 표현식 편집기를 사용하는 경우 노드에 **[!UICONTROL SegmentQualification]** 액세스할 수 있습니다. 와 **[!UICONTROL status]** (시작 또는 종료) 중에서 **[!UICONTROL Last qualification time]** 선택할 수 있습니다.

조건 활동을[&#128279;](../building-journeys/condition-activity.md#about_condition) 참조하십시오.

![](../assets/segment8.png)

세그먼트 자격 이벤트를 포함하는 새로운 여정은 게시한 지 10분 후에 작동합니다. 이 시간 간격은 전용 서비스의 캐시 새로 고침 간격에 해당합니다. 따라서 이 여정을 사용하기 전에 10분 정도 기다려야 합니다.

## 모범 사례 {#best-practices-segments}

**[!UICONTROL Segment Qualification]** 활동을 사용하면 Adobe Experience Platform 세그먼트에서 자격을 얻거나 자격을 박탈당한 개인 여정을 즉시 입력할 수 있습니다.

이 정보는 수신 속도가 빠르다. 측정된 속도는 초당 수신된 10,000개의 이벤트의 속도를 보여준다. 결과적으로, 입구의 피크가 어떻게 발생할 수 있는지, 어떻게 피해야 하는지, 그리고 이를 위해 여행을 준비하는 방법을 이해해야 합니다.

### 세그먼트 일괄 처리{#batch-speed-segment-qualification}

배치 세그먼트에 대해 세그먼트 제한을 사용하는 경우 일별 계산 시 진입 피크가 발생한다는 점에 유의하십시오. 피크의 크기는 매일 세그먼트 진입(또는 퇴장)하는 개인의 수에 따라 달라집니다.

또한 배치 세그먼트 가 새로 생성되어 여정에서 즉시 사용되는 경우 첫 번째 계산 배치로 인해 매우 많은 수의 개인이 여정에 들어갈 수 있습니다.

### 스트리밍된 세그먼트{#streamed-speed-segment-qualification}

스트리밍된 세그먼트에 대해 세그먼트 자격을 사용하면 세그먼트의 지속적인 평가로 인해 입구/출구의 큰 피크가 발생할 위험이 줄어듭니다. 그러나 세그먼트 정의로 인해 많은 수의 고객이 동시에 자격을 갖추게 된다면 피크도 있을 수 있습니다.

스트리밍 세분화 방법에 대한 자세한 내용은 이 [페이지 페이지를 참조하십시오](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### 과부하를 피하는 방법{#overloads-speed-segment-qualification}

다음은 여정에서 활용되는 시스템(데이터 소스, 사용자 지정 작업, Adobe Campaign Standard 작업)의 과부하를 방지하는 데 도움이 되는 몇 가지 모범 사례입니다.

활동에서 **[!UICONTROL Segment Qualification]** 배치 세그먼트 작성 직후에 사용하지 마십시오. 첫 번째 계산 피크를 피합니다. 계산되지 않은 세그먼트 를 사용하려는 경우 여정 캔버스에 노란색 경고가 표시됩니다.

![](../assets/segment-error.png)

과부하를 방지하기 위해 여정에 사용되는 데이터 소스 및 작업에 대한 상한 규칙 을 적용합니다(이 [섹션](../api/capping.md) 참조). 최대 가용량 규칙 에는 재시도가 없습니다. 다시 시도해야 하는 경우 조건 또는 작업에서 확인란을 **[!UICONTROL Add an alternative path in case of a timeout or an error]** 선택하여 여정에서 대체 경로를 사용해야 합니다.

프로덕션 여정에서 세그먼트를 사용하기 전에 항상 먼저 매일 이 세그먼트에 적합한 개인의 양을 평가하십시오. 이렇게 하려면 Adobe Experience Platform 섹션에서 섹션을 확인하고 **[!UICONTROL Segments]** 오른쪽의 그래프를 볼 수 있습니다.

![](../assets/segment-overload.png)
