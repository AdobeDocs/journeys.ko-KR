---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: 고유한 기능에 대해 알아봅니다.
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 13%

---


# distinct {#distinct}

null 값 없이 목록의 고유한 값을 반환합니다.

## 카테고리

목록

## 함수 구문

`distinct(<parameter>)`

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

## 서명 및 반환된 유형

`distinct(<listInteger>)`

정수 목록을 반환합니다.

`distinct(<listDecimal>)`

소수점 목록을 반환합니다.

`distinct(<listString>)`

문자열 목록을 반환합니다.

`distinct(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`distinct(<listDateTime>)`

날짜 시간 목록을 반환합니다.

`distinct(<listBoolean>)`

부울 목록을 반환합니다.

`distinct(<listDuration>)`

기간 목록을 반환합니다.

## 예제

`distinct([10,2,10,null])`

`[10, 2]`을(를) 반환합니다.
