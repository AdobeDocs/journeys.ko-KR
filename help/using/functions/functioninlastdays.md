---
product: adobe campaign
title: inLastDays
description: inLastDays 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastDays {#inLastDays}

지정된 date 또는 dateTime이 now와 now 사이에 있으면 true를 반환합니다(델타 일).

## 카테고리

날짜

## 함수 구문

`inLastDays(<dateTime>,<delta>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastDays(<dateTime>,<integer>)`

부울 반환.

## 예시

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

true를 반환합니다.
