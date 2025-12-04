---
product: adobe campaign
title: inNextDays
description: inNextDays 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

지정된 date 또는 dateTime이 now와 now + delta 일 사이인 경우 true를 반환합니다.

## 카테고리

Date

## 함수 구문

`inNextDays(<dateTime>,<delta>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextDays(<dateTime>,<integer>)`

부울 반환.

## 예

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
