---
product: adobe campaign
title: min
description: 최소 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 6%

---

# min {#min}

목록 또는 두 개의 표현식으로 제공되는 표현식 집합 중에서 최소값을 반환합니다. Null 값은 무시됩니다.

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
* listDateOnly
* 기간
* 정수
* 십진수
* dateTime
* dateTimeOnly

## 서명 및 반환된 형식

`min(<listDuration>)`

지속 시간을 반환합니다.

`min(<listInteger>)`

지속 시간을 반환합니다.

`min(<listDateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<listDateTime>)`

datetime을 반환합니다.

`min(<listDateOnly>)`

날짜를 반환합니다.

`min(<listDecimal>)`

소수점 반환

`min(<decimal>,<decimal>)`

소수점 반환

`min(<duration>,<duration>)`

지속 시간을 반환합니다.

`min(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`min(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<integer>,<integer>)`

정수를 반환합니다.

## 예시

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3 반환.

`min([10,null,8])`

8을 반환합니다.
