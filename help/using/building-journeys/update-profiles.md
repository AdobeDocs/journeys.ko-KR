---
product: adobe campaign
title: 프로필 업데이트
description: 프로필 업데이트
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# 프로필 업데이트 {#update-profile}


>[!CAUTION]
>
>**Adobe Systems Journey Optimizer** 특가를 찾고 계십니까? Journey Optimizer 설명서를 보려면 여기를[&#128279;](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"} 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._


작업 **[!UICONTROL Update profile]** 활동을 통해 기존 Adobe Experience Platform 프로필을 이벤트, 데이터 소스 또는 특정 값을 사용하여 가져온 정보로 업데이트할 수 있습니다.

## 중요 정보

* 프로필 **&#x200B;**&#x200B;업데이트 작업은 네임스페이스가 있는 이벤트로 시작하는 여정에서만 사용할 수 있습니다.
* 이 작업은 기존 필드만 업데이트하고 새 프로필 필드를 만들지는 않습니다.
* 프로필&#x200B;**업데이트 작업을 사용하여**&#x200B;구매와 같은 경험 이벤트를 생성할 수 없습니다.
* 다른 작업과 좋아요 오류 또는 시간 초과가 발생할 경우 대체 경로를 정의할 수 있으며 두 작업을 병렬로 배치할 수 없습니다.
* Platform(으)로 전송된 업데이트 요청은 빠르지만 즉시/1초 이내에 전송되지는 않습니다. 일반적으로 몇 초가 걸리지만 때로는 보장 없이 더 오래 걸릴 수 있습니다. 따라서 예를 들어 작업이 바로 앞에 배치된 프로필 업데이트 작업에 의해 업데이트된 &quot;필드 1&quot;을 사용하는 경우 작업에서 &quot;필드 1&quot;이 업데이트될 것으로 기대해서는 안 됩니다.
* 테스트 모드에서는 프로필 업데이트가 시뮬레이션되지 않습니다. 업데이트는 테스트 프로필에서 수행됩니다.
* 프로필 **업데이트** 활동은 열거로 정의된 XDM 필드를 지원하지 않습니다.

## 프로필 업데이트 사용

1. 이벤트로 시작하여 여정을 디자인합니다. 이 [섹션](../building-journeys/journey.md)을 참조하세요.

1. **팔레트의 Action** 섹션에서 Update profile **활동을 캔버스에 놓**&#x200B;습니다.

   ![](../assets/profileupdate0.png)

1. 목록에서 스키마를 선택합니다.

1. **필드를** 클릭하여 업데이트할 필드를 선택합니다. 하나의 필드만 선택할 수 있습니다.

   ![](../assets/profileupdate2.png)

1. 목록에서 데이터 세트 하나를 선택합니다.

   >[!NOTE]
   >
   >프로필 **&#x200B;**&#x200B;업데이트 작업은 프로필 데이터를 실시간으로 업데이트하지만 데이터 세트를 업데이트하지는 않습니다. 프로필이 데이터 세트와 관련된 레코드이므로 데이터 세트 선택이 필요합니다.

1. **값** 필드를 클릭하여 사용할 값을 정의합니다.

   * 단순 표현식 편집기 를 사용하여 데이터 소스 또는 수신 이벤트에서 필드를 선택할 수 있습니다.

     ![](../assets/profileupdate4.png)

   * 특정 값을 정의하거나 고급 기능을 활용하려면 고급 모드를&#x200B;**클릭하십시오**.

     ![](../assets/profileupdate3.png)

이제 업데이트 프로필&#x200B;**이**&#x200B;구성되었습니다.

![](../assets/profileupdate1.png)
