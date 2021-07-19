---
product: adobe campaign
title: setDays
description: 함수 setDays에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

---

# setDays {#setDays}

날짜 시간 또는 날짜 시간만 설정합니다. 예를 들어 해당 월의 특정 일까지 기다리려면 강제로 날짜를 설정할 수 있습니다.

## 카테고리

날짜

## 함수 구문

`setDays(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 표준 시간대를 고려하지 않은 시간 | dateTimeOnly |
| 일 | 정수 |

## 서명 및 반환된 유형

`setDays(<dateTime>,<days>)`

datetime을 반환합니다.

`setDays(<dateTimeOnly>,<days>)`

시간대를 고려하지 않고 datetime을 반환합니다.

## 예

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z를 반환합니다.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
