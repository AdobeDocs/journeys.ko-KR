---
product: adobe campaign
title: sort
description: 함수 정렬에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 18%

---

# sort {#sort}

값 목록을 자연어 순서로 정렬합니다. 첫 번째 인수는 값 목록이고, 두 번째 인수는 정렬이 오름차순(true) 또는 내림차순(false)인지 여부를 나타내는 부울 값입니다.

## 카테고리

목록

## 함수 구문

`sort(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listInteger |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |
| 부울 | 부울 |

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

## 예

`sort(["A", "C", "B"], true)`

반환 `["A","B","C"]`.

`sort([1, 3, 2], false)`

반환 `[3, 2, 1]`.
