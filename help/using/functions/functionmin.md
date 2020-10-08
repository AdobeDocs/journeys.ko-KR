---
title: min
description: 최소 함수 학습
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---


# min {#min}

목록 또는 두 개의 표현식으로 제공된 표현식 집합 중 최소값을 반환합니다. null 값은 무시됩니다.

## 범주

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
* 소수
* dateTime
* dateTimeOnly

## 서명 및 반환된 유형

`min(<listDuration>)`

지속 시간을 반환합니다.

`min(<listInteger>)`

지속 시간을 반환합니다.

`min(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`min(<listDateTime>)`

datetime을 반환합니다.

`min(<listDecimal>)`

소수점을 반환합니다.

`min(<decimal>,<decimal>)`

소수점을 반환합니다.

`min(<duration>,<duration>)`

지속 시간을 반환합니다.

`min(<dateTime>,<dateTime>)`

datetime을 반환합니다.

`min(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`min(<integer>,<integer>)`

정수를 반환합니다.

## 예제

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

반환 3.

`min([10,null,8])`

8을 반환합니다.
