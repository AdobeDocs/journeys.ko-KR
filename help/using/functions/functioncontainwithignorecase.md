---
product: adobe campaign
title: containIgnoreCase
description: containIgnoreCase 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 문자열 검색됨 | 문자열 |

## 서명 및 반환된 유형

`containIgnoreCase(<string>,<string>)`

부울 반환.

## 예

`containIgnoreCase("rowing is great", "GREAT")`

true를 반환합니다.
