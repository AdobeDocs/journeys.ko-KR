---
product: adobe campaign
title: getListItem
description: gstListItem 함수에 대해 알아봅니다.
feature: Journeys
role: Developer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 19%

---

# getListItem {#gestListItem}

지정된 인덱스에서 목록의 항목을 반환합니다.

## 카테고리

목록

## 함수 구문

`getListItem(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| list | listString |
| list | list부울 |
| list | list정수 |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| 색인 | 정수 |

## 서명 및 반환된 유형

`getListItem(<listInteger>,<index>)`

정수 반환.

`getListItem(<listDecimal>,<index>)`

십진수를 반환합니다.

`getListItem(<listString>,<index>)`

문자열을 반환합니다.

`getListItem(<listDateTimeOnly>,<index>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

`getListItem(<listDateTime>,<index>)`

날짜/시간을 반환합니다.

`getListItem(<listDateOnly>,<index>)`

날짜 목록을 반환합니다.

`getListItem(<listBoolean>,<index>)`

부울 반환.

`getListItem(<listDuration>,<index>)`

기간을 반환합니다.

## 예

`getListItem([10, 2, 3], 1)`

&quot;2&quot; 반환

`getListItem(["A", "B", "C"], 2)`
&quot;C&quot; 반환

값이 &quot;20.45.2.3434&quot;인 이벤트 필드 &#39;event.appVersion&#39;이 있는 예

`split(@{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` 반환

`getListItem(split(@{event.appVersion}, "\\."), 0)`

&quot;20&quot; 반환
