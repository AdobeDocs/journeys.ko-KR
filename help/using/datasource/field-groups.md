---
product: adobe campaign
title: 필드 그룹
description: 필드 그룹에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# 필드 그룹 {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


필드 그룹은 데이터 소스에서 검색하고 여정에서 사용할 수 있는 필드 세트입니다.

## 필드 그룹 정의 {#section_dsz_kjd_fjb}

각 데이터 소스에 대해 여러 필드 그룹을 정의할 수 있습니다.

예를 들어, 전화 번호, 이메일, 이름 및 프로필 주소로 필드 그룹을 만들 수 있습니다. 그런 다음 여정에서 이 데이터를 사용하여 조건을 만들 수 있습니다. 예를 들어 프로필의 전화 번호가 비어 있지 않은 경우에만 SMS를 보내도록 결정할 수 있습니다. 비어 있는 경우 이메일을 보낼 수 있습니다.

기본 이름이 자동으로 추가되더라도 필드 그룹의 이름을 지정하는 것이 좋습니다. 필드 그룹 이름이 [!DNL Journey Orchestration]의 다른 사용자에게 표시됩니다. 필드 그룹에 관련 이름을 지정하는 것이 좋습니다.

데이터 소스 필드가 여정에서 사용될 때 시스템은 해당 필드 그룹에 대해 정의된 모든 필드를 검색합니다. 따라서 여정에 필요한 필드만 선택하는 것이 좋습니다. 이렇게 하면 여정에서 요청 지연이 줄어들어 성능이 향상됩니다. 나중에 필드 그룹에 더 많은 필드를 쉽게 추가할 수 있습니다.

필드 그룹을 사용하는 여정 수가 **[!UICONTROL Used in]** 필드에 표시됩니다. **[!UICONTROL View journeys]** 단추를 클릭하여 이 필드 그룹을 사용하는 여정 목록을 표시할 수 있습니다.

>[!NOTE]
>
>필드 그룹에 필드가 없으면 표현식 편집기에 표시되지 않습니다.

![](../assets/journey3bis.png)

## 필드 그룹 라이프사이클 {#section_abk_njd_fjb}

초안 또는 라이브 여정에서 사용되지 않는 필드 그룹의 필드를 추가하거나 제거할 수 있습니다.

하나 이상의 초안 또는 라이브 여정에 사용된 필드 그룹에서는 필드를 추가할 수 있지만 제거할 수 없습니다. 이렇게 하면 여정 손상을 방지할 수 있습니다.

하나 이상의 여정에 사용된 필드 그룹에서 필드를 삭제하려면 다음 단계를 따르십시오. &quot;필드 그룹 A&quot;라는 필드 그룹의 예를 사용하겠습니다.

1. 필드 그룹 목록에서 &quot;필드 그룹 A&quot; 위에 커서를 놓고 오른쪽에 있는 **[!UICONTROL Duplicate]** 아이콘을 클릭합니다. 복제된 필드 그룹의 이름을 &quot;필드 그룹 B&quot;로 지정합니다.
1. 필드 그룹 B에서 더 이상 원하지 않는 필드를 제거합니다.
1. &quot;필드 그룹 A&quot;에서 이 필드 그룹이 사용되는 위치를 확인합니다. 이 정보는 **[!UICONTROL Used in]** 필드에 표시됩니다.
1. 필드 그룹 A를 사용하는 모든 여정을 엽니다.
1. 이러한 각 여정의 새 버전을 만듭니다. &quot;필드 그룹 A&quot;를 사용하여 모든 활동을 편집하고 &quot;필드 그룹 B&quot;를 선택합니다.
1. 필드 그룹 A를 사용하는 이전 버전의 여정을 중지합니다. 그러면 &quot;필드 그룹 A&quot;를 사용하는 여정이 없어야 합니다.
1. 필드 그룹 A는 더 이상 사용되지 않으므로 제거합니다.
