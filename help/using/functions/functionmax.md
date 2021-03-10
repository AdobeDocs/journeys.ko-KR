---
product: adobe campaign
solution: Journey Orchestration
title: max
description: 최대 함수에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---

# max{#max}

목록 또는 두 개의 표현식으로 지정된 표현식 집합 중 최대값을 반환합니다. null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`max(<parameter>)`

## 매개 변수

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* 지속 시간
* 정수
* decimal
* dateTime
* dateTimeOnly

## 서명 및 반환된 유형

`max(<listDuration>)`

지속 기간을 반환합니다.

`max(<listInteger>)`

지속 기간을 반환합니다.

`max(<listDateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`max(<listDateTime>)`

datetime을 반환합니다.

`max(<listDecimal>)`

소수점을 반환합니다.

`max(<decimal>,<decimal>)`

소수점을 반환합니다.

`max(<duration>,<duration>)`

지속 기간을 반환합니다.

`max(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`max(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`max(<integer>,<integer>)`

정수를 반환합니다.

## 예제

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10을 반환합니다.

`max([10,null,8])`

10을 반환합니다.
