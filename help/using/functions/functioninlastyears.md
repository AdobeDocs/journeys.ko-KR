---
product: adobe campaign
title: inLastYears
description: LastYears의 기능에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastYears {#inLastYears}

주어진 날짜 또는 dateTime이 지금부터 현재 - 델타 연도 사이에 있으면 true를 반환합니다.

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

부울을 반환합니다.

## 예

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

true를 반환합니다.
