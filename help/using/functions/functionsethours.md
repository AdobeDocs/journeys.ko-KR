---
product: adobe campaign
title: setHours
description: setHours 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 9%

---

# setHours {#setHours}

날짜 시간 또는 날짜 시간의 시간만 설정합니다. 예를 들어 내일 특정 시간까지 기다리려면 시간을 강제로 지정할 수 있습니다.

## 카테고리

Date

## 함수 구문

`setHours(<parameter>)`

## 매개변수

| 매개변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않은 날짜 시간 | dateTimeOnly |
| 시간 | 정수 |

## 서명 및 반환된 유형

`setHours(<dateTime>,<hours>)`

날짜/시간을 반환합니다.

`setHours(<dateTimeOnly>,<hours>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

2010-12-12T04:11:00Z를 반환합니다.

`setHours(nowWithDelta(1, "days"), 20)`

내일 오후 8:XY에 반환합니다. XY는 현재 시간 평가 시점의 분입니다. 평가가 오전 2:45에 이루어지면 반환된 시간은 오후 8:45입니다.
