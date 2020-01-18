---
title: avl
description: 함수 avg에 대한 자세한 내용
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# avl {#avg}

목록 또는 두 개의 표현식으로 지정된 표현식 집합 중 평균 값을 반환합니다. Null 값은 무시됩니다.


## 카테고리

집계

## 함수 구문

`avg(<parameter>)`

## 매개 변수

지원되는 유형:

* listInteger
* listDecimal
* decimal
* 정수

## 서명 및 반환된 문자

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

소수점을 반환합니다.

## 예

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0을 반환합니다.

`avg(10.2, 3)`

6.6을 반환합니다.
