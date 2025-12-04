---
product: adobe campaign
title: now
description: 이제 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# now {#now}

현재 날짜를 날짜 시간 형식으로 반환합니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

Date

## 함수 구문

`now(<parameter>)`

## 매개변수

| 매개변수 | 설명 |
|--- |--- |
| 문자열 |  |

## 서명 및 반환된 유형

`now()`

`now("<timeZone id>")`

dateTime을 반환합니다.

## 예

`now()`

2019-06-03T06:30Z을 반환합니다.

`toString(now())`

&quot;2019-06-03T06:30Z&quot; 반환

`now("Europe/Paris")`

2019-06-03T08:30+02:00을 반환합니다.
