---
product: adobe campaign
title: endWithIgnoreCase
description: endWithIgnoreCase 함수 자세히 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# endWithIgnoreCase {#endWithIgnoreCase}

첫 번째 인수 문자열이 대소문자를 고려하지 않고 특정 문자열(두 번째 인수 문자열)로 끝나는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`endWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 접미사 | 문자열 |

## 서명 및 반환된 유형

`endWithIgnoreCase(<string>,<string>)`

부울 반환.

## 예

`endWithIgnoreCase("rowing is great", "AT")`

true를 반환합니다.
