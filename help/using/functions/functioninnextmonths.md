---
product: adobe campaign
title: inNextMonths
description: inNextMonths 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

지정된 date 또는 dateTime이 now와 now + delta 개월 사이에 있으면 true를 반환합니다.

## 카테고리

Date

## 함수 구문

`inNextMonths(<dateTime>,<delta>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextMonths(<dateTime>,<integer>)`

부울 반환.

## 예

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

true를 반환합니다.
