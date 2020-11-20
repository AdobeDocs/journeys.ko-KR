---
product: adobe campaign
solution: Journey Orchestration
title: count
description: 함수 수에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 22%

---


# count {#count}

null 값을 고려하지 않는 목록의 요소를 카운트합니다.

## 범주

집계

## 함수 구문

`count(<listAny>)`

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

## 서명 및 반환된 문자

`count(<listAny>)`

정수를 반환합니다.

## 예제

`count([10,2,10,null])`

반환 3.
