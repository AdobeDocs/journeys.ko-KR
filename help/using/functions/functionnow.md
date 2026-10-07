---
product: adobe campaign
title: now
description: 이제 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
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
ht-degree: 15%
---
# now {#now}

현재 날짜를 날짜 시간 형식으로 반환합니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

일자

## 함수 구문

`now(<parameter>)`

## 매개변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 |  |

## 서명 및 반환된 유형

`now()`

`now("<timeZone id>")`

dateTime을 반환합니다.

## 예시

`now()`

2019-06-03T06:30Z를 반환합니다.

`toString(now())`

&quot;2019-06-03T06:30Z&quot; 반환

`now("Europe/Paris")`

2019-06-03T08:30+02:00을 반환합니다.
