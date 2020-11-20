---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: 함수 endWithIgnoreCase에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 4%

---


# endWithIgnoreCase {#endWithIgnoreCase}

첫 번째 인수 문자열이 대/소문자를 고려하지 않고 특정 문자열(두 번째 인수 문자열)로 끝나는지 확인합니다.

## 범주

문자열

## 함수 구문

`endWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미어 | 문자열 |

## 서명 및 반환된 문자

`endWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예제

`endWithIgnoreCase("rowing is great', "AT")`

true를 반환합니다.
