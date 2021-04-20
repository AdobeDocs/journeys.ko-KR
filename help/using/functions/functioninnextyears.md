---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: NextYears의 기능에 대한 자세한 내용
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextYears {#inNextYears}

주어진 날짜 또는 dateTime이 지금부터 현재 + 델타 연도 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextYears(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextYears(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예제

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

true를 반환합니다.
