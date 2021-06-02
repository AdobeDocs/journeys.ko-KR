---
product: adobe campaign
title: 네임스페이스 선택
description: 네임스페이스를 선택하는 방법 알아보기
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 12%

---

# 네임스페이스 선택 {#concept_ckb_3qt_52b}

네임스페이스를 사용하면 이벤트와 연결된 사람을 식별하는 데 사용되는 키 유형을 정의할 수 있습니다. 구성은 선택 사항입니다. 여정에서 [실시간 고객 프로필](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html)에서 오는 추가 정보를 검색하려면 필요합니다. 사용자 지정 데이터 소스를 통해 타사 시스템에서 가져온 데이터만 사용하는 경우에는 네임스페이스 정의가 필요하지 않습니다.

미리 정의된 네임스페이스 중 하나를 사용하거나 ID 네임스페이스 서비스를 사용하여 새 ID를 만들 수 있습니다. 이 [page](https://docs.adobe.com/content/help/ko-KR/experience-platform/identity/home.html)을 참조하십시오.

기본 ID가 있는 스키마를 선택하면 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드가 미리 채워집니다. 정의된 ID가 없으면 _identityMap > id_&#x200B;를 기본 키로 선택합니다. 그런 다음 네임스페이스를 선택해야 합니다. 그러면 _identityMap > id_&#x200B;를 사용하여 키가 미리 채워져 **[!UICONTROL Namespace]** 필드 아래에 있습니다.

필드를 선택할 때 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)


드롭다운 목록에서 네임스페이스를 선택합니다.

![](../assets/journey17.png)

여정 당 하나의 네임스페이스만 허용됩니다. 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다. [이 페이지](../building-journeys/journey.md)를 참조하십시오.
