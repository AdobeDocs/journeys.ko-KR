---
title: distinctWithNull
description: distinctWithNull 함수에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# distinctWithNull {#distinctWithNull}

목록의 고유한 값을 반환합니다. 목록에 Null 값이 하나 이상 있으면 반환 목록에 Null 값이 표시됩니다.

## 카테고리

목록

## 함수 구문

`distinctWithNull(<parameter>)`

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

`distinctWithNull(<listInteger>)`

정수 목록을 반환합니다.

`distinctWithNull(<listDecimal>)`

소수 목록을 반환합니다.

`distinctWithNull(<listString>)`

문자열 목록을 반환합니다.

`distinctWithNull(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`distinctWithNull(<listDateTime>)`

날짜 시간 목록을 반환합니다.

`distinctWithNull(<listBoolean>)`

부울 목록을 반환합니다.

`distinctWithNull(<listDuration>)`

기간 목록을 반환합니다.

## 예

`distinctWithNull([10,2,10,null])`

반환 [10, 2, null]
