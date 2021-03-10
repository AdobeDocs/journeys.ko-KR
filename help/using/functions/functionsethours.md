---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: 함수 집합에 대해 알아봅니다.시간
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# setHours {#setHours}

날짜 시간 또는 날짜 시간만 설정합니다. 예를 들어, 내일 특정 시간까지 기다리려면 시간을 강제할 수 있습니다.

## 카테고리

날짜

## 함수 구문

`setHours(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않고 | dateTimeOnly |
| hours | 정수 |

## 서명 및 반환된 유형

`setHours(<dateTime>,<hours>)`

datetime을 반환합니다.

`setHours(<dateTimeOnly>,<hours>)`

시간대를 고려하지 않고 datetime을 반환합니다.

## 예제

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Z를 반환합니다.

`setHours(nowWithDelta(1, "days"), 20)`

내일 저녁 8시에 돌아오겠습니다.
