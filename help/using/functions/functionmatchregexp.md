---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: matchRegExp 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

첫 번째 매개 변수의 문자열이 두 번째 매개 변수의 정규 표현식과 일치하면 true를 반환합니다. 자세한 내용은 [이 페이지](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)를 참조하십시오.

## 카테고리

문자열

## 함수 구문

`matchRegExp(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 문자열 | 문자열 |
| regexp | 문자열 |

## 서명 및 반환된 유형

`matchRegExp(<string>,<string>)`

true를 반환합니다.

## 예제

`matchRegExp("Hello World", "Hello\s+World")`

true를 반환합니다.

설명:

여기에서 문자열이 정규 표현식(java 구문)을 충족하는지 확인합니다.&quot;Hello&quot;로 시작하고 모든 종류의 문자열을 &quot;World&quot;로 끝냅니다.
