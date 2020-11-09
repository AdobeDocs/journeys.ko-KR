---
title: 속성 변경
description: 속성 변경 방법 살펴보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---



# 속성 변경 {#concept_prq_wqt_52b}

오른쪽 상단의 연필 아이콘을 클릭하여 경로 속성에 액세스합니다.

경로 이름을 변경하고, 설명을 추가하고, 다시 입장하고, 시작 날짜와 종료 날짜를 선택하고, 관리자인 경우 기간을 정의할 수 **[!UICONTROL Timeout and error]** 있습니다.

![](../assets/journey32.png)

## 입구{#entrance}

기본적으로 새로운 여정은 재입구를 가능하게 한다. 예를 들어 한 사람이 상점에 들어올 때 일회용 선물을 제공하려는 경우 &quot;한 샷&quot; 여정에 대한 옵션의 선택을 취소할 수 있습니다. 이러한 경우 고객이 해당 여정에 다시 액세스하여 제안을 다시 받을 수 있는 경우는 원하지 않습니다.

여행이 &quot;종료&quot;될 때, 그것은 상태가 될 것입니다 **[!UICONTROL Closed (no entrance)]**. 이 여행은 새로운 사람들이 여행을 가는 것을 멈출 것이다. 이미 여행 중인 사람은 정상적으로 여행을 마칠 것이다.

## 경로 활동 시간 초과 및 오류 {#timeout_and_error}

작업 또는 조건 활동을 편집할 때 오류 또는 시간 초과에 대한 대체 경로를 정의할 수 있습니다. 타사 시스템을 심문하는 활동이 경로의 속성(필드)에 정의된 시간 초과 기간을 초과하는 경우 두 번째 경로가 선택되어 잠재적인 대체 작업을 수행합니다&#x200B;**[!UICONTROL Timeout and  error]** .

허가된 값은 1초에서 30초 사이입니다.

여정이 시간에 민감한 경우 매우 짧은 **[!UICONTROL Timeout and error]** 값을 정의하는 것이 좋습니다(예:동작을 몇 초 이상 지연할 수 없기 때문에(사람의 실시간 위치에 응답) 여정이 덜 민감한 경우 더 긴 값을 사용하여 올바른 응답을 보내기 위해 호출된 시스템에 더 많은 시간을 줄 수 있습니다.

[!DNL Journey Orchestration] 전역 시간 초과도 사용합니다. 다음 [섹션을 참조하십시오](#global_timeout).

## 전역 경로 제한 시간 {#global_timeout}

경로 활동에 사용되는 [시간 제한](#timeout_and_error) 외에, 인터페이스에 표시되지 않고 변경할 수 없는 글로벌 경로 시간 초과도 있습니다. 이 시간 초과는 사용자가 참여한 후 30일 동안 경로의 진행률을 중단합니다. 이는 개인의 여정이 30일 이상 지속될 수 없다는 것을 의미한다. 30일 제한 시간이 지나면 개인 데이터가 삭제됩니다. 시간 초과 기간이 끝날 때 여전히 여행 중에 이동하는 개인은 중지되며, 보고 오류를 고려할 것입니다.

>[!NOTE]
>
>[!DNL Journey Orchestration] 개인정보 보호 옵트아웃, 액세스 또는 삭제 요청에 직접 응답하지 않습니다. 그러나 글로벌 시간 초과는 개인 사용자가 어떠한 여행에서도 30일 이상 머무르지 못하도록 합니다.

30일 여정 시간이 초과돼 다시 입장할 수 없는 상황이라 30일 이상 재진입 차단 장치가 필요한지 알 수 없다. 실제로 입국 후 30일 만에 모든 여행 정보를 지워버리기 때문에 30일 전에 들어온 사람도 알 수 없다.

## 표준 시간대 및 프로필 표준 시간대 {#timezone}

시간대는 여정 수준에서 정의됩니다.

고정 시간대를 입력하거나 Adobe Experience Platform 프로필을 사용하여 여정 시간대를 정의할 수 있습니다.

시간대 관리에 대한 자세한 내용은 [이 페이지를 참조하십시오](../building-journeys/timezone-management.md).
