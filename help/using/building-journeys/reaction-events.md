---
product: adobe campaign
title: 반응 이벤트
description: 반응 이벤트에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---

# 반응 이벤트 {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._



팔레트에서 사용할 수 있는 여러 이벤트 활동 중에서 기본 제공 **[!UICONTROL Reactions]** 이벤트를 찾을 수 있습니다. 이 활동을 사용하면 동일한 여정 내에서 이메일, SMS 또는 푸시 활동으로 보낸 메시지와 관련된 추적 데이터에 반응할 수 있습니다. 이 정보는 Adobe Campaign Standard의 트랜잭션 메시지에서 가져온 것입니다. Adobe Experience Platform과 공유되는 즉시 이 정보를 실시간으로 캡처합니다. 푸시 알림의 경우 클릭, 전송 또는 실패한 메시지에 반응할 수 있습니다. SMS 메시지의 경우, 전송 또는 실패한 메시지에 반응할 수 있습니다. 이메일의 경우 클릭, 전송, 열림 또는 실패한 메시지에 반응할 수 있습니다.

메시지에 대한 반응이 없을 때 이 메커니즘을 사용하여 작업을 수행할 수도 있습니다. 이렇게 하려면 반응 활동과 평행한 두 번째 경로를 만들고 대기 활동을 추가합니다. 대기 활동에 정의된 기간 동안 반응이 없으면 두 번째 경로가 선택됩니다. 예를 들어 후속 메시지를 보내도록 선택할 수 있습니다.

이전에 이메일, 푸시 또는 SMS 활동이 있는 경우에만 캔버스에서 반응 활동을 사용할 수 있습니다.

[작업 활동 정보](../building-journeys/about-action-activities.md)를 참조하세요.

![](../assets/journey45.png)

반응 이벤트를 구성하는 여러 단계는 다음과 같습니다.

1. 반응에 **[!UICONTROL Label]**&#x200B;을(를) 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 드롭다운 목록에서 반응할 작업 활동을 선택합니다. 경로의 이전 단계에 배치된 모든 작업 활동을 선택할 수 있습니다.
1. 선택한 작업(이메일, SMS 또는 푸시 알림)에 따라 반응할 항목을 선택합니다.
1. 이벤트 시간 제한(40초~30일)과 시간 제한 경로를 정의할 수 있습니다. 이렇게 하면 정의된 기간 내에 반응하지 않은 개인에 대한 두 번째 경로가 만들어집니다. 반응 이벤트를 사용하는 여정을 테스트할 때 테스트 모드 **[!UICONTROL Wait time]**&#x200B;의 기본값과 최소값은 40초입니다. [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.

>[!NOTE]
>
>반응 이벤트는 Adobe Campaign Standard을 AWS 또는 Azure 서버에 배포하든 관계없이 에서 작동합니다.
>
>반응 이벤트는 다른 여정에서 발생하는 이메일, SMS 또는 푸시 작업을 추적할 수 없습니다.
>
>반응 이벤트는 &quot;추적됨&quot; 유형의 링크에서 클릭을 추적합니다([페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls) 참조). 구독 취소 및 미러 페이지 링크는 고려되지 않습니다.

>[!IMPORTANT]
>
>Gmail과 같은 이메일 클라이언트는 이미지 차단을 허용합니다. 이메일에 포함된 0픽셀 이미지를 사용하여 이메일 열기가 추적됩니다. 이미지가 차단되면 이메일 열림은 고려되지 않습니다.
