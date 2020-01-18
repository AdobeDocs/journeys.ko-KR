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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# 시간대 관리 {#timezone_management}

시간대 정의는 다음 활동에서 사용할 수 있습니다.

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

경로 시작 이벤트에 네임스페이스가 있는 경우, 해당 여정이 데이터 플랫폼의 실시간 고객 프로필 서비스에 도달할 수 있음을 의미하며, 시간대는 여정에서 이동하는 개인의 프로필에 지정된 시간대로 미리 정의됩니다. 개인의 프로필에 시간대가 포함되어 있지 않으면 인스턴스의 시간대가 사용됩니다. 관리자에게 문의하여 인스턴스 시간대를 알 수 있습니다.

![](../assets/journey73.png)

표준 시간대를 수정할 수도 있습니다. 사전 정의된 시간대를 지우고 드롭다운 목록에서 시간대를 선택합니다. 고정 시간대를 사용하는 경우, 여행 중인 모든 사용자에 대해 동일하게 적용됩니다.

![](../assets/journey72.png)

마지막으로, 시간대는 단계에 들어가는 각 사용자에 대해 동적일 수 있습니다. 이 경우 표현식 편집기를 사용하여 시스템에서 이 정보를 얻을 위치를 선택합니다(이벤트 또는 데이터 소스에서 가져올 수 있음). 을 [](../expression/expressionadvanced.md)참조하십시오.


경로의 시작 날짜와 종료 날짜는 특정 시간대로 연결할 수 없습니다. 인스턴스의 표준 시간대와 자동으로 연결됩니다.
