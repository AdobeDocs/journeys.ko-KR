---
title: min
description: 최소 함수에 대한 자세한 내용
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

---


# min {#min}

목록 또는 두 표현식으로 지정된 표현식 집합 중 최소값을 반환합니다. Null 값은 무시됩니다.

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

기간을 반환합니다.

`min(<listInteger>)`

기간을 반환합니다.

`min(<listDateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<listDateTime>)`

datetime을 반환합니다.

`min(<listDecimal>)`

소수점을 반환합니다.

`min(<decimal>,<decimal>)`

소수점을 반환합니다.

`min(<duration>,<duration>)`

기간을 반환합니다.

`min(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`min(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`min(<integer>,<integer>)`

정수를 반환합니다.

## 예

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

반환 3입니다.

`min([10,null,8])`

8을 반환합니다.
