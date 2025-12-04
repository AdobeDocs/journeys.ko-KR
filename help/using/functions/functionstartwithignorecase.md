---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 함수에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 25%

---

# startWithIgnoreCase {#startWithIgnoreCase}

두 번째 매개 변수가 첫 번째 매개 변수의 접두사이면 대소문자를 고려하지 않고 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`startWithIgnoreCase(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-------------|--------|
| 문자열 | 문자열 |
| 접두사 | 문자열 |

## 서명 및 반환된 유형

`startWithIgnoreCase(<string>,<string>)`

부울 반환.

## 예

`startWithIgnoreCase("rowing is great", "RO")`

true를 반환합니다.
