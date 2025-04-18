---
product: adobe campaign
title: 이벤트 키 정의
description: 이벤트 키를 정의하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# 이벤트 키 정의 {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


키는 필드이거나 필드 조합이 이벤트 페이로드 데이터의 일부이며, 이를 통해 시스템에서 이벤트와 관련된 사용자를 식별할 수 있습니다. 키는 예를 들어 Experience Cloud ID, CRM ID 또는 이메일 주소일 수 있습니다.

실시간 고객 프로필 데이터베이스에 저장된 데이터를 활용하려면 [실시간 고객 프로필 서비스](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko)에서 프로필 ID로 정의한 정보를 이벤트 키로 선택해야 합니다.

이 설정을 사용하면 시스템에서 이벤트와 개인 프로필 간의 조정을 수행할 수 있습니다. 기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드가 미리 채워집니다. ID가 정의되지 않은 경우 _identityMap > id_&#x200B;을(를) 기본 키로 선택합니다. 네임스페이스를 선택해야 하며 _identityMap > id_&#x200B;을(를) 사용하여 키가 미리 채워집니다(**[!UICONTROL Namespace]** 필드 아래).

필드를 선택하면 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)

CRM ID 또는 이메일 주소와 같은 다른 키를 사용해야 하는 경우 수동으로 추가해야 합니다.

1. **[!UICONTROL Key]** 필드 안이나 연필 아이콘을 클릭합니다.

   ![](../assets/journey16.png)

1. 페이로드 필드 목록에서 키로 선택한 필드를 선택합니다. 고급 표현식 편집기로 전환하여 더 복잡한 키(예: 이벤트의 두 필드 연결)를 만들 수도 있습니다. 이 섹션의 아래를 참조하십시오.

   ![](../assets/journey20.png)

이벤트가 수신되면, 키의 값은 시스템이 이벤트와 연관된 인물을 식별하도록 허용할 것이다. 네임스페이스와 연결되어([이 페이지](../event/selecting-the-namespace.md) 참조), 키를 사용하여 Adobe Experience Platform에서 쿼리를 수행할 수 있습니다. [이 페이지](../building-journeys/about-orchestration-activities.md)를 참조하세요.
또한 이 키는 개인이 여정 내에 있는지 확인하는 데도 사용됩니다. 실제로, 한 사람은 같은 여정에서 두 개의 다른 장소에 있을 수 없다. 따라서 시스템은 동일한 키(예: 키 CRMID=3224)가 동일한 여정의 다른 위치에 있는 것을 허용하지 않습니다.

추가 조작을 수행하려면 고급 식 함수(**[!UICONTROL Advanced mode]**)에 액세스할 수도 있습니다. 이러한 함수를 사용하면 필드의 일부(예: 첫 번째 문자 10개)만 고려하여 필드 연결을 수행하는 등 형식 변경과 같은 특정 쿼리를 수행하는 데 사용되는 값을 조작할 수 있습니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.
