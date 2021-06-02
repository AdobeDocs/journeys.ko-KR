---
product: adobe campaign
title: getListItem
description: gstListItem 함수에 대해 알아봅니다
feature: 여정
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 6%

---

# getListItem {#gestListItem}

지정된 인덱스에서 목록의 항목을 반환합니다.

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
| 색인 | 정수 |

## 서명 및 반환된 유형

`getListItem(<listInteger>,<index>)`

정수 목록을 반환합니다.

`getListItem(<listDecimal>,<index>)`

소수 목록을 반환합니다.

`getListItem(<listString>,<index>)`

문자열 목록을 반환합니다.

`getListItem(<listDateTimeOnly>,<index>)`

시간대를 고려하지 않고 날짜 시간 목록을 반환합니다.

`getListItem(<listDateTime>,<index>)`

datetime 목록을 반환합니다.

`getListItem(<listBoolean>,<index>)`

부울 목록을 반환합니다.

`getListItem(<listDuration>,<index>)`

지속 시간 목록을 반환합니다.

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
