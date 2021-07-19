---
product: adobe campaign
title: containWithIgnoreCase
description: containWithIgnoreCase 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---

# containWithIgnoreCase {#containWithIgnoreCase}

대/소문자를 고려하지 않고 두 번째 인수 문자열이 첫 번째 인수 문자열에 포함되어 있는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`containWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| string | string |
| 검색된 문자열 | string |

## 서명 및 반환된 형식

`containWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예

`containWithIgnoreCase("rowing is great', "GREAT")`

true를 반환합니다.
