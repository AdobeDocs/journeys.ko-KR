---
product: adobe campaign
title: inNextMonths
description: NextMonths의 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 13%

---

# inNextMonths {#inNextMonths}

주어진 날짜 또는 dateTime이 now와 now + delta months 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextMonths(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextMonths(<dateTime>,<integer>)`

부울을 반환합니다.

## 예제

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

true를 반환합니다.
