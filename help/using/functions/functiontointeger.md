---
product: adobe campaign
title: toInteger
description: toInteger 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 9%

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
| string | 문자열 값을 정수로 변환 |
| dateTime | 날짜를 밀리초(epoch 밀리초)로 변환 |
| 십진수 | 소수점 부분을 제거하여 정수로 변환합니다(예:1.5가 1이 됨) |
| 부울 | 부울 값을 true면 1로, false이면 0으로 변환합니다 |

## 서명 및 반환된 유형

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

정수를 반환합니다.

## 예제

`toInteger("4")`

4 반환.
