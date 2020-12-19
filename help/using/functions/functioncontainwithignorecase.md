---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: containWithIgnoreCase 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

---


# containWithIgnoreCase {#containWithIgnoreCase}

두 번째 인수 문자열이 대/소문자를 고려하지 않고 첫 번째 인수 문자열에 포함되어 있는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`containWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 문자열 검색 | 문자열 |

## 서명 및 반환된 유형

`containWithIgnoreCase(<string>,<string>)`

부울 값을 반환합니다.

## 예제

`containWithIgnoreCase("rowing is great', "GREAT")`

true를 반환합니다.
