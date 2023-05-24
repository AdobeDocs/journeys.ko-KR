---
product: adobe campaign
title: inNextMonths
description: inNextMonths 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

지정된 date 또는 dateTime이 now와 now + delta 개월 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextMonths(<dateTime>,<delta>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextMonths(<dateTime>,<integer>)`

부울 반환.

## 예시

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

true를 반환합니다.
