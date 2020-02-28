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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# 시간대 관리 {#timezone_management}

여정의 [속성에서](../building-journeys/changing-properties.md) 시간대를 정의할 수 있습니다.

속성에 액세스하려면 화면 오른쪽 상단에 있는 연필 아이콘을 클릭합니다.

이 시간대는 다음과 같은 시간 요소를 포함하는 경로의 모든 활동에 사용됩니다.

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

시간대를 선택하거나 사용자 프로필에 정의된 시간대를 사용하도록 선택할 수 있습니다.

## 고정 표준 시간대 정의 {#fixed-timezone}

표준 시간대를 수정할 수도 있습니다. 사전 정의된 시간대를 지우고 드롭다운 목록에서 시간대를 선택합니다. 고정 시간대를 사용하는 경우, 여행 중인 모든 사용자에 대해 동일하게 적용됩니다.

이렇게 하려면 에서 **[!UICONTROL Properties]**&#x200B;시간대를 선택합니다.

![](../assets/journey73.png)

## 프로파일을 사용하여 여정 시간대 정의 {#timezone-from-profiles}

경로 시작 이벤트에 네임스페이스가 있는 경우, 해당 여정이 데이터 플랫폼의 실시간 고객 프로필 서비스에 도달할 수 있음을 의미하며, 시간대는 여정에서 이동하는 개인의 프로필에 지정된 시간대로 미리 정의됩니다.

Experience Platform 프로필에 표준 시간대가 정의된 경우 여정에서 검색할 수 있습니다.

개인의 프로필에 시간대가 포함되어 있지 않으면 검색된 시간대가 시간대 필드에 정의된 시간대가 됩니다.

그렇게 하려면 **[!UICONTROL Properties]**&#x200B;체크 인 **[!UICONTROL Use Profile timezone in timers and conditions]**&#x200B;하십시오.

![](../assets/journey72.png)

## 표현식에서 시간대 사용 {#timezone-in-expressions}

시간대는 고급 표현식 편집기를 사용하여 표현식을 작성하는 데 사용됩니다. 이 경우 표현식 편집기를 사용하여 시스템에서 이 정보를 가져올 위치를 선택합니다. 을 [](../expression/expressionadvanced.md)참조하십시오.

경로의 시작 날짜와 종료 날짜는 특정 시간대로 연결할 수 없습니다. 인스턴스의 표준 시간대와 자동으로 연결됩니다.
