---
product: adobe campaign
title: sum
description: 함수 합에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
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
source-wordcount: '53'
ht-degree: 13%
---
# sum {#sum}

표현식 집합의 값 합계를 반환합니다. Null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`sum(<parameters>)`

## 매개변수

* list정수
* listDecimal
* 지속 시간
* 정수
* decimal

## 서명 및 반환된 유형

`sum(<listDecimal>)`

십진수를 반환합니다.

`sum(<listInteger>)`

정수 반환.

`sum(<integer>,<integer>)`

정수 반환.

`sum(<decimal>,<decimal>)`

십진수를 반환합니다.

## 예시

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21을 반환합니다.

`sum([10.5,null,8.1])`

18.6을 반환합니다.
