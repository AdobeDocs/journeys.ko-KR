---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: LastHours의 기능에 대해 알아봅니다.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 8%

---


# inLastHours {#inLastHours}

주어진 날짜 시간이 지금부터 현재 - 델타 시간 사이에 있으면 true를 반환합니다.

## 범주

날짜

## 함수 구문

`inLastHours(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 문자

`inLastHours(<dateTime>,<integer>)`

부울을 반환합니다.

## 예제

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

true를 반환합니다.

`inLastHours(@{MyEvent.timestamp}, 4)`

true를 반환합니다.
