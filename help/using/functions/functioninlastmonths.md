---
product: adobe campaign
title: inLastMonths
description: inLastMonths 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

지정된 date 또는 dateTime이 now와 now 사이에 있으면 true를 반환합니다(델타 월).

## 카테고리

날짜

## 함수 구문

`inLastMonths(<dateTime>,<delta>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastMonths(<dateTime>,<integer>)`

부울 반환.

## 예시

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
