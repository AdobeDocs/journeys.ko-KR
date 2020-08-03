---
title: substr
description: 함수 하위 문자열에 대한 자세한 내용
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
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 4%

---


# substr {#substr}

시작 인덱스와 끝 인덱스 사이의 문자열 식의 하위 문자열을 반환합니다. 끝 인덱스가 정의되지 않은 경우 시작 색인과 끝 사이에 있습니다.

## 범주

문자열

## 함수 구문

`substr(<parameters>)`

## 매개 변수

| 매개 변수 | type |
|-------------|----------|
| 문자열 | 문자열 |
| beginIndex | 정수 |
| endIndex | 정수 |

## 서명 및 반환된 문자

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

문자열을 반환합니다.

## 예

`substr("Hello World",6)`

&quot;World&quot;를 반환합니다.

`substr("Hello World", 0, 5)`

&quot;Hello&quot;를 반환합니다.