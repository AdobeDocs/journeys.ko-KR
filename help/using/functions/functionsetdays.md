---
product: adobe campaign
title: setDays
description: setDays 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 13%

---

# setDays {#setDays}

날짜/시간 또는 날짜/시간만 설정합니다. 예를 들어, 특정 날짜까지 기다리려면 날짜를 강제로 지정할 수 있습니다.

## 카테고리

Date

## 함수 구문

`setDays(<parameter>)`

## 매개변수

| 매개변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않은 날짜 시간 | dateTimeOnly |
| 일 | 정수 |

## 서명 및 반환된 유형

`setDays(<dateTime>,<days>)`

날짜/시간을 반환합니다.

`setDays(<dateTimeOnly>,<days>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z를 반환합니다.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
