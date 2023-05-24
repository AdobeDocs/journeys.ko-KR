---
product: adobe campaign
title: 작업 매개 변수 정의
description: 작업 매개 변수를 정의하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 4%

---

# 작업 매개 변수 정의 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

다음에서 **[!UICONTROL Action parameters]** 섹션에 외부 서비스로 전송할 JSON 페이로드의 예제를 붙여 넣습니다.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>페이로드의 필드 이름에는 &quot;.&quot;를 사용할 수 없습니다. 문자. &quot;$&quot; 문자로 시작할 수 없습니다.

매개 변수 유형(예: 문자열, 정수 등)을 정의할 수 있습니다.

매개 변수가 상수인지 변수인지 지정할 것인지 선택할 수도 있습니다.

* 상수는 매개 변수 값이 기술 담당자에 의해 작업 구성 창에 정의됨을 의미합니다. 값은 여정 간에 항상 동일합니다. 여정에서 사용자 지정 작업을 사용할 때 변경되지 않으며 마케터가 표시되지 않습니다. 예를 들어 서드파티 시스템에서 예상하는 ID일 수 있습니다. 이 경우 상수/변수 전환 오른쪽에 있는 필드가 전달된 값입니다.
* 변수는 매개 변수의 값이 변함을 의미합니다. 여정에서 이 사용자 지정 작업을 사용하는 마케터는 원하는 값을 전달하거나 이 매개 변수에 대한 값을 검색할 위치를 지정할 수 있습니다(예: 이벤트, Adobe Experience Platform 등). 이 경우 전환 상수/변수 오른쪽의 필드는 이 매개 변수의 이름을 지정하기 위해 여정에 표시되는 레이블입니다.

![](../assets/customactionpayloadmessage2.png)
