---
product: adobe campaign
title: countWithNull
description: countWithNull 함수에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# countWithNull {#countWithNull}

null 값을 포함하여 목록의 모든 요소를 계산합니다.

## 카테고리

집계

## 함수 구문

`countWithNull(<listAny>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | list부울 |
| 목록 | list정수 |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`countWithNull(<listAny>)`

정수 반환.

## 예

`countWithNull([10,2,10,null])`

4를 반환합니다.
