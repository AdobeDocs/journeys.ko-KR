---
product: adobe campaign
title: toDecimal
description: toDecimal 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 소수로 변환합니다. |
| dateTime | 날짜를 밀리초 단위로 변환(에포크 밀리초) |
| 부울 | true이면 부울 값을 1, false이면 부울 값으로 변환합니다. |
| 정수 | 소수로 변환(예: 1이 1.0이 됨) |

## 서명 및 반환된 유형

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

십진수를 반환합니다.

## 예시

`toDecimal("4.0")`

4.0을 반환합니다
