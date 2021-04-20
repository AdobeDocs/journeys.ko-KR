---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 함수 바꾸기에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# replace {#replace}

대상 문자열과 일치하는 첫 번째 항목을 기본 문자열의 대체 문자열로 바꿉니다.

바꾸기는 문자열의 시작 부분부터 끝 부분(예: 문자열 &quot;aaa&quot;에서 &quot;aa&quot;를 &quot;b&quot;로 바꾸면 &quot;ab&quot;가 아닌 &quot;ba&quot;가 됩니다.

## 카테고리

문자열

## 함수 구문

`replace(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|--------------|
| 기본 | 문자열 |
| target | 문자열 |
| 교체 | 문자열 |

## 서명 및 반환된 유형

`replace(<base>,<target>,<replacement>)`

문자열을 반환합니다.

## 예제

`replace("Hello World", "l", "x")`

&quot;Hexlo World&quot;를 반환합니다.
