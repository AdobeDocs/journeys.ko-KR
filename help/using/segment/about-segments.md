---
product: adobe campaign
title: Adobe Experience Platform 세그먼트
description: Adobe Experience Platform 세그먼트를 구성하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Adobe Experience Platform 세그먼트 {#about-segments}

를 사용 중이라면 [Adobe Experience Platform 세그멘테이션 서비스](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) 세그먼트를 만들려면 다음을 수행하십시오. [!DNL Journey Orchestration]. 전용 이벤트 활동 덕분에 Adobe Experience Platform 세그먼트 출입구 및 종료에 따라 개인이 여정에 들어오거나 앞으로 이동하도록 할 수 있습니다. 또한 단순 또는 고급 표현식 편집기를 사용하여 여정에서 복잡한 조건을 작성할 수도 있습니다.

&quot;실버 고객&quot; 세그먼트가 있다고 가정해 보겠습니다. 이 활동을 사용하면 모든 신규 실버 고객이 여정을 입력하고 일련의 개인화된 메시지를 보내게 할 수 있습니다. 이 세그먼트를 기반으로 조건을 쉽게 작성할 수도 있습니다.

가능성은 다음과 같습니다 [!DNL Journey Orchestration] 세그먼트를 사용하여 을 제공합니다.

* Adobe Experience Platform 세그먼트 목록에 액세스합니다. 자세한 내용은 [세그먼트 만들기](../segment/creating-a-segment.md).
* 에서 바로 세그먼트 만들기 [!DNL Journey Orchestration] 세분화 서비스를 사용하여 만드는 것과 동일한 방식으로 만듭니다. 자세한 내용은 [세그먼트 만들기](../segment/creating-a-segment.md).
* 단순 또는 고급 표현식 편집기를 사용하여 여정의 조건에서 세그먼트를 활용합니다. 자세한 내용은 [조건에서 세그먼트 사용](../segment/using-a-segment.md).
* 추가 **[!UICONTROL Segment qualification]** 이벤트를 여정에 전달하여 Adobe Experience Platform 세그먼트의 프로필의 처음과 끝에서 의견을 수렴합니다. 자세한 내용은 [이벤트 활동](../building-journeys/segment-qualification-events.md).

## Journey Orchestration 평가 방법 {#evaluation-method-in-journey-orchestration}

Journey Orchestration에서 대상은 다음 평가 방법 중 하나를 사용하여 세그먼트 정의에서 생성됩니다.

* 스트리밍 세그먼테이션 - 새로운 데이터가 시스템으로 이동하는 동안 세그먼트의 대상 목록이 실시간으로 최신 상태로 유지됩니다.
* 배치 세그먼테이션 - 세그먼트의 대상 목록이 지난 시간에 도착한 데이터를 기반으로 시간별로 업데이트됩니다.

배치 세그먼테이션과 스트리밍 세그먼테이션 간의 결정은 세그먼트 규칙 평가의 복잡성과 비용을 기반으로, 각 세그먼트 정의에 대해 시스템에서 수행됩니다.

에서 각 세그먼트에 대한 평가 방법을 볼 수 있습니다 **[!UICONTROL Evaluation method]** 세그먼트 목록의 열입니다.

세그먼트를 처음 정의하면 자격이 되면 프로필이 대상에 추가됩니다.

이전 데이터에서 대상자를 다시 채우는 데는 최대 24시간이 걸릴 수 있습니다. 대상이 다시 채워지면 대상이 계속 최신 상태로 유지되며 항상 타깃팅할 준비가 됩니다.