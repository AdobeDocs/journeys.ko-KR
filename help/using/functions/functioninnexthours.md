---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: NextHours의 기능에 대해 알아봅니다.
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextHours {#inNextHours}

주어진 날짜 또는 dateTime이 현재 시간 + 델타 시간 사이인 경우 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextHours(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextHours(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예제

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
