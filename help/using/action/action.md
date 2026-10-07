---
product: adobe campaign
title: 작업 정보
description: 액션 구성 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 95%
---
# 작업 정보 {#about_actions}


>[!CAUTION]
>
>**Adobe Journey Optimizer를 찾고 계신가요**? [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하여 Journey Optimizer 설명서를 확인할 수 있습니다.
>
>
>_이 설명서는 Journey Optimizer로 대체된 이전 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="작업 정보"
>abstract="여기서 메시지를 전송할 시스템에 대한 연결을 정의합니다. 그러면 여기서 정의한 작업을 여정 왼쪽 팔레트의 [작업] 카테고리에서 사용할 수 있습니다. "

액션은 푸시 알림, 이메일, SMS 또는 회사에서 사용하는 기타 디지털 참여 방법 등의 개인화된 실시간 경험을 고객에게 제공하는 데 사용되는 연결입니다.

사용자 정의 액션에서는 메시지나 API 호출을 전송할 서드파티 시스템의 연결을 구성할 수 있습니다. JSON 형식 페이로드를 사용하여 REST API를 통해 호출할 수 있는 모든 공급자의 어떤 서비스로든 작업을 구성할 수 있습니다.

작업은 여정 왼쪽 팔레트의 **[!UICONTROL Action]** 범주에서 사용 가능합니다. [이 페이지](../building-journeys/about-action-activities.md)를 참조하십시오.

>[!NOTE]
>
>사용자 지정 작업은 항상 **기술 사용자**&#x200B;가 구성해야 합니다.

**작업** 목록에서 c 키를 누르면 새 여정, 작업, 데이터 소스 또는 이벤트를 만들 수 있습니다. [!DNL Journey Orchestration]의 바로 가기에 대한 자세한 내용은 [이 섹션](../about/user-interface.md#section_ksq_zr1_ffb)을 참조하십시오.

작업 목록을 확인하거나 새 작업을 구성하려면 상단 메뉴에서 **[!UICONTROL Actions]**&#x200B;을 클릭합니다. 그러면 작업 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [이 페이지](../about/user-interface.md)를 참조하십시오.

![](../assets/custom1.png)

Adobe Campaign Standard가 설치되어 있다면 Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS 전송을 위한 기본 액션을 구성해야 합니다. [이 페이지](../action/working-with-adobe-campaign.md)를 참조하십시오.

Adobe Campaign v7 또는 v8이 있는 경우 요청 시 통합을 사용할 수 있습니다. [이 페이지](../action/acc-action.md)를 참조하십시오.

Epsilon, Facebook, Adobe.io, Firebase 등의 서드파티 시스템을 사용하여 메시지를 보내는 경우에는 사용자 지정 액션을 추가하고 구성해야 합니다. [이 페이지](../action/about-custom-action-configuration.md)를 참조하십시오.

