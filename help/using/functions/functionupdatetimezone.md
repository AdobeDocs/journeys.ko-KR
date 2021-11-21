---
product: adobe campaign
title: updateTimeZone
description: 함수 updateTimeZone에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# updateTimeZone {#updateTimeZone}

새 시간대가 동일한 순간에 있는 새 날짜 시간을 반환합니다.

## 카테고리

날짜

## 함수 구문

`updateTimeZone(<parameters>)`

## 매개 변수

* 시간대 id: string
* dateTime

## 서명 및 반환된 형식

`updateTimeZone(<dateTime>,<timeZone id>)`

datetime을 반환합니다.

## 예시

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17 반환:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

타임스탬프 필드의 값이 `2021-11-16T16:55:12.939318+01:00`를 반환한 후 함수가 `2021-11-17T02:55:12.942115+11:00`.
