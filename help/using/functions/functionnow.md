---
product: adobe campaign
title: now
description: 지금 함수 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%

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
| string |  |

## 서명 및 반환된 유형

`now()`

`now("<timeZone id>")`

dateTime 반환

## 예

`now()`

2019-06-03T06:30Z를 반환합니다.

`toString(now())`

반환: &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

2019-06-03T08:30+02:00을 반환합니다.
