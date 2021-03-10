---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: toDateTime 함수에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 9%

---


# toDateTimeOnly{#toDateTimeOnly}

인수 값을 날짜 시간 전용 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateTimeOnly(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 형식의 날짜 시간 | 문자열 |
| 날짜 시간 | dateTime |

## 서명 및 반환된 유형

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

시간대를 고려하지 않고 datetime을 반환합니다.

## 예제

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

2016-08-18T23:17:59.123을 반환합니다.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
