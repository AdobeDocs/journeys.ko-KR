---
product: adobe campaign
title: matchRegExp
description: matchRegExp 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 18%

---

# matchRegExp {#matchRegExp}

첫 번째 매개 변수의 문자열이 두 번째 매개 변수의 정규 표현식과 일치하면 true를 반환합니다. 자세한 내용은 [이 페이지](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## 카테고리

문자열

## 함수 구문

`matchRegExp(<parameters>)`

## 매개 변수

| 매개변수 | 유형 |
|--- |--- |
| 문자열 | 문자열 |
| regexp | 문자열 |

## 서명 및 반환된 유형

`matchRegExp(<string>,<string>)`

부울 반환.

## 예

`matchRegExp("username@adobe.com", "*adobe")`

true를 반환합니다.
