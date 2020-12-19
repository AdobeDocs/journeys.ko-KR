---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: LastDays 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inLastDays {#inLastDays}

주어진 날짜 또는 dateTime이 현재 - 델타 일 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inLastDays(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastDays(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예제

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

true를 반환합니다.
