---
title: 작업
description: 작업 구성 방법 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---


# 작업 {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="작업"
>abstract="여기서 메시지를 전송할 시스템에 대한 연결을 정의합니다. 그러면 여기서 정의한 작업을 경로 왼쪽 팔레트의 [작업] 범주에서 사용할 수 있습니다. "

작업은 푸시 알림, 이메일, SMS 또는 회사에서 사용하는 기타 디지털 참여 방법 등의 개인화된 실시간 경험을 고객에게 제공하는 데 사용되는 연결입니다.

사용자 지정 작업에서는 메시지나 API 호출을 전송할 서드파티 시스템의 연결을 구성할 수 있습니다. JSON 형식 페이로드를 사용하여 REST API를 통해 호출할 수 있는 모든 공급자의 어떤 서비스로든 작업을 구성할 수 있습니다.

작업은 경로 왼쪽 팔레트의 **[!UICONTROL Action]** 범주에서 사용 가능합니다([](../building-journeys/about-action-activities.md) 참조).

>[!NOTE]
>
>사용자 지정 작업은 항상 **기술 사용자**&#x200B;가 구성해야 합니다.

**작업** 목록에서 c 키를 누르면 새 경로, 작업, 데이터 소스 또는 이벤트를 만들 수 있습니다. [!DNL Journey Orchestration]의 바로 가기에 대한 자세한 내용은 [](../about/user-interface.md#section_ksq_zr1_ffb)을 참조하십시오.

작업 목록을 확인하거나 새 작업을 구성하려면 상단 메뉴에서 **[!UICONTROL Actions]**&#x200B;을 클릭합니다. 그러면 작업 목록이 표시됩니다. 인터페이스에 대한 자세한 내용은 [](../about/user-interface.md)를 참조하십시오.

![](../assets/custom1.png)

Adobe Campaign Standard가 설치되어 있다면 Adobe Campaign Standard의 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림 및 SMS 전송을 위한 기본 작업을 구성해야 합니다. [](../action/working-with-adobe-campaign.md)을 참조하십시오.

Epsilon, Facebook, Adobe.io, Firebase 등의 서드파티 시스템을 사용하여 메시지를 보내는 경우에는 사용자 지정 작업을 추가하고 구성해야 합니다. [](../action/about-custom-action-configuration.md)을 참조하십시오.

[!DNL Journey Orchestration]용 작업을 구성하여 경로에서 사용하는 방법과 관련된 자세한 내용을 확인하려면 이 [비디오 튜토리얼](https://docs.adobe.com/content/help/ko-KR/journey-orchestration-learn/tutorials/configure-actions.html)을 시청하십시오.
