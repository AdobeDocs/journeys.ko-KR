---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: 함수 바꾸기에 대해 자세히 알아보기All
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 6%

---


# replaceAll {#replaceAll}

대상 문자열과 일치하는 모든 항목을 기본 문자열의 대체 문자열로 바꿉니다.

바꾸기는 문자열의 시작 부분부터 끝 부분(예: 문자열 &quot;aaa&quot;에서 &quot;aa&quot;를 &quot;b&quot;로 바꾸면 &quot;ab&quot;가 아닌 &quot;ba&quot;가 됩니다.

## 카테고리

문자열

## 함수 구문

`replaceAll(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|--------------|
| 기본 | 문자열 |
| target | 문자열 |
| 교체 | 문자열 |

## 서명 및 반환된 유형

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

문자열을 반환합니다.

## 예제

`replaceAll("Hello World", "l", "x")`

&quot;Hexxo Worxd&quot;를 반환합니다.
