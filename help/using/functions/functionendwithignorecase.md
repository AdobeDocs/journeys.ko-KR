---
product: adobe campaign
title: endWithIgnoreCase
description: endWithIgnoreCase 함수 자세히 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
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
ht-degree: 18%
---
# endWithIgnoreCase {#endWithIgnoreCase}

첫 번째 인수 문자열이 대소문자를 고려하지 않고 특정 문자열(두 번째 인수 문자열)로 끝나는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`endWithIgnoreCase(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미사 | 문자열 |

## 서명 및 반환된 유형

`endWithIgnoreCase(<string>,<string>)`

부울 반환.

## 예

`endWithIgnoreCase("rowing is great", "AT")`

true를 반환합니다.
