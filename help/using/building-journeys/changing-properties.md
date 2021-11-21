---
product: adobe campaign
title: 속성 변경
description: 속성을 변경하는 방법에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# 속성 변경 {#concept_prq_wqt_52b}

오른쪽 상단에 있는 연필 아이콘을 클릭하여 여정 속성에 액세스합니다.

여정 이름을 변경하고, 설명을 추가하고, 다시 시작하고, 시작 날짜와 종료 날짜를 선택하고, **[!UICONTROL Timeout and error]** 관리하는 경우 지속 시간.

라이브 여정의 경우 이 화면에는 여정을 게시한 사용자의 게시 날짜와 이름이 표시됩니다.

다음 **기술 세부 정보 복사** 지원 팀이 문제를 해결하는 데 사용할 수 있는 여정에 대한 기술 정보를 복사할 수 있습니다. 다음 정보가 복사됩니다. JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## 입구{#entrance}

기본적으로 새 여정은 다시 입력할 수 있습니다. &quot;일회성&quot; 여정에 대한 옵션의 선택을 취소할 수 있습니다. 예를 들어, 사용자가 상점에 들어올 때 일회성 선물을 제공하려는 경우입니다. 이러한 경우 고객이 여정을 다시 입력하고 오퍼를 다시 받을 수 없도록 합니다.

여정이 &quot;종료&quot;되면 상태가 됩니다 **[!UICONTROL Closed (no entrance)]**. 여정은 새 개인이 여정에 들어가는 것을 중지합니다. 여정에 이미 있는 사람은 여정을 정상적으로 완료합니다.

기본 글로벌 시간 초과 30일 이후에는 여정이 **완료됨** 상태. 다음 보기 [섹션](#global_timeout).

## 여정 활동의 시간 제한 및 오류 {#timeout_and_error}

작업 또는 조건 활동을 편집할 때 오류 또는 시간 제한 시 대체 경로를 정의할 수 있습니다. 서드파티 시스템을 심문하는 활동이 여정 속성에 정의된 시간 초과 기간을 초과하는 경우(**[!UICONTROL Timeout and  error]** 필드), 잠재적인 대체 작업을 수행하도록 두 번째 경로가 선택됩니다.

허용된 값은 1초에서 30초 사이입니다.

매우 짧은 을 정의하는 것이 좋습니다 **[!UICONTROL Timeout and error]** 여정이 시간에 민감한 경우 값(예: 몇 초 이상 작업을 지연할 수 없으므로 여기에 응답합니다. 여정에 시간이 덜 민감한 경우, 더 긴 값을 사용하여 유효한 응답을 보내기 위해 라는 시스템에 더 많은 시간을 줄 수 있습니다.

[!DNL Journey Orchestration] 또한 글로벌 시간 초과를 사용합니다. 자세한 내용은 [다음 섹션](#global_timeout).

## 글로벌 여정 시간 초과 {#global_timeout}

추가 [timeout](#timeout_and_error) 여정 활동에 사용되며 인터페이스에 표시되지 않으며 변경할 수 없는 글로벌 여정 시간 초과도 있습니다. 이 시간 제한은 여정이 입력한 후 30일 후에 개인 진행 상태를 중지합니다. 이는 개인의 여정이 30일 이상 지속될 수 없음을 의미합니다. 30일 시간 제한 기간 후 개인의 데이터가 삭제됩니다. 시간 제한 기간이 끝날 때 여전히 여정에 흐르는 개인은 중지되며 보고 오류로 고려됩니다.

>[!NOTE]
>
>[!DNL Journey Orchestration] 은 개인 정보 보호 옵트아웃, 액세스 또는 삭제 요청에 직접 대응하지 않습니다. 그러나 글로벌 시간 제한은 개인이 여정에서 30일 이상 머무르지 않도록 합니다.

30일 여정 제한 시간 때문에 여정 재입력이 허용되지 않는 경우 30일 이상, 재입력 차단 기능이 있는지 확인할 수 없습니다. 실제로 입국한 지 30일이 지난 뒤 여정에 들어온 사람에 대한 모든 정보를 제거하므로 30일 이상 전에 입국한 사람을 알 수 없습니다.

## 표준 시간대 및 프로필 시간대 {#timezone}

시간대는 여정 수준에서 정의됩니다.

고정 시간대를 입력하거나 Adobe Experience Platform 프로필을 사용하여 여정 시간대를 정의할 수 있습니다.

시간대 관리에 대한 자세한 내용은 [이 페이지](../building-journeys/timezone-management.md).
