---
title: 시작
description: Journey Orchestration 시작
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---


# 시작{#concept_y4b_4qt_52b}

Journey Orchestration에는 각기 특정 작업을 수행하는 두 가지 유형의 사용자가 있습니다. 그중 하나는 **기술 사용자**&#x200B;이고 다른 하나는 **비즈니스 사용자**&#x200B;입니다. 제품 프로필과 권한을 통해 사용자 액세스를 관리합니다. 사용자 액세스를 구성하는 방법에 대해 알아보려면 [](../about/access-management.md)를 참조하십시오.

Journey Orchestration을 구성 및 사용하는 주요 단계는 다음과 같습니다.

1. **이벤트 구성**

   필요한 정보와 정보 처리 방법을 정의해야 합니다. 이 구성은 반드시 진행해야 하며, **기술 사용자**&#x200B;가 이 단계를 수행해야 합니다.

   자세한 내용은 [](../event/about-events.md)를 참조하십시오.

   ![](../assets/journey7.png)

1. **데이터 소스 구성**

   경로에 사용할 조건 등의 추가 정보를 검색하려면 시스템에 대한 연결을 정의해야 합니다. 기본 Experience Platform 데이터 소스도 프로비저닝 시에 구성됩니다. 경로 내 이벤트의 데이터만 활용하는 경우에는 이 단계를 수행할 필요가 없습니다. 이 단계가 필요한 경우에는 **기술 사용자**&#x200B;가 이 단계를 수행해야 합니다.

   자세한 내용은 [](../datasource/about-data-sources.md)를 참조하십시오.

   ![](../assets/journey22.png)

1. **작업 구성**

   서드파티 시스템을 사용하여 메시지를 전송하는 경우 Journey Orchestration과의 연결을 구성해야 합니다. [](../action/about-custom-action-configuration.md)을 참조하십시오.

   Adobe Campaign Standard를 사용하여 메시지를 전송하는 경우 기본 작업을 구성해야 합니다. [](../action/working-with-adobe-campaign.md)을 참조하십시오.

   이러한 단계는 **기술 사용자**&#x200B;가 수행해야 합니다.

   ![](../assets/custom2.png)

1. **경로 디자인**

   다양한 이벤트, 오케스트레이션 및 작업 활동을 조합하여 여러 단계로 구성된 크로스 채널 시나리오를 작성할 수 있습니다. 이 단계는 **비즈니스 사용자**&#x200B;가 수행해야 합니다.

   자세한 내용은 [](../building-journeys/journey.md)를 참조하십시오.

   ![](../assets/journeyuc2_24.png)

1. **경로 테스트 및 게시**

   경로를 만든 후에는 유효성을 검사하고 활성화해야 합니다. 이 단계는 **비즈니스 사용자**&#x200B;가 수행해야 합니다.

   자세한 내용은 [](../building-journeys/testing-the-journey.md) 및 [](../building-journeys/publishing-the-journey.md)를 참조하십시오.

   ![](../assets/journeyuc2_32bis.png)

1. **경로 모니터링**

   전용 보고 도구를 사용하여 경로의 효율성을 측정합니다. 이 단계는 **비즈니스 사용자**&#x200B;가 수행해야 합니다.

   자세한 내용은 [](../reporting/about-journey-reports.md)를 참조하십시오.

   ![](../assets/dynamic_report_journey_12.png)

