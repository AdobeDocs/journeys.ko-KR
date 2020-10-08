---
title: containWithIgnoreCase
description: 함수에서 containWithIgnoreCase에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

---


# containWithIgnoreCase {#containWithIgnoreCase}

첫 번째 인수 문자열에 두 번째 인수 문자열이 들어 있는지, 대/소문자를 고려하지 않고 있는지 확인합니다.

## 범주

문자열

## 함수 구문

`containWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 문자열 검색 | 문자열 |

## 서명 및 반환된 문자

`containWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예제

`containWithIgnoreCase("rowing is great', "GREAT")`

true를 반환합니다.
