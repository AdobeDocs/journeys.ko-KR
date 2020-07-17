---
title: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마 정보 '
description: 'Journey Orchestration 이벤트에 대한 ExperienceEvent 스키마 알아보기 '
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---



# 이벤트에 대한 ExperienceEvent 스키마 [!DNL Journey Orchestration] 정보

[!DNL Journey Orchestration] 이벤트는 스트리밍 습제를 통해 Adobe Experience Platform으로 전송되는 XDM 경험 이벤트입니다.

이와 같이, 이벤트 설정을 위한 중요한 전제 조건 [!DNL Journey Orchestration] 은 Adobe Experience Platform의 경험 데이터 모델(또는 XDM) 및 XDM 경험 이벤트 스키마를 구성하는 방법과 XDM 형식 데이터를 Adobe Experience Platform으로 스트리밍하는 방법에 익숙하다는 것입니다.

## 이벤트에 대한 스키마 요구 [!DNL Journey Orchestration] 사항

이벤트를 설정하는 첫 번째 단계 [!DNL Journey Orchestration] 는 이벤트를 나타내도록 정의된 XDM 스키마와 Adobe Experience Platform에서 이벤트 인스턴스를 기록하도록 만들어진 데이터 세트를 갖는 것입니다. 이벤트에 대한 데이터 세트가 반드시 필요한 것은 아니지만 특정 데이터 세트에 이벤트를 전송하면 나중에 참조하고 분석할 수 있도록 사용자의 이벤트 내역을 유지할 수 있으므로 항상 좋은 생각입니다. 이벤트에 적합한 스키마와 데이터 세트가 아직 없는 경우 Adobe Experience Platform 웹 인터페이스에서 두 작업을 모두 수행할 수 있습니다.

![](../assets/schema1.png)

이벤트에 사용될 모든 XDM 스키마는 다음 요구 사항을 [!DNL Journey Orchestration] 충족해야 합니다.

* 스키마는 XDM ExperienceEvent 클래스여야 합니다.

![](../assets/schema2.png)

* 스키마에는 오케스트레이션 eventID 믹신이 포함되어야 합니다. [!DNL Journey Orchestration] 이 필드를 사용하여 여정에 사용된 이벤트를 식별합니다.

![](../assets/schema3.png)

* 이벤트의 제목을 식별할 수 있는 ID 필드를 선언합니다. ID를 지정하지 않으면 ID 맵을 사용할 수 있습니다. 권장되지 않습니다.

![](../assets/schema4.png)

* 이 데이터를 여정에서 나중에 조회할 수 있도록 하려면 프로필의 스키마 및 데이터 세트에 표시하십시오.

![](../assets/schema5.png)

![](../assets/schema6.png)

* 사용자 정보, 이벤트가 생성된 장치, 위치 또는 이벤트와 관련된 기타 의미 있는 상황 등 이벤트에 포함할 다른 컨텍스트 데이터를 캡처하려면 데이터 필드를 자유롭게 사용하십시오.

![](../assets/schema7.png)

![](../assets/schema8.png)