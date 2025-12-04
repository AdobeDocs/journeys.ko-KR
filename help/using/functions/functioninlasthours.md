---
product: adobe campaign
title: inLastHours
description: inLastHours 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastHours {#inLastHours}

지정된 날짜 시간이 지금부터 델타 시간 사이인 경우 true를 반환합니다.

## 카테고리

Date

## 함수 구문

`inLastHours(<dateTime>,<delta>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastHours(<dateTime>,<integer>)`

부울 반환.

## 예

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

true를 반환합니다.

`inLastHours(@{MyEvent.timestamp}, 4)`

true를 반환합니다.
