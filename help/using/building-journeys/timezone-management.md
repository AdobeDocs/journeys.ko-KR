---
title: 시간대 관리
description: 시간대 관리에 대한 자세한 내용
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 2%

---



# 시간대 관리 {#timezone_management}

여정의 [속성에서](../building-journeys/changing-properties.md) 시간대를 정의할 수 있습니다.

속성에 액세스하려면 화면 오른쪽 상단에 있는 연필 아이콘을 클릭합니다.

이 시간대는 다음과 같은 시간 요소를 포함하는 여정의 모든 활동에 사용됩니다.

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

시간대를 선택하거나 사용자 프로필에 정의된 시간대를 사용하도록 선택할 수 있습니다.

## 고정 표준 시간대 정의 {#fixed-timezone}

표준 시간대를 설정할 수도 있습니다. 사전 정의된 시간대를 지우고 드롭다운 목록에서 하나를 선택합니다. 고정 시간대를 사용하는 경우, 여행을 시작하는 모든 사람에게 동일하게 적용됩니다.

이렇게 하려면 **[!UICONTROL Properties]**&#x200B;시간대를 선택합니다.

![](../assets/journey73.png)

## 프로필을 사용하여 여정 시간대 정의 {#timezone-from-profiles}

여정의 시작 이벤트에 네임스페이스가 있는 경우, 해당 여정이 Adobe Experience Platform의 실시간 고객 프로필 서비스에 도달할 수 있음을 의미하며, 시간대는 여정에서 이동하는 개인의 프로필에 지정된 시간대로 미리 정의됩니다.

Adobe Experience Platform 프로필에 시간대가 정의된 경우 경로 중에 검색할 수 있습니다.

개인의 프로필에 시간대가 포함되어 있지 않으면 검색된 시간대가 표준 시간대 필드에 정의된 시간대가 됩니다.

그렇게 하려면, in **[!UICONTROL Properties]**&#x200B;을 확인하십시오 **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## 표현식에서 시간대 사용 {#timezone-in-expressions}

경로의 시작 날짜와 종료 날짜는 특정 시간대로 연결할 수 없습니다. 인스턴스의 표준 시간대와 자동으로 연결됩니다.
