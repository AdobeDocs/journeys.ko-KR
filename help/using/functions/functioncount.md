---
product: adobe campaign
title: count
description: 함수 개수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 30%

---

# count {#count}

null 값을 고려하지 않는 목록의 요소를 계산합니다.

## 카테고리

집계

## 함수 구문

`count(<listAny>)`

## 매개 변수

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

`count(<listAny>)`

정수 반환.

## 예

`count([10,2,10,null])`

3을 반환합니다.
