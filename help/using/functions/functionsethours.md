---
product: adobe campaign
title: setHours
description: setHours 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
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
source-wordcount: '106'
ht-degree: 9%
---
# setHours {#setHours}

날짜 시간 또는 날짜 시간의 시간만 설정합니다. 예를 들어 내일 특정 시간까지 기다리려면 시간을 강제로 지정할 수 있습니다.

## 카테고리

일자

## 함수 구문

`setHours(<parameter>)`

## 매개변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않은 날짜 시간 | dateTimeOnly |
| 시간 | 정수 |

## 서명 및 반환된 유형

`setHours(<dateTime>,<hours>)`

날짜/시간을 반환합니다.

`setHours(<dateTimeOnly>,<hours>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예시

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

2010-12-12T04:11:00Z를 반환합니다.

`setHours(nowWithDelta(1, "days"), 20)`

내일 오후 8:XY에 반환합니다. XY는 현재 시간 평가 시점의 분입니다. 오전 2시 45분에 평가가 이뤄지면 돌아오는 시간은 오후 8시 45분이다.
