---
title: serializeList
description: 함수 serializeList에 대해 알아봅니다.
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
source-wordcount: '86'
ht-degree: 15%

---


# serializeList {#serializeList}

첫 번째 매개 변수에 지정된 목록(모든 유형)을 문자열로 변환합니다. 두 번째 매개 변수는 사용할 구분 기호를 나타냅니다. 세 번째 매개 변수는 표현식의 각 요소에 따옴표가 포함되어야 하는지 여부를 나타내는 부울 값입니다.

## 범주

목록

## 함수 구문

`serializeList(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 부울 | 부울 |
| DateTimeOnly | DateTimeOnly |
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listPoint |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |

## 서명 및 반환된 문자

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

문자열을 반환합니다.

## 예제

`serializeList(["Hello","World"], " ", false)`

&quot;Hello World&quot;를 반환합니다.

`serializeList(["Hello", "World"], ",", true)`

&quot;&quot;Hello&quot;,&quot;World&quot;&quot;를 반환합니다.
