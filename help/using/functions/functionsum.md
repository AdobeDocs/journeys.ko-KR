---
product: adobe campaign
title: sum
description: 함수 합에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# sum {#sum}

표현식 집합의 값 합계를 반환합니다. Null 값은 무시됩니다.

## 카테고리

집계

## 함수 구문

`sum(<parameters>)`

## 매개 변수

* list정수
* listDecimal
* 지속 시간
* 정수
* decimal

## 서명 및 반환된 유형

`sum(<listDecimal>)`

십진수를 반환합니다.

`sum(<listInteger>)`

정수 반환.

`sum(<integer>,<integer>)`

정수 반환.

`sum(<decimal>,<decimal>)`

십진수를 반환합니다.

## 예시

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21을 반환합니다.

`sum([10.5,null,8.1])`

18.6을 반환합니다.
