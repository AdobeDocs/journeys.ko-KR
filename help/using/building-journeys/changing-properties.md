---
product: adobe campaign
title: 속성 변경
description: 속성을 변경하는 방법에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 2%

---

# 속성 변경 {#concept_prq_wqt_52b}



>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


오른쪽 상단의 연필 아이콘을 클릭하여 여정 속성에 액세스합니다.

관리자의 경우 여정 이름을 변경하고, 설명을 추가하고, 다시 입력할 수 있도록 허용하고, 시작 및 종료 날짜를 선택하고 **[!UICONTROL Timeout and error]** 기간을 정의할 수 있습니다.

라이브 여정의 경우 이 화면에는 게시 날짜와 여정을 게시한 사용자의 이름이 표시됩니다.

**기술 세부 정보 복사**&#x200B;를 통해 지원 팀이 문제를 해결하는 데 사용할 수 있는 여정에 대한 기술 정보를 복사할 수 있습니다. JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt 정보가 복사됩니다.

![](../assets/journey32.png)

## Entrance{#entrance}

기본적으로 새 여정은 재진입을 허용합니다. 예를 들어 한 사람이 상점에 들어갈 때 일회성 선물을 제공하려는 경우 &quot;한 방&quot; 여정에 대한 옵션을 선택 취소할 수 있습니다. 이 경우 고객이 여정에 다시 입장하여 오퍼를 다시 받을 수 없도록 해야 합니다.

여정이 &quot;종료&quot;되면 **[!UICONTROL Closed (no entrance)]** 상태가 됩니다. 여정은 새로운 개인이 여정에 들어오도록 하는 것을 중단합니다. 이미 여정에 있는 사람은 여정을 정상적으로 완료합니다.

기본 전역 시간 제한(30일)이 지나면 여정이 **완료됨** 상태로 전환됩니다. 이 [섹션](#global_timeout)을 참조하세요.

## 여정 활동의 시간 제한 및 오류 {#timeout_and_error}

작업 또는 조건 활동을 편집할 때 오류 또는 시간 초과가 발생하는 경우 대체 경로를 정의할 수 있습니다. 서드파티 시스템을 조사하는 활동 처리가 여정의 속성(**[!UICONTROL Timeout and  error]** 필드)에 정의된 시간 제한 기간을 초과하는 경우 잠재적인 대체 작업을 수행하도록 두 번째 경로가 선택됩니다.

승인된 값은 1초에서 30초 사이입니다.

여정이 시간에 민감한 경우(예: 사람의 실시간 위치에 반응하는 경우) 몇 초 이상 작업을 지연할 수 없으므로 매우 짧은 **[!UICONTROL Timeout and error]** 값을 정의하는 것이 좋습니다. 여정에서 시간에 덜 민감한 경우, 더 긴 값을 사용하여 유효한 응답을 보내기 위해 호출된 시스템에 더 많은 시간을 제공할 수 있습니다.

[!DNL Journey Orchestration]에서도 전역 시간 제한을 사용합니다. [다음 섹션](#global_timeout)을 참조하세요.

## 전역 여정 시간 제한 {#global_timeout}

여정 활동에 사용된 [timeout](#timeout_and_error) 외에 인터페이스에 표시되지 않고 변경할 수 없는 전역 여정 시간 초과도 있습니다. 이 시간 제한은 여정에 들어온 후 30일 후에 개인 사용자의 진행을 중지합니다. 이는 개인의 여정이 30일을 초과할 수 없음을 의미합니다. 30일 제한 시간이 지나면 개인의 데이터가 삭제됩니다. 시간 제한 기간이 끝날 때 여정에 계속 유입되는 개인은 중지되며, 보고에서 오류로 처리됩니다.

>[!NOTE]
>
>[!DNL Journey Orchestration]은(는) 개인 정보 옵트아웃, 액세스 또는 삭제 요청에 직접 반응하지 않습니다. 그러나 전역 시간 제한은 개인이 어떤 여정에서 30일 이상 머무르지 않도록 합니다.

30일 여정 시간 제한으로 인해 여정 재입력이 허용되지 않는 경우 재입력 차단이 30일 이상 작동하도록 할 수 없습니다. 실제로 여정에 입장한 후 30일이 지난 사람에 대한 정보를 모두 삭제하기 때문에 30일 이상 전에 입력한 사람을 알 수 없습니다.

## 시간대 및 프로필 시간대 {#timezone}

시간대는 여정 수준에서 정의됩니다.

고정 시간대를 입력하거나 Adobe Experience Platform 프로필을 사용하여 여정 시간대를 정의할 수 있습니다.

시간대 관리에 대한 자세한 내용은 [이 페이지](../building-journeys/timezone-management.md)를 참조하십시오.
