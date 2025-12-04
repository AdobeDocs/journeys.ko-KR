---
product: adobe campaign
title: startWith
description: startWith 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# startWith {#startWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접두사인 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`startWith(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-------------|--------|
| 문자열 | 문자열 |
| 접두사 | 문자열 |

## 서명 및 반환된 유형

`startWith(<string>,<string>)`

부울 반환.

## 예

`startWith("Hello World", "Hello")`

true를 반환합니다.

`startWith("Hello World", "World")`

false를 반환합니다.
