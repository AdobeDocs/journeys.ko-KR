---
title: 반응 이벤트
description: 반응 이벤트에 대한 자세한 내용
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
source-git-commit: 2b44cd9db7732c5e272b69e2583a5f81b4580d11
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# 반응 이벤트 {#section_dhx_gss_dgb}

팔레트에서 사용할 수 있는 다양한 이벤트 활동 중에서 내장 **[!UICONTROL Reactions]** 이벤트를 찾을 수 있습니다. 이 활동을 통해 이메일, SMS 또는 푸시 활동과 함께 전송된 메시지와 관련된 추적 데이터에 응답할 수 있습니다. 이 정보는 Adobe Campaign Standard의 트랜잭션 메시징에서 옵니다. 이 정보는 Adobe Experience Platform과 공유되는 즉시 실시간으로 캡처됩니다. 푸시 알림의 경우, 클릭, 전송 또는 실패한 메시지에 응답할 수 있습니다. SMS 메시지의 경우 전송되거나 실패한 메시지에 응답할 수 있습니다. 이메일의 경우, 클릭된 메시지, 전송, 열려 있거나 실패한 메시지에 응답할 수 있습니다.

메시지에 반응이 없을 때 이 메커니즘을 사용하여 작업을 수행할 수도 있습니다. 이렇게 하려면 반응 활동과 평행하게 두 번째 경로를 만들고 대기 활동을 추가합니다. 대기 활동에 정의된 기간 동안 반응이 없으면 두 번째 경로가 선택됩니다. 예를 들어 후속 메시지를 보내도록 선택할 수 있습니다.

이전에 이메일, 푸시 또는 SMS 활동이 있는 경우에만 캔버스에서 반응 활동을 사용할 수 있습니다.

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

다음은 반응 이벤트를 구성하는 다른 단계입니다.

1. 반응 **[!UICONTROL Label]** 을 더하세요. 데이터 소스에 이벤트에 설명을 추가합니다.
1. 드롭다운 목록에서 응답할 작업 활동을 선택합니다. 경로의 이전 단계에 배치된 작업 활동을 선택할 수 있습니다.
1. 선택한 작업(이메일, SMS 또는 푸시 알림)에 따라 반응할 동작을 선택합니다.
1. 조건을 선택 단계로 정의할 수 있습니다. 예를 들어 이메일 동작 후 응답 이벤트가 있는 두 개의 경로를 만들어 VIP 고객의 클릭만 추적하고, 여성 사용자의 클릭을 추적하는 반응 이벤트가 있는 경로를 선택할 수 있습니다.

>[!NOTE]
>
>반응 이벤트는 Adobe Campaign Standard에서 작동하며 AWS 또는 Azure 서버에 배포되어 있습니다.
>
>반응 이벤트는 다른 여정에서 발생하는 이메일, SMS 또는 푸시 동작을 추적할 수 없습니다.
>
>반응 이벤트는 &quot;추적된&quot; 유형의 링크에 대한 클릭을 추적합니다(이 [페이지](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)참조). 구독 취소 및 미러 페이지 링크는 고려되지 않습니다.

>[!IMPORTANT]
>
>Gmail과 같은 이메일 클라이언트는 이미지 차단을 허용합니다. 이메일에 포함된 0 픽셀 이미지를 사용하여 연 이메일을 추적합니다. 이미지가 차단된 경우 이메일 열기 기능을 고려하지 않습니다.
