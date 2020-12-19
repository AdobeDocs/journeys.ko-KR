---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: LastYears의 기능에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inLastYears {#inLastYears}

주어진 날짜 또는 dateTime이 현재 - 델타 연도 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inLastYears(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inLastYears(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예제

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

true를 반환합니다.
