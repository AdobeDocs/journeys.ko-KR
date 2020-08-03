---
title: concat
description: 함수 이해
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
source-wordcount: '40'
ht-degree: 10%

---


# concat {#concat}

두 문자열 매개 변수 또는 문자열 목록을 연결합니다.

## 범주

문자열

## 함수 구문

`concat(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 문자열 | 문자열 |

## 서명 및 반환된 문자

`concat(<string>,<string>)`

`concat(<listString>)`

문자열을 반환합니다.

## 예

`concat("Hello","World")`

&quot;HelloWorld&quot;를 반환합니다.

`concat(["Hello"," ","World"])`

&quot;Hello World&quot;를 반환합니다.
