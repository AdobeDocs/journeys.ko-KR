---
product: adobe campaign
solution: Journey Orchestration
title: 반응 이벤트
description: 반응 이벤트에 대해 알아보기
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 4b30ac80a2dfb5b0675a88ecb5abf81e57c64097
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---


# 반응 이벤트 {#section_dhx_gss_dgb}

팔레트에서 사용할 수 있는 다양한 이벤트 활동 중에서 내장 **[!UICONTROL Reactions]** 이벤트를 찾을 수 있습니다. 이 활동을 통해 동일한 여정 내에서 이메일, SMS 또는 푸시 활동과 함께 전송된 메시지와 관련된 추적 데이터에 응답할 수 있습니다. 이 정보는 Adobe Campaign Standard의 트랜잭션 메시징에서 가져옵니다. Adobe Experience Platform과 공유되는 즉시 이 정보를 실시간으로 캡처합니다. 푸시 알림의 경우, 클릭, 전송 또는 실패한 메시지에 응답할 수 있습니다. SMS 메시지의 경우 전송되거나 실패한 메시지에 응답할 수 있습니다. 이메일의 경우, 클릭된 메시지, 전송, 열림 또는 실패한 메시지에 응답할 수 있습니다.

메시지에 반응이 없을 때 이 메커니즘을 사용하여 작업을 수행할 수도 있습니다. 이렇게 하려면 반응 활동과 평행한 두 번째 경로를 만들고 대기 활동을 추가합니다. 대기 활동에 정의된 기간 동안 반응이 없으면 두 번째 경로가 선택됩니다. 예를 들어 후속 메시지를 보내도록 선택할 수 있습니다.

이전에 이메일, 푸시 또는 SMS 활동이 있는 경우에만 캔버스에서 반응 활동을 사용할 수 있습니다.

[작업 활동 정보](../building-journeys/about-action-activities.md)를 참조하십시오.

![](../assets/journey45.png)

다음은 반응 이벤트를 구성하는 다른 단계입니다.

1. 응답에 **[!UICONTROL Label]**&#x200B;을(를) 추가합니다. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 드롭다운 목록에서 반응할 작업 활동을 선택합니다. 경로의 이전 단계에 배치된 작업 활동을 선택할 수 있습니다.
1. 선택한 작업(이메일, SMS 또는 푸시 알림)에 따라 반응할 동작을 선택합니다.
1. 이벤트 시간 초과(40초~30일 사이)와 시간 초과 경로를 정의할 수 있습니다. 그러면 정의된 기간 내에 응답하지 않은 개별 사용자에 대한 두 번째 경로가 만들어집니다. 반응 이벤트를 사용하는 여정을 테스트할 때 테스트 모드 **[!UICONTROL Wait time]** 기본값 및 최소 값은 40초입니다. [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.

>[!NOTE]
>
>반응 이벤트는 AWS 또는 Azure 서버에 배포되어 있는지 여부와 관계없이 Adobe Campaign Standard에서 작동합니다.
>
>반응 이벤트는 다른 여정에서 발생하는 이메일, SMS 또는 푸시 동작을 추적할 수 없습니다.
>
>반응 이벤트는 &quot;추적됨&quot; 유형의 링크에 대한 클릭을 추적합니다(이 [페이지](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls) 참조). 구독 취소 및 미러 페이지 링크는 고려되지 않습니다.

>[!IMPORTANT]
>
>Gmail과 같은 이메일 클라이언트는 이미지 차단을 허용합니다. 이메일에 포함된 0 픽셀 이미지를 사용하여 이메일 열기를 추적합니다. 이미지가 차단된 경우 이메일 열기 계산에 포함되지 않습니다.
