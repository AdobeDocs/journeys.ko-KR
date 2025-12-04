---
product: adobe campaign
title: distinctCount
description: distinctCount 함수에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCount{#distinctCount}

null 값을 무시하는 다른 값의 수를 계산합니다.

## 카테고리

집계

## 함수 구문

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

정수 반환.

## 예

`distinctCount([10,2,10,null])`

2를 반환합니다.
