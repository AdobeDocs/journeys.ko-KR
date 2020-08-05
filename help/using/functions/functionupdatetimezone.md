---
title: updateTimeZone
description: 함수 updateTimeZone 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

새 시간대가 동일한 순간에 있는 새 날짜 시간을 반환합니다.

## 범주

날짜

## 함수 구문

`updateTimeZone(<parameters>)`

## 매개 변수

* 시간대 ID: 문자열
* dateTime

## 서명 및 반환된 문자

`updateTimeZone(<dateTime>,<timeZone id>)`

datetime을 반환합니다.

## 예제

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00을 반환합니다.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
