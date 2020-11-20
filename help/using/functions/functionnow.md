---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 기능에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# now {#now}

현재 날짜를 날짜 시간 형식으로 반환합니다. For more information on data types, refer to [this page](../expression/data-types.md).

## 범주

날짜

## 함수 구문

`now(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 |  |

## 서명 및 반환된 문자

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