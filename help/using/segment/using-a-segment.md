---
product: adobe campaign
title: 조건에서 세그먼트 사용
description: 세그먼트 사용 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# 조건에서 세그먼트 사용 {#using-a-segment}

이 섹션에서는 여정 조건에서 세그먼트를 사용하는 방법을 설명합니다. 를 사용하는 방법을 알아보려면 **[!UICONTROL Segment qualification]** 여정의 이벤트입니다. 다음을 참조하십시오. [섹션](../building-journeys/segment-qualification-events.md).

여정 조건에서 세그먼트를 사용하려면 다음 단계를 따르십시오.

1. 여정을 열고 **[!UICONTROL Condition]** 활동 및 선택 **데이터 소스 조건**.
   ![](../assets/journey47.png)

1. 클릭 **[!UICONTROL Add a path]** 각 추가 경로에 대해 필요합니다. 각 경로에 대해 **[!UICONTROL Expression]** 필드.

   ![](../assets/segment3.png)

1. 왼쪽에서 펼칩니다. **[!UICONTROL Segments]** 노드. 조건에 사용할 세그먼트를 끌어서 놓습니다. 세그먼트의 조건은 기본적으로 true입니다.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >다음을 보유한 개인만 **실현됨** 및 **기존 항목** 세그먼트 기여도 상태는 세그먼트의 멤버로 간주됩니다. 세그먼트를 평가하는 방법에 대한 자세한 내용은 [세그먼테이션 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

여정 조건 및 단순 표현식 편집기 사용 방법에 대한 자세한 내용은 다음을 참조하십시오. [조건 활동](../building-journeys/condition-activity.md#about_condition).
