---
product: adobe campaign
title: toDateTimeOnly
description: toDateTime 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

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
| ISO-8601 형식의 날짜 시간 | string |
| 날짜 시간 | dateTime |

## 서명 및 반환된 형식

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예제

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

2016-08-18T23:17:59.123을 반환합니다.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
