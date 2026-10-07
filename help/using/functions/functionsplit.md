---
product: adobe campaign
title: split
description: 함수 분할에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 15%
---
# split {#split}

첫 번째 인수 문자열을 구분 문자 문자열(정규 표현식일 수 있는 두 번째 인수 문자열)로 분할하여 문자열(토큰) 목록을 생성합니다.

## 카테고리

문자열

## 함수 구문

`split(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
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
