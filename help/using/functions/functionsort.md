---
product: adobe campaign
title: sort
description: 함수 정렬에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---

# sort {#sort}

값이나 개체 목록을 자연어 순서로 정렬합니다.

## 카테고리

목록

## 함수 구문

`sort(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 | 설명 |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly 또는 listObject | 정렬할 목록입니다. listObject의 경우 필드 참조여야 합니다. |
| keyAttributeName | string | 이 매개 변수는 listObject에만 사용됩니다. 지정된 목록의 개체에 있는 속성 이름이 정렬 키로 사용됩니다. |
| sortingOrder | 부울 | 오름차순(true) 또는 내림차순(false) |

## 서명 및 반환된 형식

`sort(<listInteger>,<boolean>)`

정수 목록을 반환합니다.

`sort(<listDecimal>,<boolean>)`

소수 목록을 반환합니다.

`sort(<listString>,<boolean>)`

문자열 목록을 반환합니다.

`sort(<listDateTimeOnly>,<boolean>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`sort(<listDateTime>,<boolean>)`

datetime 목록을 반환합니다.

`sort(<listDateOnly>,<boolean>)`

날짜 목록을 반환합니다.

`sort(<listBoolean>,<boolean>)`

부울 목록을 반환합니다.

`sort(<listObject>,<string>,<boolean>)`

개체 목록을 반환합니다.

## 예

`sort(["A", "C", "B"], true)`

반환 `["A","B","C"]`.

`sort([1, 3, 2], false)`

반환 `[3, 2, 1]`.

