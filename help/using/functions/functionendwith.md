---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 끝 함수에 대한 자세한 정보사용
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# endWith {#endWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접미어인 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`endWith(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미어 | 문자열 |

## 서명 및 반환된 유형

`endWith(<string>,<string>)`

부울 값을 반환합니다.

## 예제

`endWith("Hello World", "World")`

true를 반환합니다.

`endWith("Hello World", "Hello")`

false를 반환합니다.
