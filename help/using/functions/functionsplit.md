---
product: adobe campaign
solution: Journey Orchestration
title: split
description: 함수 분할에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 7%

---


# split {#split}

문자열(토큰) 목록을 만들기 위해 구분 문자열(정규 표현식이 될 수 있는 두 번째 인수 문자열)로 첫 번째 인수 문자열을 분할합니다.

## 카테고리

문자열

## 함수 구문

`split(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 입력 문자열 | 문자열 |
| 구분 문자열 | 문자열 |

## 서명 및 반환된 유형

`split(<input string>, <separator string>)`

listString을 반환합니다.

## 예제

`split(["A_B_C"], "_")`

`["A","B","C"]` 반환

값이 있는 이벤트 필드 &#39;event.appVersion&#39;의 예:&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` 반환
