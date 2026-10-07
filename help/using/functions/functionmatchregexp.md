---
product: adobe campaign
title: matchRegExp
description: matchRegExp 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
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
source-wordcount: '61'
ht-degree: 18%
---
# matchRegExp {#matchRegExp}

첫 번째 매개 변수의 문자열이 두 번째 매개 변수의 정규 표현식과 일치하면 true를 반환합니다. 자세한 내용은 [이 페이지](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)를 참조하세요.

## 카테고리

문자열

## 함수 구문

`matchRegExp(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|--- |--- |
| 문자열 | 문자열 |
| regexp | 문자열 |

## 서명 및 반환된 유형

`matchRegExp(<string>,<string>)`

부울 반환.

## 예

`matchRegExp("username@adobe.com", "*adobe")`

true를 반환합니다.
