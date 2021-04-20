---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: startWithIgnoreCase 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# startWithIgnoreCase {#startWithIgnoreCase}

두 번째 매개 변수가 대/소문자를 고려하지 않고 첫 번째 매개 변수의 접두어인 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`startWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-------------|--------|
| 문자열 | 문자열 |
| 접두사 | 문자열 |

## 서명 및 반환된 유형

`startWithIgnoreCase(<string>,<string>)`

부울 값을 반환합니다.

## 예제

`startWith("rowing is great', "RO")`

true를 반환합니다.
