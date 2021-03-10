---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: 함수 하위 문자열에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

시작 인덱스와 끝 인덱스 사이의 문자열 표현식의 하위 문자열을 반환합니다. 끝 인덱스가 정의되지 않은 경우 시작 색인과 끝 사이의 인덱스입니다.

## 카테고리

문자열

## 함수 구문

`substr(<parameters>)`

## 매개 변수

| 매개 변수 | type |
|-------------|----------|
| 문자열 | 문자열 |
| beginIndex | 정수 |
| endIndex | 정수 |

## 서명 및 반환된 유형

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

문자열을 반환합니다.

## 예제

`substr("Hello World",6)`

&quot;World&quot;를 반환합니다.

`substr("Hello World", 0, 5)`

&quot;Hello&quot;를 반환합니다.