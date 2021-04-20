---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: 평균 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 9%

---


# avg {#avg}

목록 또는 두 개의 표현식으로 지정된 표현식 집합 중 평균 값을 반환합니다. null 값은 무시됩니다.


## 카테고리

집계

## 함수 구문

`avg(<parameter>)`

## 매개 변수

지원되는 유형:

* listInteger
* listDecimal
* decimal
* 정수

## 서명 및 반환된 유형

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

소수점을 반환합니다.

## 예제

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0을 반환합니다.

`avg(10.2, 3)`

6.6을 반환합니다.
