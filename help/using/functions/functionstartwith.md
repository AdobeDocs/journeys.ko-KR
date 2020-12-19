---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: startWith 함수
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# startWith {#startWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접두어인 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`startWith(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-------------|--------|
| 문자열 | 문자열 |
| 접두사 | 문자열 |

## 서명 및 반환된 유형

`startWith(<string>,<string>)`

부울 값을 반환합니다.

## 예제

`startWith("Hello World", "Hello")`

true를 반환합니다.

`startWith("Hello World", "World")`

false를 반환합니다.
