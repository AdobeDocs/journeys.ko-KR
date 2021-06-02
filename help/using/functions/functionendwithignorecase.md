---
product: adobe campaign
title: endWithIgnoreCase
description: 함수 endWithIgnoreCase에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---

# endWithIgnoreCase {#endWithIgnoreCase}

첫 번째 인수 문자열이 대/소문자를 고려하지 않고 특정 문자열(두 번째 인수 문자열)로 끝나는지 확인합니다.

## 카테고리

문자열

## 함수 구문

`endWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| string | string |
| 접미사 | string |

## 서명 및 반환된 형식

`endWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예제

`endWithIgnoreCase("rowing is great', "AT")`

true를 반환합니다.
