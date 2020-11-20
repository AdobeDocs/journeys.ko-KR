---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Decimal 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

---


# toDecimal {#toDecimal}

유형에 따라 인수 값을 십진수 값으로 변환합니다.

## 범주

전환

## 함수 구문

`toDecimal(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 소수로 변환합니다. |
| dateTime | 날짜를 밀리초(epoch milliseconds)의 수로 변환합니다. |
| boolean | 부울 값을 true이면 1, false이면 0으로 변환합니다. |
| 정수 | decimal로 변환합니다(예).:1이 1.0이 됨) |

## 서명 및 반환된 유형

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

십진수를 반환합니다.

## 예제

`toDecimal("4.0")`

4.0을 반환합니다.
