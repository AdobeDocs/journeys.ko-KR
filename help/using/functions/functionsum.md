---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: 함수 합에 대해 알아봅니다.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

---


# sum {#sum}

표현식 세트의 값의 합계를 반환합니다. null 값은 무시됩니다.

## 범주

집계

## 함수 구문

`sum(<parameters>)`

## 매개 변수

* listInteger
* listDecimal
* 지속 시간
* 정수
* 소수

## 서명 및 반환된 유형

`sum(<listDecimal>)`

소수점을 반환합니다.

`sum(<listInteger>)`

정수를 반환합니다.

`sum(<integer>,<integer>)`

정수를 반환합니다.

`sum(<decimal>,<decimal>)`

소수점을 반환합니다.

## 예제

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21을 반환합니다.

`sum([10.5,null,8.1])`

18.6을 반환합니다.
