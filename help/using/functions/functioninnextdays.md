---
product: adobe campaign
title: inNextDays
description: inNextDays 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

지정된 date 또는 dateTime이 now와 now + delta 일 사이인 경우 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextDays(<dateTime>,<delta>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextDays(<dateTime>,<integer>)`

부울 반환.

## 예시

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
