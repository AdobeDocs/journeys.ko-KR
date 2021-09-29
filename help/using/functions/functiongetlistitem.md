---
product: adobe campaign
title: getListItem
description: gstListItem 함수에 대해 알아봅니다
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 21%

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
| 목록에 있는 참조 페이지를 나타냅니다 | listString |
| 목록에 있는 참조 페이지를 나타냅니다 | listBoolean |
| 목록에 있는 참조 페이지를 나타냅니다 | listInteger |
| 목록에 있는 참조 페이지를 나타냅니다 | listDecimal |
| 목록에 있는 참조 페이지를 나타냅니다 | listDuration |
| 목록에 있는 참조 페이지를 나타냅니다 | listDateTime |
| 목록에 있는 참조 페이지를 나타냅니다 | listDateTimeOnly |
| 목록에 있는 참조 페이지를 나타냅니다 | listDateOnly |
| 색인 | 정수 |

## 서명 및 반환된 유형

`getListItem(<listInteger>,<index>)`

정수를 반환합니다.

`getListItem(<listDecimal>,<index>)`

소수점 반환

`getListItem(<listString>,<index>)`

문자열을 반환합니다.

`getListItem(<listDateTimeOnly>,<index>)`

시간대를 고려하지 않고 datetime을 반환합니다.

`getListItem(<listDateTime>,<index>)`

datetime을 반환합니다.

`getListItem(<listBoolean>,<index>)`

부울을 반환합니다.

`getListItem(<listDuration>,<index>)`

지속 시간을 반환합니다.

## 예

`getListItem([10, 2, 3], 1)`

&quot;2&quot;를 반환합니다.

`getListItem(["A", "B", "C"], 2)`
&quot;C&quot;를 반환합니다.

값이 있는 이벤트 필드 &#39;event.appVersion&#39;의 예: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

반환 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

&quot;20&quot;을 반환합니다.
