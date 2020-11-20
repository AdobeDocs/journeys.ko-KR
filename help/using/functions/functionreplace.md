---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 함수 바꾸기에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# replace {#replace}

대상 문자열과 일치하는 첫 번째 항목을 기본 문자열의 대체 문자열로 바꿉니다.

바꾸기는 문자열 시작에서 끝까지 진행되며, 예를 들어 문자열 &quot;aaa&quot;에서 &quot;aa&quot;를 &quot;b&quot;로 바꾸면 &quot;ab&quot;가 아닌 &quot;ba&quot;가 됩니다.

## 범주

문자열

## 함수 구문

`replace(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|--------------|
| 기본 | 문자열 |
| target | 문자열 |
| 교체 | 문자열 |

## 서명 및 반환된 문자

`replace(<base>,<target>,<replacement>)`

문자열을 반환합니다.

## 예제

`replace("Hello World", "l", "x")`

&quot;Hexlo World&quot;를 반환합니다.
