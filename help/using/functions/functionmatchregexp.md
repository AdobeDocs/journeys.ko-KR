---
product: adobe campaign
title: matchRegExp
description: matchRegExp 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 13%

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
| string | string |
| regexp | string |

## 서명 및 반환된 형식

`matchRegExp(<string>,<string>)`

true를 반환합니다.

## 예

`matchRegExp("Hello World", "Hello\s+World")`

true를 반환합니다.

설명:

여기에서 문자열이 정규 표현식(java 구문)을 충족하는지 확인합니다. &quot;Hello&quot;로 시작하는 다음, 임의의 문자열로 시작하여 &quot;World&quot;로 끝납니다.
