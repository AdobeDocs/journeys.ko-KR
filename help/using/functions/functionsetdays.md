---
title: setDays
description: 함수 집합에 대한 자세한 내용Days
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# setDays {#setDays}

날짜 시간 또는 날짜 시간만 설정합니다. 예를 들어 해당 월의 특정 요일까지 기다리려면 해당 요일을 강제할 수 있습니다.

## 카테고리

날짜

## 함수 구문

`setDays(<parameter>)`

## 매개 변수

| 매개 변수 | 유형 |
|--- |--- |
| 날짜 시간 | dateTime |
| 시간대를 고려하지 않고 | dateTimeOnly |
| 일 | 정수 |

## 서명 및 반환된 문자

`setDays(<dateTime>,<days>)`

datetime을 반환합니다.

`setDays(<dateTimeOnly>,<days>)`

시간대를 고려하지 않고 datetime을 반환합니다.

## 예

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z를 반환합니다.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
