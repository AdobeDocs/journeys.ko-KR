---
title: inNextYears
description: 향후 기능 살펴보기
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
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49

---


# inNextYears {#inNextYears}

주어진 날짜 또는 dateTime이 현재 + 델타 연도 사이에 있으면 true를 반환합니다.

## 카테고리

날짜

## 함수 구문

`inNextYears(<dateTime>,<delta>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 날짜 시간 | dateTime |
| 델타 | 정수 |

## 서명 및 반환된 문자

`inNextYears(<dateTime>,<integer>)`

부울 값을 반환합니다.

## 예

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

true를 반환합니다.
