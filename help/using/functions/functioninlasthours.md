---
product: adobe campaign
title: inLastHours
description: LastHours의 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 13%

---

# inLastHours {#inLastHours}

주어진 날짜 시간이 지금부터 현재 - 델타 시간 사이에 있는 경우 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inLastHours(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastHours(<dateTime>,<integer>)`

부울을 반환합니다.

## 예제

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

true를 반환합니다.

`inLastHours(@{MyEvent.timestamp}, 4)`

true를 반환합니다.
