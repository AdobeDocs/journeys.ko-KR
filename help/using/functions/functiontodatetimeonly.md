---
product: adobe campaign
title: toDateTimeOnly
description: 함수 toDateTime에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
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
source-wordcount: '60'
ht-degree: 15%
---
# toDateTimeOnly{#toDateTimeOnly}

인수 값을 날짜/시간 전용 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateTimeOnly(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 또는 &quot;YYYY-MM-DD&quot; 형식의 날짜 시간(XDM 날짜 형식) | 문자열 |
| 날짜 시간 | dateTime |

## 서명 및 반환된 유형

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--
`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`
-->

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예시

`toDateTimeOnly ("2016-08-18")`

2016-08-18T00:00:00.000을 나타내는 dateTime을 반환합니다

`toDateTimeOnly(now())`

<!--
`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.
-->
