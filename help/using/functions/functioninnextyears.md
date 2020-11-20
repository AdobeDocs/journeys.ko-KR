---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: NextYears의 기능에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextYears {#inNextYears}

주어진 날짜 또는 dateTime이 지금부터 현재 + 델타 연도 사이에 있으면 true를 반환합니다.

## 범주

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

부울을 반환합니다.

## 예제

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

true를 반환합니다.
