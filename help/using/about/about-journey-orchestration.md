---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration
description: Journey Orchestration에 대해 자세히 알아보십시오
feature: 여정
role: 비즈니스 전문가
level: 초급
translation-type: ht
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

이벤트나 데이터 소스에 저장된 상황별 데이터를 활용하여 실시간 오케스트레이션 사용 사례를 작성할 수 있습니다.

[!DNL Journey Orchestration]은(는) Adobe Experience Platform과 통합된 애플리케이션 서비스입니다. 

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration]에서는 이벤트, Adobe Experience Platform의 정보 또는 서드파티 API 서비스의 데이터를 활용한 실시간 오케스트레이션이 가능합니다. 서드파티 시스템을 사용하여 메시지를 보내는 경우에는 사용자 지정 작업을 구성할 수 있습니다. Adobe Campaign Standard가 설치되어 있다면 Adobe Campaign Standard의 [트랜잭션 메시지 기능](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)을 사용하여 이메일, 푸시 알림 및 SMS를 전송할 수 있습니다.

이벤트 구성 탭에서 **기술 사용자**&#x200B;는 여정에서 예상되는 이벤트를 구성합니다. 수신되는 이벤트 데이터는 Adobe Experience 데이터 모델(XDM)에 따라 표준화됩니다. 이벤트는 인증된 이벤트와 인증되지 않은 이벤트(예: Adobe Mobile SDK 이벤트)를 위한 수집 API 스트리밍에서 옵니다.

데이터 소스 구성 탭에서 **기술 사용자**&#x200B;는 다음을 구성합니다.

* 조건 작성 및 개인화를 위해 여정 디자이너에서 Adobe Experience Platform으로부터 노출되는 다양한 필드.
* 여정 디자이너에서 활용하는 추가적인 사용자 지정 데이터 소스. 사용자 지정 데이터 소스는 API를 통해 이루어지는 [!DNL Journey Orchestration] 및 서드파티 시스템 또는 서비스의 연결입니다. 충성도 시스템과 같은 서드파티 시스템을 연결할 수 있습니다. 예를 들어 날씨 API와 같은 서드파티 서비스가 있을 수 있습니다.

여정 디자이너를 통해 **비즈니스 사용자**&#x200B;는 손쉽게 항목 이벤트를 끌어서 놓고, 조건을 추가하고, 수행할 작업을 지정할 수 있습니다.

그리고 다음을 기준으로 조건을 만듭니다.

* 시간
* 이벤트 페이로드에서 오는 데이터
* 데이터 소스에서 오는 정보: 실시간 고객 프로필 데이터 소스 또는 사용자 지정 데이터 소스

분할된 조건을 사용하여 여정에 있는 사람들을 다른 방향으로 보낼 수 있습니다.

그런 다음에 작업 활동을 사용하여 서드파티 시스템을 통해 메시지를 보낼 수 있습니다. Adobe Campaign Standard가 있는 경우에는 개인화된 실시간 SMS, 푸시 알림 또는 이메일을 보내십시오.

[!DNL Journey Orchestration]은 여러 단계로 진행되므로 고급 시나리오를 만들 수 있습니다. 예를 들어 첫 번째 이벤트 및 작업 후에 다른 이벤트를 드래그할 수 있습니다. 그런 다음에 두 번째 작업을 추가하고, 잠시 기다리기 위한 대기 활동을 배치하고, 서로 다른 두 여정에 사람들을 푸시한 후에 각기 다른 메시지를 보내기 위한 분할 조건을 추가할 수 있습니다.

>[!NOTE]
>
>이 설명서는 제품의 최근 변경 사항을 반영하여 자주 업데이트됩니다. 그러나 실제 제품 인터페이스와 약간 다른 스크린샷도 있습니다.
