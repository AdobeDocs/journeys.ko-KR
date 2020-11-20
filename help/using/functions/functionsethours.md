---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: 함수 집합에 대해 알아봅니다.시간
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# setHours {#setHours}

날짜 시간 또는 날짜 시간만 설정합니다. 예를 들어 내일 특정 시간까지 대기하려는 경우 시간을 강제 적용할 수 있습니다.

## 범주

날짜

## 함수 구문

`setHours(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않은 날짜 시간 | dateTimeOnly |
| 시간 | 정수 |

## 서명 및 반환된 문자

`setHours(<dateTime>,<hours>)`

datetime을 반환합니다.

`setHours(<dateTimeOnly>,<hours>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예제

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Z를 반환합니다.

`setHours(nowWithDelta(1, "days"), 20)`

내일 저녁 8시에 돌아오세요
