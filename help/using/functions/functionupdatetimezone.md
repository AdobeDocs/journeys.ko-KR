---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: updateTimeZone 함수에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

동일한 순간에 새 시간대가 있는 새 날짜 시간을 반환합니다.

## 카테고리

날짜

## 함수 구문

`updateTimeZone(<parameters>)`

## 매개 변수

* 시간대 ID:문자열
* dateTime

## 서명 및 반환된 유형

`updateTimeZone(<dateTime>,<timeZone id>)`

datetime을 반환합니다.

## 예제

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00을 반환합니다.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
