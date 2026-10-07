---
product: adobe campaign
title: updateTimeZone
description: updateTimeZone 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
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
source-wordcount: '57'
ht-degree: 10%
---
# updateTimeZone {#updateTimeZone}

같은 순간에 새 시간대와 함께 새 날짜 시간을 반환합니다.

## 카테고리

일자

## 함수 구문

`updateTimeZone(<parameters>)`

## 매개변수

* 시간대 id: 문자열
* dateTime

## 서명 및 반환된 유형

`updateTimeZone(<dateTime>,<timeZone id>)`

날짜/시간을 반환합니다.

## 예시

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00을 반환합니다.

<!--
`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".
-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

타임스탬프 필드의 값이 `2021-11-16T16:55:12.939318+01:00`이면 함수는 `2021-11-17T02:55:12.942115+11:00`을(를) 반환합니다.
