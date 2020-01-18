---
title: sum
description: 함수 합에 대해 자세히 알아보기
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


# sum {#sum}

표현식 세트의 값 합계를 반환합니다. Null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`sum(<parameters>)`

## 매개 변수

* listInteger
* listDecimal
* 지속 시간
* 정수
* decimal

## 서명 및 반환된 유형

`sum(<listDecimal>)`

소수점을 반환합니다.

`sum(<listInteger>)`

정수를 반환합니다.

`sum(<integer>,<integer>)`

정수를 반환합니다.

`sum(<decimal>,<decimal>)`

소수점을 반환합니다.

## 예

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21을 반환합니다.

`sum([10.5,null,8.1])`

18.6을 반환합니다.
