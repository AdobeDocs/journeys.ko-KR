---
title: inNextHours
description: NextHours의 기능에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextHours {#inNextHours}

주어진 날짜 또는 dateTime이 지금부터 현재 + 델타 시간 사이에 있으면 true를 반환합니다.

## 범주

날짜

## 함수 구문

`inNextHours(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 문자

`inNextHours(<dateTime>,<integer>)`

부울을 반환합니다.

## 예제

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

true를 반환합니다.
