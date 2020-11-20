---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: 함수 정렬에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 10%

---


# sort {#sort}

값의 목록을 자연순으로 정렬합니다. 첫 번째 인수는 값 목록입니다. 두 번째는 오름차순(true) 또는 내림차순(false)인지 여부를 나타내는 부울 값입니다.

## 범주

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
| 부울 | 부울 |

## 서명 및 반환된 문자

`sort(<listInteger>,<boolean>)`

정수 목록을 반환합니다.

`sort(<listDecimal>,<boolean>)`

소수 목록을 반환합니다.

`sort(<listString>,<boolean>)`

문자열 목록을 반환합니다.

`sort(<listDateTimeOnly>,<boolean>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`sort(<listDateTime>,<boolean>)`

날짜 시간 목록을 반환합니다.

`sort(<listBoolean>,<boolean>)`

부울 목록을 반환합니다.

## 예제

`sort(["A", "C", "B"], true)`

반환 `["A","B","C"]`.

`sort([1, 3, 2], false)`

반환 `[3, 2, 1]`.
