---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: 함수 목록에 대해 학습크기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---


# listSize {#listSize}

목록의 요소 수를 카운트합니다.

## 카테고리

목록

## 함수 구문

`listSize(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listInteger |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |

## 서명 및 반환된 유형

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

정수를 반환합니다.

## 예제

`listSize([10,2,3])`

3을 반환합니다.
