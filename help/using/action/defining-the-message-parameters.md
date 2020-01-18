---
title: 메시지 매개 변수 정의
description: 메시지 매개 변수를 정의하는 방법 알아보기
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 메시지 매개 변수 정의 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

섹션에서 외부 서비스로 전송할 JSON 페이로드의 예를 붙여 넣습니다. **[!UICONTROL Message parameters]**


![](../assets/customactionpayloadmessage.png)

매개 변수의 유형이 적절한지(예:문자열, 정수 등).

매개 변수를 상수 또는 변수로 지정할 수도 있습니다.

* 상수는 매개 변수의 값이 작업 구성 창에서 기술적 페르소나로 정의됨을 의미합니다. 이 값은 모든 경로에서 항상 동일합니다. 고객은 이에 따라 달라질 수 없으며 고객 여정의 사용자 지정 동작을 사용할 때 이를 확인할 수 없습니다. 예를 들어 타사 시스템에서 기대하는 ID일 수 있습니다. 이 경우 전환 상수/변수 오른쪽의 필드는 전달된 값입니다.
* 변수는 매개 변수의 값이 달라짐을 의미합니다. 경로에서 이 사용자 지정 작업을 사용하는 마케터는 원하는 값을 전달하거나 이 매개 변수의 값(예: 이벤트에서 데이터 플랫폼...)을 가져올 위치를 지정할 수 있습니다. 이 경우 전환 상수/변수 오른쪽의 필드는 마케터가 이 매개 변수의 이름을 지정할 때 보게 되는 레이블입니다.
