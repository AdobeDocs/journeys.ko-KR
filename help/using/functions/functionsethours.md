---
product: adobe campaign
title: setHours
description: 함수 setHours에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 7%

---

# setHours {#setHours}

날짜 시간 또는 날짜 시간의 시간만 설정합니다. 예를 들어 내일 일정 시간까지 기다리려면 시간을 강제 적용할 수 있습니다.

## 카테고리

날짜

## 함수 구문

`setHours(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 표준 시간대를 고려하지 않은 시간 | dateTimeOnly |
| 시간 | 정수 |

## 서명 및 반환된 유형

`setHours(<dateTime>,<hours>)`

datetime을 반환합니다.

`setHours(<dateTimeOnly>,<hours>)`

시간대를 고려하지 않고 datetime을 반환합니다.

## 예제

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Z를 반환합니다.

`setHours(nowWithDelta(1, "days"), 20)`

내일 오후 8시에 돌아옵니다.
