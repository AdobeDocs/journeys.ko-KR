---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: 함수 정렬에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---


# sort {#sort}

자연스러운 순서로 값 목록을 정렬합니다. 첫 번째 인수는 값 목록입니다. 두 번째 인수는 정렬이 오름차순(true) 또는 내림차순(false)인지 여부를 나타내는 부울 값입니다.

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
| 부울 | 부울 |

## 서명 및 반환된 유형

`sort(<listInteger>,<boolean>)`

정수 목록을 반환합니다.

`sort(<listDecimal>,<boolean>)`

소수점 목록을 반환합니다.

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

`["A","B","C"]`을(를) 반환합니다.

`sort([1, 3, 2], false)`

`[3, 2, 1]`을(를) 반환합니다.
