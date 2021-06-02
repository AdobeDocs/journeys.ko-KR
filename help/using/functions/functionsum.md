---
product: adobe campaign
title: sum
description: 함수 합에 대해 알아봅니다
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

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
* 기간
* 정수
* 십진수

## 서명 및 반환된 형식

`sum(<listDecimal>)`

소수점 반환

`sum(<listInteger>)`

정수를 반환합니다.

`sum(<integer>,<integer>)`

정수를 반환합니다.

`sum(<decimal>,<decimal>)`

소수점 반환

## 예제

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21을 반환합니다.

`sum([10.5,null,8.1])`

18.6을 반환합니다.
