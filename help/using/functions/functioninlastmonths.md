---
product: adobe campaign
title: inLastMonths
description: inLastMonths 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%
---
# inLastMonths {#inLastMonths}

지정된 date 또는 dateTime이 now와 now 사이에 있으면 true를 반환합니다(델타 월).

## 카테고리

일자

## 함수 구문

`inLastMonths(<dateTime>,<delta>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastMonths(<dateTime>,<integer>)`

부울 반환.

## 예시

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
