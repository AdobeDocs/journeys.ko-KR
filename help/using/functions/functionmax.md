---
product: adobe campaign
title: max
description: 최대 함수에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 7%

---

# max{#max}

목록 또는 두 개의 표현식으로 제공되는 표현식 집합 중 최대값을 반환합니다. Null 값은 무시됩니다.

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
* 기간
* 정수
* 십진수
* dateTime
* dateTimeOnly

## 서명 및 반환된 형식

`max(<listDuration>)`

지속 시간을 반환합니다.

`max(<listInteger>)`

지속 시간을 반환합니다.

`max(<listDateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`max(<listDateTime>)`

datetime을 반환합니다.

`max(<listDecimal>)`

소수점 반환

`max(<decimal>,<decimal>)`

소수점 반환

`max(<duration>,<duration>)`

지속 시간을 반환합니다.

`max(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`max(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`max(<integer>,<integer>)`

정수를 반환합니다.

## 예

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10을 반환합니다.

`max([10,null,8])`

10을 반환합니다.
