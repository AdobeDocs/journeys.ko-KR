---
product: adobe campaign
title: avg
description: 평균 함수에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 14%

---

# avg {#avg}

목록 또는 두 개의 표현식으로 제공되는 표현식 집합 간의 평균 값을 반환합니다. Null 값은 무시됩니다.


## 카테고리

집계

## 함수 구문

`avg(<parameter>)`

## 매개 변수

지원되는 유형:

* listInteger
* listDecimal
* 십진수
* 정수

## 서명 및 반환된 유형

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

소수점 반환

## 예

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0을 반환합니다.

`avg(10.2, 3)`

6.6을 반환합니다.
