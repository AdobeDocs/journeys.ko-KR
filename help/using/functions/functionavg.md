---
product: adobe campaign
title: avg
description: 함수 avg에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 14%

---

# avg {#avg}

목록 또는 두 표현식으로 지정된 표현식 세트 중 평균 값을 반환합니다. Null 값은 무시됩니다.


## 카테고리

집계

## 함수 구문

`avg(<parameter>)`

## 매개 변수

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
