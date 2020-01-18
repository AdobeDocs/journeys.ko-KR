---
title: toInteger
description: toInteger 함수에 대해 알아보기
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

---


# toInteger {#toInteger}

인수 값을 정수로 변환합니다.

## 카테고리

전환

## 함수 구문

`toInteger(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | 문자열 값을 정수로 변환합니다. |
| dateTime | 날짜를 밀리초 단위(epoch milliseconds)로 변환합니다. |
| decimal | decimal part(예:1.5가 1이 됨) |
| boolean | 부울 값을 true인 경우 1로, false인 경우 0으로 변환합니다. |

## 서명 및 반환된 문자

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

정수를 반환합니다.

## 예

`toInteger(4)`

반환 4입니다.
