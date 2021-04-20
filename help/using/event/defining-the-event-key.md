---
product: adobe campaign
solution: Journey Orchestration
title: 이벤트 키 정의
description: 이벤트 키 정의 방법 알아보기
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---


# 이벤트 키 정의 {#concept_ond_hqt_52b}

키는 이벤트 페이로드 데이터의 필드나 필드 조합이 되어 시스템에서 이벤트에 연결된 사람을 식별할 수 있도록 합니다. 키는 Experience Cloud ID, CRM ID 또는 이메일 주소와 같은 것일 수 있습니다.

실시간 고객 프로필 데이터베이스에 저장된 데이터를 활용하려면 [실시간 고객 프로필 서비스](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html)에서 프로필 ID로 정의한 정보를 이벤트 키로 선택해야 합니다.

그러면 시스템에서 이벤트와 개인 프로필 간의 조정을 수행할 수 있습니다. 기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드가 미리 채워집니다. ID가 정의되지 않은 경우 _identityMap > id_&#x200B;를 기본 키로 선택합니다. 그런 다음 네임스페이스를 선택해야 합니다. 그러면 _identityMap > id_&#x200B;를 사용하여 **[!UICONTROL Namespace]** 필드 아래에 키가 미리 채워집니다.

필드를 선택하면 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)

CRM ID 또는 이메일 주소와 같은 다른 키를 사용해야 하는 경우 수동으로 추가해야 합니다.

1. **[!UICONTROL Key]** 필드 안이나 연필 아이콘을 클릭합니다.

   ![](../assets/journey16.png)

1. 페이로드 필드 목록에서 키로 선택한 필드를 선택합니다. 고급 표현식 편집기로 전환하여 보다 복잡한 키를 만들 수도 있습니다(예: 이벤트의 두 필드 연결). 아래 섹션을 참조하십시오.

   ![](../assets/journey20.png)

이벤트가 수신되면 시스템에서 해당 이벤트와 관련된 사람을 식별할 수 있도록 키 값을 허용합니다. 네임스페이스와 연결된 경우([이 페이지](../event/selecting-the-namespace.md) 참조), 키를 사용하여 Adobe Experience Platform에서 쿼리를 수행할 수 있습니다. [이 페이지](../building-journeys/about-orchestration-activities.md)를 참조하십시오.
키는 또한 여정에 있는지 확인하는 데 사용됩니다. 사실, 한 사람은 같은 여정에서 두 곳에 있을 수 없다. 따라서 동일한 여정의 다른 위치에 있는 키(예: 키 CRMID=3224)를 허용하지 않습니다.

추가 조작을 수행하려면 고급 표현식 함수(**[!UICONTROL Advanced mode]**)에 액세스할 수도 있습니다. 이러한 함수를 사용하면 필드의 일부(예: 첫 번째 문자 10개)만 고려하여 형식 변경, 필드 연결 수행 등 특정 쿼리를 수행하는 데 사용되는 값을 조작할 수 있습니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.
