---
title: max
description: 함수 최대값에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

목록 또는 두 개의 표현식으로 제공된 표현식 집합 중 최대값을 반환합니다. null 값은 무시됩니다.

## 범주

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
* 소수
* dateTime
* dateTimeOnly

## 서명 및 반환된 유형

`max(<listDuration>)`

지속 시간을 반환합니다.

`max(<listInteger>)`

지속 시간을 반환합니다.

`max(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`max(<listDateTime>)`

datetime을 반환합니다.

`max(<listDecimal>)`

소수점을 반환합니다.

`max(<decimal>,<decimal>)`

소수점을 반환합니다.

`max(<duration>,<duration>)`

지속 시간을 반환합니다.

`max(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`max(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`max(<integer>,<integer>)`

정수를 반환합니다.

## 예제

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10을 반환합니다.

`max([10,null,8])`

10을 반환합니다.
