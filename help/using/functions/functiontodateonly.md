---
product: adobe campaign
title: toDateOnly
description: toDateOnly 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

인수 값을 날짜 전용 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateOnly(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 또는 &quot;YYYY-MM-DD&quot; 형식(XDM 날짜 형식)의 날짜 | string |
| 날짜 | 날짜 |

## 서명 및 반환된 형식

`toDateOnly(<date>)`

`toDateOnly(<string>)`

시간대를 고려하지 않고 날짜/시간을 반환합니다.

## 예시

`toDateOnly("2016-08-18")`

2016-08-18을 나타내는 dateOnly 개체를 반환합니다.
