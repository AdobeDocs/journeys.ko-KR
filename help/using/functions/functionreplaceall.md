---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: 함수 바꾸기에 대한 자세한 정보모두
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%

---


# replaceAll {#replaceAll}

대상 문자열과 일치하는 모든 항목을 기본 문자열의 대체 문자열로 바꿉니다.

바꾸기는 문자열 시작에서 끝까지 진행되며, 예를 들어 문자열 &quot;aaa&quot;에서 &quot;aa&quot;를 &quot;b&quot;로 바꾸면 &quot;ab&quot;가 아닌 &quot;ba&quot;가 됩니다.

## 범주

문자열

## 함수 구문

`replaceAll(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|--------------|
| 기본 | 문자열 |
| target | 문자열 |
| 교체 | 문자열 |

## 서명 및 반환된 문자

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

문자열을 반환합니다.

## 예제

`replaceAll("Hello World", "l", "x")`

&quot;Hexxo Worxd&quot;를 반환합니다.
