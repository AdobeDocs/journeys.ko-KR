---
product: adobe campaign
title: toDateOnly
description: toDateOnly 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# toDateOnly{#toDateOnly}

인수 값을 날짜만 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateOnly(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| ISO-8601 또는 &quot;YYYY-MM-DD&quot; 형식의 날짜(XDM 날짜 형식) | 문자열 |
| 날짜 | 날짜 |

## 서명 및 반환된 유형

`toDateOnly(<date>)`

`toDateOnly(<string>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예

`toDateOnly("2016-08-18")`

2016-08-18을 나타내는 dateOnly 개체를 반환합니다.
