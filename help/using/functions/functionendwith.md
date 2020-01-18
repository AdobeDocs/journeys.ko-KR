---
title: endWith
description: 함수 끝에 대한 자세한 정보사용
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
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7

---


# endWith {#endWith}

두 번째 매개 변수가 첫 번째 매개 변수의 접미어일 경우 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`endWith(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미사 | 문자열 |

## 서명 및 반환된 유형

`endWith(<string>,<string>)`

부울 값을 반환합니다.

## 예

`endWith("Hello World", "World")`

true를 반환합니다.

`endWith("Hello World", "Hello")`

false를 반환합니다.
