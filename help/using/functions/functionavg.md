---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: avg 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---


# avg {#avg}

목록 또는 두 개의 표현식으로 제공된 표현식 집합 간의 평균 값을 반환합니다. null 값은 무시됩니다.


## 범주

집계

## 함수 구문

`avg(<parameter>)`

## 매개 변수

지원되는 유형:

* listInteger
* listDecimal
* 소수
* 정수

## 서명 및 반환된 문자

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
