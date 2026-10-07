---
product: adobe campaign
title: sort
description: 함수 정렬에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
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
source-wordcount: '131'
ht-degree: 8%
---
# sort {#sort}

값 또는 개체 목록을 원래 순서로 정렬합니다.

## 카테고리

목록

## 함수 구문

`sort(<parameters>)`

## 매개변수

| 매개 변수 | 유형 | 설명 |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly 또는 listObject | 정렬할 목록입니다. listObject의 경우 필드 참조여야 합니다. |
| keyAttributeName | 문자열 | 이 매개 변수는 listObject에만 사용할 수 있습니다. 해당 목록의 개체에 있는 특성 이름은 정렬의 키로 사용됩니다. |
| 정렬 순서 | 부울 | 오름차순(true) 또는 내림차순(false) |

## 서명 및 반환된 유형

`sort(<listInteger>,<boolean>)`

정수 목록을 반환합니다.

`sort(<listDecimal>,<boolean>)`

소수점 목록을 반환합니다.

`sort(<listString>,<boolean>)`

문자열 목록을 반환합니다.

`sort(<listDateTimeOnly>,<boolean>)`

시간대를 고려하지 않고 날짜/시간 목록을 반환합니다.

`sort(<listDateTime>,<boolean>)`

날짜/시간 목록을 반환합니다.

`sort(<listDateOnly>,<boolean>)`

날짜 목록을 반환합니다.

`sort(<listBoolean>,<boolean>)`

부울 목록을 반환합니다.

`sort(<listObject>,<string>,<boolean>)`

개체 목록을 반환합니다.

## 예

`sort(["A", "C", "B"], true)`

`["A","B","C"]`을(를) 반환합니다

`sort([1, 3, 2], false)`

`[3, 2, 1]`을(를) 반환합니다

