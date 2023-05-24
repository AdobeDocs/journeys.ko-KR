---
product: adobe campaign
title: containIgnoreCase
description: containIgnoreCase 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 22%

---

# containIgnoreCase {#containIgnoreCase}

두 번째 인수 문자열이 대소문자를 고려하지 않고 첫 번째 인수 문자열에 포함되어 있는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`containIgnoreCase(<parameters>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 문자열 검색됨 | 문자열 |

## 서명 및 반환된 유형

`containIgnoreCase(<string>,<string>)`

부울 반환.

## 예

`containIgnoreCase("rowing is great", "GREAT")`

true를 반환합니다.
