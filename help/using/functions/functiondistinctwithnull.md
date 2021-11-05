---
product: adobe campaign
title: distinctWithNull
description: distinctWithNull 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 15%

---

# distinctWithNull {#distinctWithNull}

목록의 고유 값을 반환합니다. 목록에 Null 값이 하나 이상 있으면 Null 값이 반환된 목록에 표시됩니다.

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
| 목록 | listDateOnly |

## 서명 및 반환된 형식

`distinctWithNull(<listInteger>)`

정수 목록을 반환합니다.

`distinctWithNull(<listDecimal>)`

소수 목록을 반환합니다.

`distinctWithNull(<listString>)`

문자열 목록을 반환합니다.

`distinctWithNull(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`distinctWithNull(<listDateTime>)`

datetime 목록을 반환합니다.

`distinctWithNull(<listDateOnly>)`

날짜 목록을 반환합니다.

`distinctWithNull(<listBoolean>)`

부울 목록을 반환합니다.

`distinctWithNull(<listDuration>)`

지속 시간 목록을 반환합니다.

## 예시

`distinctWithNull([10,2,10,null])`

반환 [10, 2, null]
