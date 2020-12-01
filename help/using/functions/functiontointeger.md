---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: 정수 함수 알아보기
translation-type: tm+mt
source-git-commit: e2f7c39e61118c42272f730cf5f688ee34d6a9c2
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

인수 값을 정수로 변환합니다.

## 범주

전환

## 함수 구문

`toInteger(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 정수로 변환합니다. |
| dateTime | 날짜를 밀리초(epoch milliseconds)의 수로 변환합니다. |
| 소수 | decimal part를 제거하여 정수(예:1.5가 1이 됨) |
| boolean | 부울 값을 true이면 1, false이면 0으로 변환합니다. |

## 서명 및 반환된 문자

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

정수를 반환합니다.

## 예제

`toInteger("4")`

반환 4입니다.
