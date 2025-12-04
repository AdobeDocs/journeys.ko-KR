---
product: adobe campaign
title: distinctCountWithNull
description: distinctCountWithNull 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCountWithNull {#distinctCountWithNull}

null 값을 포함하여 다른 값의 수를 계산합니다.

## 카테고리

집계

## 함수 구문

`distinctCountWithNull(<listAny>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | list부울 |
| 목록 | list정수 |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`distinctCountWithNull(<listAny>)`

정수 반환.

## 예

`distinctCountWithNull([10,2,10,null])`

3을 반환합니다.
