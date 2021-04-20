---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: gstListItem 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

---


# getListItem {#gestListItem}

지정된 인덱스에 있는 목록의 항목을 반환합니다.

## 카테고리

목록

## 함수 구문

`getListItem(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| index | 정수 |

## 서명 및 반환된 유형

`getListItem(<listInteger>,<index>)`

정수 목록을 반환합니다.

`getListItem(<listDecimal>,<index>)`

소수점 목록을 반환합니다.

`getListItem(<listString>,<index>)`

문자열 목록을 반환합니다.

`getListItem(<listDateTimeOnly>,<index>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`getListItem(<listDateTime>,<index>)`

날짜 시간 목록을 반환합니다.

`getListItem(<listBoolean>,<index>)`

부울 목록을 반환합니다.

`getListItem(<listDuration>,<index>)`

기간 목록을 반환합니다.

## 예제

`getListItem([10, 2, 3], 1)`

&quot;2&quot;를 반환합니다.

`getListItem(["A", "B", "C"], 3)`
&quot;C&quot;를 반환합니다.

값이 있는 이벤트 필드 &#39;event.appVersion&#39;의 예:&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` 반환

`getListItem(split(@{event.appVersion}, "\\."), 0)`

&quot;20&quot;을 반환합니다.