---
title: endWithIgnoreCase
description: 함수 endWithIgnoreCase에 대해 알아보기
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
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 2%

---


# endWithIgnoreCase {#endWithIgnoreCase}

첫 번째 인수 문자열이 대/소문자를 고려하지 않고 특정 문자열(두 번째 인수 문자열)로 끝나는지 확인합니다.

## 범주

문자열

## 함수 구문

`endWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미어 | 문자열 |

## 서명 및 반환된 문자

`endWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예

`endWithIgnoreCase("rowing is great', "AT")`

true를 반환합니다.
