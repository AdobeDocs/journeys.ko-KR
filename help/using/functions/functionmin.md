---
product: adobe campaign
title: min
description: min 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 7%

---

# min {#min}

목록 또는 두 표현식으로 지정된 표현식 세트 중 최소값을 반환합니다. Null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`min(<parameters>)`

## 매개 변수

* listDuration
* list정수
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
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

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`min(<listDateTime>)`

날짜/시간을 반환합니다.

`min(<listDateOnly>)`

날짜를 반환합니다.

`min(<listDecimal>)`

십진수를 반환합니다.

`min(<decimal>,<decimal>)`

십진수를 반환합니다.

`min(<duration>,<duration>)`

기간을 반환합니다.

`min(<dateTime>,<dateTime>)`

날짜/시간을 반환합니다.

`min(<dateTimeOnly>,<dateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`min(<integer>,<integer>)`

정수 반환.

## 예시

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3을 반환합니다.

`min([10,null,8])`

8을 반환합니다.
