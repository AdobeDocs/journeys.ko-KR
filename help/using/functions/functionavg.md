---
product: adobe campaign
title: avg
description: 함수 avg에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
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
source-wordcount: '51'
ht-degree: 13%
---
# avg {#avg}

목록 또는 두 표현식으로 지정된 표현식 세트 중 평균 값을 반환합니다. Null 값은 무시됩니다.


## 카테고리

집계

## 함수 구문

`avg(<parameter>)`

## 매개변수

지원되는 유형:

* list정수
* listDecimal
* decimal
* 정수

## 서명 및 반환된 유형

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

십진수를 반환합니다.

## 예시

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0을 반환합니다

`avg(10.2, 3)`

6.6 반환.
