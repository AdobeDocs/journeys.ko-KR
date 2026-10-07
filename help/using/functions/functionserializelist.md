---
product: adobe campaign
title: serializeList
description: serializeList 함수에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 22%
---
# serializeList {#serializeList}

첫 번째 매개 변수에 지정된 목록(모든 유형)을 문자열로 변환합니다. 두 번째 매개 변수는 사용할 구분 기호를 나타냅니다. 세 번째 매개 변수는 표현식의 각 요소에 따옴표가 포함되어야 하는지 여부를 나타내는 부울 값입니다.

## 카테고리

목록

## 함수 구문

`serializeList(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 부울 | 부울 |
| 날짜/시간만 | 날짜/시간만 |
| 목록 | listString |
| 목록 | list부울 |
| 목록 | listPoint |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

문자열을 반환합니다.

## 예

`serializeList(["Hello","World"], " ", false)`

&quot;Hello World&quot;를 반환합니다.

`serializeList(["Hello", "World"], ",", true)`

&quot;&quot;Hello&quot;,&quot;World&quot;&quot;를 반환합니다.
