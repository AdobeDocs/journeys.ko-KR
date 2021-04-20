---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 지금 기능에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---


# now {#now}

현재 날짜를 날짜 시간 형식으로 반환합니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

날짜

## 함수 구문

`now(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 |  |

## 서명 및 반환된 유형

`now()`

`now("<timeZone id>")`

dateTime을 반환합니다.

## 예제

`now()`

2019-06-03T06:30Z를 반환합니다.

`toString(now())`

&quot;2019-06-03T06:30Z&quot;를 반환합니다.

`now("Europe/Paris")`

2019-06-03T08:30+02:00을 반환합니다.