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
source-wordcount: '154'
ht-degree: 5%

---

# 조건에서 세그먼트 사용 {#using-a-segment}

이 섹션에서는 여정 조건에서 세그먼트를 사용하는 방법을 설명합니다. 여정에서 **[!UICONTROL Segment qualification]** 이벤트를 사용하는 방법에 대해 알아보려면 이 [섹션](../building-journeys/segment-qualification-events.md)을 참조하세요.

여정 조건에서 세그먼트를 사용하려면 다음 단계를 따르십시오.

1. 여정을 열고 **[!UICONTROL Condition]** 활동을 삭제하고 **데이터 Source 조건**을 선택하세요.
   ![](../assets/journey47.png)

1. 필요한 각 추가 경로에 대해 **[!UICONTROL Add a path]**&#x200B;을(를) 클릭합니다. 각 경로에 대해 **[!UICONTROL Expression]** 필드를 클릭합니다.

   ![](../assets/segment3.png)

1. 왼쪽에서 **[!UICONTROL Segments]** 노드를 펼칩니다. 조건에 사용할 세그먼트를 끌어서 놓습니다. 세그먼트의 조건은 기본적으로 true입니다.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >**실현됨** 및 **기존** 세그먼트 참여 상태가 있는 개인만 세그먼트의 구성원으로 간주됩니다. 세그먼트를 평가하는 방법에 대한 자세한 내용은 [세그먼테이션 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)를 참조하세요.

여정 조건 및 단순 표현식 편집기 사용 방법에 대한 자세한 내용은 [조건 활동](../building-journeys/condition-activity.md#about_condition)을 참조하세요.
