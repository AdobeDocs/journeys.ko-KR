---
product: adobe campaign
title: 시간대 관리
description: 표준 시간대 관리에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 8%

---

# 시간대 관리 {#timezone_management}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._



여정의 [속성](../building-journeys/changing-properties.md)에서 시간대를 정의할 수 있습니다.

속성에 액세스하려면 화면 오른쪽 상단의 연필 아이콘을 클릭합니다.

이 시간대는 다음과 같은 시간 요소를 포함하는 여정의 모든 활동에 사용됩니다.

* [시간 조건](../building-journeys/condition-activity.md#time_condition)
* [날짜 조건](../building-journeys/condition-activity.md#date_condition)
* [사용자 지정 대기](../building-journeys/wait-activity.md#custom)

시간대를 선택하거나 사용자 프로필에 정의된 시간대를 사용하도록 선택할 수 있습니다.

>[!NOTE]
>
>프로필 시간대는 **환경 설정 세부 정보** 필드 그룹에 있는 **표준 시간대** 필드에서 작동합니다.

## 고정 시간대 정의 {#fixed-timezone}

시간대를 고정할 수도 있습니다. 사전 정의된 시간대를 지우고 드롭다운 목록에서 시간대를 선택합니다. 고정된 시간대를 사용하는 경우 여정에 들어오는 모든 개인에 대해 동일합니다.

이렇게 하려면 **[!UICONTROL Properties]**&#x200B;에서 표준 시간대를 선택하십시오.

![](../assets/journey72.png)

## 프로필을 사용하여 여정 시간대 정의 {#timezone-from-profiles}

여정의 시작 이벤트에 네임스페이스가 있는 경우, 즉 여정이 Adobe Experience Platform의 실시간 고객 프로필 서비스에 도달할 수 있다면 프로필 수준에서 정의된 시간대를 사용할 수 있습니다. 이렇게 하려면 **속성**&#x200B;에서 **대기 및 조건에 프로필 시간대 사용**&#x200B;을 확인하세요. 이 옵션은 기본적으로 선택되어 있지 않습니다.

프로필에 대해 시간대가 정의된 경우 여정은 해당 시간대를 검색하고 이를 사용하게 됩니다. 시간대가 정의되어 있지 않으면 사용된 시간대는 시간대 필드에 정의된 시간대가 됩니다.

![](../assets/journey73.png)

## 표현식에서 시간대 사용 {#timezone-in-expressions}

여정의 시작 및 종료 날짜를 특정 시간대에 연결할 수 없습니다. 인스턴스의 시간대에 자동으로 연결됩니다.
