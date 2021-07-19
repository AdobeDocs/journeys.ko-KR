---
product: adobe campaign
title: count
description: 함수 개수에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 31%

---

# count {#count}

null 값을 고려하지 않는 목록의 요소를 계산합니다.

## 카테고리

집계

## 함수 구문

`count(<listAny>)`

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

## 서명 및 반환된 유형

`count(<listAny>)`

정수를 반환합니다.

## 예

`count([10,2,10,null])`

3 반환.
