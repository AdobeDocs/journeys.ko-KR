---
product: adobe campaign
title: 네임스페이스 선택
description: 네임스페이스 선택 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 네임스페이스 선택 {#concept_ckb_3qt_52b}

네임스페이스를 통해 이벤트와 연계된 사용자를 식별하는 데 사용되는 키 유형을 정의할 수 있습니다. 구성은 선택 사항입니다. 에서 제공되는 추가 정보를 여정에서 검색하려면 필요합니다. [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko). 사용자 지정 데이터 소스를 통해 서드파티 시스템에서 오는 데이터만 사용하는 경우에는 네임스페이스 정의가 필요하지 않습니다.

미리 정의된 네임스페이스 서비스 중 하나를 사용하거나 ID 네임스페이스 서비스를 사용하여 새 프로필을 만들 수 있습니다. 다음을 참조하십시오. [페이지](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ko-KR).

기본 ID가 있는 스키마를 선택하는 경우 **[!UICONTROL Key]** 및 **[!UICONTROL Namespace]** 필드는 미리 채워져 있습니다. ID가 정의되지 않은 경우 다음을 선택합니다 _identityMap > id_ 기본 키로 사용됩니다. 그런 다음 네임스페이스를 선택해야 하며 키는 미리 채워집니다( **[!UICONTROL Namespace]** field) 사용 _identityMap > id_.

필드를 선택하면 기본 ID 필드에 태그가 지정됩니다.

![](../assets/primary-identity.png)


드롭다운 목록에서 네임스페이스를 선택합니다.

![](../assets/journey17.png)

네임스페이스는 여정 당 하나만 허용됩니다. 동일한 여정에서 여러 이벤트를 사용하는 경우 동일한 네임스페이스를 사용해야 합니다. [이 페이지](../building-journeys/journey.md)를 참조하십시오.
