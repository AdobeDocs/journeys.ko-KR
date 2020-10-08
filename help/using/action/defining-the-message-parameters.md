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
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# 메시지 매개 변수 정의 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

섹션에서 **[!UICONTROL Message parameters]** 외부 서비스로 전송할 JSON 페이로드의 예를 붙여넣습니다.

![](../assets/customactionpayloadmessage.png)

매개 변수 유형(예:문자열, 정수 등).

매개 변수가 상수 또는 변수인지 여부를 지정할 수도 있습니다.

* 상수는 매개 변수의 값이 작업 구성 창에서 기술 페르소나로 정의됨을 의미합니다. 이 값은 모든 여정에서 항상 동일합니다. 고객 여정의 맞춤형 동작을 사용해도 달라질 수 있으므로 마케터는 이에 동의하지 않습니다. 예를 들어 타사 시스템에서 기대하는 ID일 수 있습니다. 이 경우 전환 상수/변수 오른쪽에 있는 필드는 전달된 값입니다.
* 변수는 매개 변수의 값이 다를 것임을 의미합니다. 경로에서 이 사용자 지정 작업을 사용하는 마케터는 원하는 값을 전달하거나 이 매개 변수의 값을 가져올 위치(예: 이벤트, Adobe Experience Platform 등)를 지정할 수 있습니다. 이 경우 전환 상수/변수 오른쪽의 필드는 마케터가 이 매개 변수의 이름을 지정하기 위해 여정에서 볼 레이블입니다.

![](../assets/customactionpayloadmessage2.png)
