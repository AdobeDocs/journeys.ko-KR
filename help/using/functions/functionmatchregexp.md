---
title: matchRegExp
description: 함수 matchRegExp에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

첫 번째 매개 변수의 문자열이 두 번째 매개 변수의 정규 표현식과 일치하는 경우 true를 반환합니다. 자세한 내용은 [이 페이지를 참조하십시오](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## 범주

문자열

## 함수 구문

`matchRegExp(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 문자열 | 문자열 |
| regexp | 문자열 |

## 서명 및 반환된 문자

`matchRegExp(<string>,<string>)`

true를 반환합니다.

## 예제

`matchRegExp("Hello World", "Hello\s+World")`

true를 반환합니다.

설명:

여기에서 문자열이 정규 표현식(java 구문)을 충족하는지 확인합니다. 다음으로 시작하고 모든 종류의 문자열을 &quot;World&quot;로 끝냅니다.
