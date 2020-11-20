---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: 함수 이해
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 12%

---


# concat {#concat}

두 문자열 매개 변수 또는 문자열 목록을 연결합니다.

## 범주

문자열

## 함수 구문

`concat(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 문자열 | 문자열 |

## 서명 및 반환된 문자

`concat(<string>,<string>)`

`concat(<listString>)`

문자열을 반환합니다.

## 예제

`concat("Hello","World")`

&quot;HelloWorld&quot;를 반환합니다.

`concat(["Hello"," ","World"])`

&quot;Hello World&quot;를 반환합니다.
