---
title: distinctCount
description: distinctCount 함수에 대한 자세한 내용
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
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 23%

---


# distinctCount{#distinctCount}

null 값을 무시하고 있는 다른 값의 수를 카운트합니다.

## 범주

집계

## 함수 구문

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

정수를 반환합니다.

## 예제

`distinctCount([10,2,10,null])`

2를 반환합니다.
