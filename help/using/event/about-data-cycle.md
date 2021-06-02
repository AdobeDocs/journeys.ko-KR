---
product: adobe campaign
title: 이벤트 데이터 주기
description: 이벤트 데이터 주기에 대해 알아보기
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 79%

---

# 데이터 주기 {#section_r1f_xqt_pgb}

POST API 호출인 이벤트는 이벤트는 스트리밍 수집 API를 통해 Adobe Experience Platform으로 전송됩니다. 트랜잭션 메시징 API를 통해 전송되는 이벤트의 URL 대상은 &quot;인렛&quot;입니다. 이벤트의 페이로드는 XDM 형식을 따릅니다.

페이로드의 헤더에는 스트리밍 수집 API의 작동에 필요한 정보가, 이벤트 ID와 페이로드 본분의 일부분에는 [!DNL Journey Orchestration]의 작동에 필요한 정보가 포함되어 있습니다. 그리고 본문에는 경로에 사용할 정보(예: 쇼핑을 중단한 카트의 금액)가 포함되어 있습니다. 스트리밍 수집에는 인증/미인증의 두 가지 모드가 있습니다. 스트리밍 수집 API에 대한 자세한 내용은 [이 링크](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/api/getting-started.html)를 참조하십시오.

스트리밍 수집 API를 통과하여 대상에 도착한 이벤트는 파이프라인이라는 내부 서비스로 이동한 후 Adobe Experience Platform으로 이동합니다. 이벤트 스키마에 실시간 고객 프로필 서비스 플래그가 설정되어 있고, 역시 실시간 고객 프로필 태그가 설정된 데이터 세트 ID도 포함되어 있으면 이벤트는 실시간 고객 프로필 서비스로 이동합니다.

시스템 생성 이벤트의 경우 파이프라인은 [!DNL Journey Orchestration] eventID([!DNL Journey Orchestration]에서 제공하며 이벤트 페이로드에 포함됨)가 들어 있는 페이로드가 포함된 이벤트를 필터링합니다. 아래 이벤트 만들기 프로세스를 참조하십시오. 규칙 기반 이벤트의 경우, 시스템은 eventID 조건을 사용하여 이벤트를 식별합니다. [!DNL Journey Orchestration]에서 이러한 이벤트를 수신하면 해당하는 경로가 트리거됩니다.
