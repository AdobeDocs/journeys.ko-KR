---
product: adobe campaign
title: inNextHours
description: inNextHours 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextHours {#inNextHours}

지정된 date 또는 dateTime이 now와 now + delta 시간 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextHours(<dateTime>,<delta>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextHours(<dateTime>,<integer>)`

부울 반환.

## 예시

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
