---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 함수 종료에 대한 자세한 정보사용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# endWith {#endWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접미어일 경우 true를 반환합니다.

## 범주

문자열

## 함수 구문

`endWith(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미어 | 문자열 |

## 서명 및 반환된 문자

`endWith(<string>,<string>)`

부울을 반환합니다.

## 예제

`endWith("Hello World", "World")`

true를 반환합니다.

`endWith("Hello World", "Hello")`

false를 반환합니다.
