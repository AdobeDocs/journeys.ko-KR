---
product: adobe campaign
title: toDateOnly
description: toDateOnly 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 18%
---
# toDateOnly{#toDateOnly}

인수 값을 날짜만 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateOnly(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 또는 &quot;YYYY-MM-DD&quot; 형식의 날짜(XDM 날짜 형식) | 문자열 |
| 날짜 | 날짜 |

## 서명 및 반환된 유형

`toDateOnly(<date>)`

`toDateOnly(<string>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예시

`toDateOnly("2016-08-18")`

2016-08-18을 나타내는 dateOnly 개체를 반환합니다.
