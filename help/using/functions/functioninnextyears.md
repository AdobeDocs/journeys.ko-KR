---
product: adobe campaign
title: inNextYears
description: inNextYears 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextYears {#inNextYears}

지정된 date 또는 dateTime이 now와 now + delta years 사이에 있으면 true를 반환합니다.

## 카테고리

Date

## 함수 구문

`inNextYears(<dateTime>,<delta>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 유형

`inNextYears(<dateTime>,<integer>)`

부울 반환.

## 예

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

true를 반환합니다.
