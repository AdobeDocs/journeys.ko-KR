---
product: adobe campaign
title: split
description: 함수 분할에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%

---

# split {#split}

첫 번째 인수 문자열을 구분 문자 문자열(정규 표현식일 수 있는 두 번째 인수 문자열)로 분할하여 문자열(토큰) 목록을 생성합니다.

## 카테고리

문자열

## 함수 구문

`split(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 입력 문자열 | 문자열 |
| 구분 문자 문자열 | 문자열 |

## 서명 및 반환된 유형

`split(<input string>, <separator string>)`

listString을 반환합니다.

## 예

`split(["A_B_C"], "_")`

`["A","B","C"]` 반환

값이 &quot;20.45.2.3434&quot;인 이벤트 필드 &#39;event.appVersion&#39;이 있는 예

`split(@{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` 반환
