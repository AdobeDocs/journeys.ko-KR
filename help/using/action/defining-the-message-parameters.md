---
product: adobe campaign
title: 메시지 매개 변수 정의
description: 메시지 매개 변수를 정의하는 방법을 알아봅니다
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 1251eafcfe7487c3df01b412f17706f5ed6c6836
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 4%

---

# 메시지 매개 변수 정의 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

**[!UICONTROL Message parameters]** 섹션에서 외부 서비스로 전송할 JSON 페이로드의 예제를 붙여넣습니다.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>페이로드의 필드 이름에는 &quot;.&quot;를 사용할 수 없습니다. 문자.

매개 변수 유형(예:문자열, 정수 등)

매개 변수가 상수 또는 변수인지를 지정할 수도 있습니다.

* 상수는 매개 변수의 값이 기술 성향에 의해 작업 구성 창에 정의되어 있음을 의미합니다. 값은 여정 간에 항상 동일합니다. 여정에서 사용자 지정 작업을 사용할 때에는 변경사항이 발생하지 않으며 마케터가 표시되지 않습니다. 예를 들어 서드파티 시스템에서 기대하는 ID일 수 있습니다. 이 경우 전환 상수/변수 오른쪽에 있는 필드가 전달된 값입니다.
* 변수는 매개 변수의 값이 변경됨을 의미합니다. 여정에서 이 사용자 지정 작업을 사용하는 마케터는 원하는 값을 전달하거나 이 매개 변수의 값을 검색할 위치(예: 이벤트에서 또는 Adobe Experience Platform에서)를 지정할 수 있습니다. 이 경우 전환 상수/변수 오른쪽의 필드는 여정에서 이 매개 변수의 이름을 지정하는 레이블입니다.

![](../assets/customactionpayloadmessage2.png)
