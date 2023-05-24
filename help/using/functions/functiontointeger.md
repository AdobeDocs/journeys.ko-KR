---
product: adobe campaign
title: toInteger
description: toInteger 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%

---

# toInteger {#toInteger}

인수 값을 정수로 변환합니다.

## 카테고리

전환

## 함수 구문

`toInteger(<parameter>)`

## 매개 변수

| 매개변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 정수로 변환합니다. |
| dateTime | 날짜를 밀리초 단위로 변환(에포크 밀리초) |
| decimal | 소수 부분을 제거하여 정수로 변환합니다(예: 1.5가 1이 됨). |
| 부울 | true이면 부울 값을 1, false이면 부울 값으로 변환합니다. |

## 서명 및 반환된 유형

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

정수를 반환합니다.

## 예시

`toInteger("4")`

4를 반환합니다.
