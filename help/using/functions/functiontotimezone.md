---
title: toTimeZone
description: toTimeZone 함수에 대해 알아보기
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# toTimeZone {#toTimeZone}

문자열 값을 표준 시간대로 변환합니다.

## 범주

전환

## 함수 구문

`toTimeZone(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값은 영역 ID를 포함해야 합니다. 필드 참조나 식이 될 수 있습니다 |

## 서명 및 반환된 유형

`toTimeZone(<string>)`

표준 시간대를 반환합니다.

## 예제

`toTimeZone("UTC")`

UTC를 반환합니다.
