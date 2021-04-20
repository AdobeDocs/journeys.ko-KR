---
product: adobe campaign
solution: Journey Orchestration
title: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마 정보 '
description: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마에 대해 알아보기 '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---



# [!DNL Journey Orchestration] 이벤트에 대한 ExperienceEvent 스키마 정보

[!DNL Journey Orchestration] 이벤트는 스트리밍 습제를 통해 Adobe Experience Platform으로 전송되는 XDM 경험 이벤트입니다.

이와 같이 [!DNL Journey Orchestration]에 대한 이벤트 설정을 위한 중요한 전제 조건은 Adobe Experience Platform의 경험 데이터 모델(또는 XDM) 및 XDM 경험 이벤트 스키마를 구성하는 방법과 XDM 형식 데이터를 Adobe Experience Platform으로 스트리밍하는 방법에 익숙하다는 것입니다.

## [!DNL Journey Orchestration] 이벤트에 대한 스키마 요구 사항

[!DNL Journey Orchestration]에 대한 이벤트를 설정하는 첫 번째 단계는 이벤트를 나타내기 위해 정의된 XDM 스키마와 Adobe Experience Platform에서 이벤트의 인스턴스를 기록하도록 만들어진 데이터 세트를 갖는 것입니다. 이벤트에 대한 데이터 세트가 반드시 필요한 것은 아니지만 이벤트를 특정 데이터 세트에 보내면 나중에 참조하고 분석할 수 있도록 사용자의 이벤트 내역을 유지할 수 있으므로 항상 좋은 생각입니다. 이벤트에 적합한 스키마와 데이터 세트가 아직 없는 경우에는 Adobe Experience Platform 웹 인터페이스에서 두 작업을 모두 수행할 수 있습니다.

![](../assets/schema1.png)

[!DNL Journey Orchestration] 이벤트에 사용할 모든 XDM 스키마는 다음 요구 사항을 충족해야 합니다.

* 스키마는 XDM ExperienceEvent 클래스여야 합니다.

   ![](../assets/schema2.png)

* 시스템에서 생성된 이벤트의 경우 스키마에는 Orchestration eventID 믹신이 포함되어야 합니다. [!DNL Journey Orchestration] 이 필드를 사용하여 여정에 사용된 이벤트를 식별합니다.

   ![](../assets/schema3.png)

* 이벤트의 제목을 식별할 수 있는 ID 필드를 선언합니다. ID를 지정하지 않으면 ID 맵을 사용할 수 있습니다. 권장되지 않습니다.

   ![](../assets/schema4.png)

* 이 데이터를 여정에서 나중에 조회할 수 있도록 하려면 프로필의 스키마 및 데이터 집합을 표시하십시오.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 사용자 정보, 이벤트가 생성된 장치, 위치 또는 이벤트와 관련된 기타 의미 있는 상황 등, 이벤트에 포함할 다른 컨텍스트 데이터를 캡처하려면 데이터 필드를 자유롭게 입력하십시오.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)