---
product: adobe campaign
title: updateTimeZone
description: 함수 updateTimeZone에 대해 알아봅니다.
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 7%

---


# updateTimeZone {#updateTimeZone}

새 시간대가 동일한 순간에 있는 새 날짜 시간을 반환합니다.

## 카테고리

날짜

## 함수 구문

`updateTimeZone(<parameters>)`

## 매개 변수

* 시간대 id:string
* dateTime

## 서명 및 반환된 형식

`updateTimeZone(<dateTime>,<timeZone id>)`

datetime을 반환합니다.

## 예제

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00을 반환합니다.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
