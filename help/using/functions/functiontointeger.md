---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Integer 함수에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 8%

---


# toInteger {#toInteger}

인수 값을 정수로 변환합니다.

## 카테고리

전환

## 함수 구문

`toInteger(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 정수로 변환합니다. |
| dateTime | 날짜를 밀리초 수로 변환합니다(밀리초). |
| decimal | 소수점 이하(예:1.5가 1이 됨) |
| boolean | 부울 값을 true이면 1로, false이면 0으로 변환합니다. |

## 서명 및 반환된 유형

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

정수를 반환합니다.

## 예제

`toInteger("4")`

4를 반환합니다.
