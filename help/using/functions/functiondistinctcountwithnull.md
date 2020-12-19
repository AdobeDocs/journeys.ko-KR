---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: distinctCountWithNull 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 23%

---


# distinctCountWithNull {#distinctCountWithNull}

null 값을 포함하여 다른 값의 수를 카운트합니다.

## 카테고리

집계

## 함수 구문

`distinctCountWithNull(<listAny>)`

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

`distinctCountwithNull(<listAny>)`

정수를 반환합니다.

## 예제

`distinctCountWithNull([10,2,10,null])`

3을 반환합니다.
