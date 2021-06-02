---
product: adobe campaign
title: 조건 추가
description: 조건을 추가하는 방법 알아보기
feature: 여정
role: Business Practitioner
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 4%

---

# 조건 추가 {#concept_rbg_gqt_52b}

시스템 생성 이벤트의 경우, 시스템에서 이벤트 처리를 필터링할 수 있는 이벤트 조건을 정의할 수 있습니다. 조건이 true면 이벤트가 처리됩니다. 조건이 true가 아니면 이벤트가 무시됩니다.

이벤트에 대한 조건은 이벤트 페이로드에서 전달된 데이터만 기반으로 할 수 있습니다. 이벤트 수준에서 정의된 조건은 마케터가 캔버스에서 변경할 수 없습니다. 이 이벤트를 사용할 때 이 조건을 제한하는 것이 목적입니다. 예를 들어 장바구니 값이 너무 작은 경우 장바구니 포기 이벤트를 사용하지 않도록 하려면 &quot;장바구니 값&quot; 이벤트 필드에 조건을 만들고 100달러 이상의 값을 부과할 수 있습니다.

단순 표현식 편집기 또는 고급 표현식 편집기를 사용하여 이벤트에 대한 조건을 설정할 수 있습니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

예를 들어 특정 이벤트 유형의 이벤트만 처리하고 다른 유형을 무시할 조건을 정의할 수 있습니다. 또는 이벤트가 장바구니 중단이고 페이로드에 장바구니 값 필드가 포함된 경우 장바구니 값이 100달러보다 큰 경우에만 이벤트를 처리하도록 이벤트 조건을 정의할 수 있습니다.

![](../assets/journey78.png)
