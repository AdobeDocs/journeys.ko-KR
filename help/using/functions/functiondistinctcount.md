---
product: adobe campaign
title: distinctCount
description: distinctCount 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCount{#distinctCount}

null 값을 무시하고 다른 값의 수를 계산합니다.

## 카테고리

집계

## 함수 구문

`distinctCount(<listAny>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listInteger |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |

## 서명 및 반환된 형식

`distinctCount(<listAny>)`

정수를 반환합니다.

## 예

`distinctCount([10,2,10,null])`

2를 반환합니다.
