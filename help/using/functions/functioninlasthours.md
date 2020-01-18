---
title: inLastHours
description: LastHours의 기능에 대한 자세한 내용
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


# inLastHours {#inLastHours}

주어진 날짜 시간이 지금부터 현재 시간(델타 시간) 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inLastHours(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 문자

`inLastHours(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

true를 반환합니다.

`inLastHours(@{MyEvent.timestamp}, 4)`

true를 반환합니다.
