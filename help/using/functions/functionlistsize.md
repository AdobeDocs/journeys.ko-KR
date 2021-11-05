---
product: adobe campaign
title: listSize
description: 함수 listSize에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c0d34a8d-33e9-4c7b-9b7d-a1b21ed96d35
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 34%

---

# listSize {#listSize}

목록의 요소 수를 계산합니다.

## 카테고리

목록

## 함수 구문

`listSize(<parameters>)`

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
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

정수를 반환합니다.

## 예

`listSize([10,2,3])`

3 반환.
