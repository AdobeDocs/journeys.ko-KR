---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: 함수 집합에 대해 알아봅니다.일
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# setDays {#setDays}

날짜 시간 또는 날짜 시간만 설정합니다. 예를 들어 해당 월의 특정 일까지 대기하려면 날짜를 강제 적용할 수 있습니다.

## 범주

날짜

## 함수 구문

`setDays(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않은 날짜 시간 | dateTimeOnly |
| 일 | 정수 |

## 서명 및 반환된 문자

`setDays(<dateTime>,<days>)`

datetime을 반환합니다.

`setDays(<dateTimeOnly>,<days>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예제

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z를 반환합니다.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
