---
product: adobe campaign
title: endWith
description: endWith 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접미사인 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`endWith(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미사 | 문자열 |

## 서명 및 반환된 유형

`endWith(<string>,<string>)`

부울 반환.

## 예

`endWith("Hello World", "World")`

true를 반환합니다.

`endWith("Hello World", "Hello")`

false를 반환합니다.
