---
product: adobe campaign
solution: Journey Orchestration
title: min
description: 최소 함수 학습
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---


# min {#min}

목록 또는 2개의 표현식으로 지정된 표현식 집합 중 최소값을 반환합니다. null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`min(<parameters>)`

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

`min(<listDuration>)`

지속 기간을 반환합니다.

`min(<listInteger>)`

지속 기간을 반환합니다.

`min(<listDateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<listDateTime>)`

datetime을 반환합니다.

`min(<listDecimal>)`

소수점을 반환합니다.

`min(<decimal>,<decimal>)`

소수점을 반환합니다.

`min(<duration>,<duration>)`

지속 기간을 반환합니다.

`min(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`min(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<integer>,<integer>)`

정수를 반환합니다.

## 예제

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3을 반환합니다.

`min([10,null,8])`

8을 반환합니다.
