---
product: adobe campaign
title: toDecimal
description: toDecimal 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 14%

---

# toDecimal {#toDecimal}

인수 유형에 따라 인수 값을 십진수 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDecimal(<parameter>)`

## 매개변수

| 매개변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 소수로 변환합니다. |
| dateTime | 날짜를 밀리초 단위로 변환(에포크 밀리초) |
| 부울 | true이면 부울 값을 1, false이면 부울 값으로 변환합니다. |
| 정수 | 소수로 변환합니다(예: ).: 1이 1.0이 됨) |

## 서명 및 반환된 유형

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

십진수를 반환합니다.

## 예

`toDecimal("4.0")`

4.0을 반환합니다
