---
product: adobe campaign
title: inLastMonths
description: LastMonths의 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inLastMonths {#inLastMonths}

주어진 날짜 또는 dateTime이 지금부터 현재 - 델타 개월 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inLastMonths(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastMonths(<dateTime>,<integer>)`

부울을 반환합니다.

## 예시

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
