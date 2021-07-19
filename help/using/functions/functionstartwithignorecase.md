---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 28%

---

# startWithIgnoreCase {#startWithIgnoreCase}

두 번째 매개 변수가 대/소문자를 고려하지 않고 첫 번째 매개 변수의 접두사이면 true를 반환합니다.

## 카테고리

문자열

## 함수 구문

`startWithIgnoreCase(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-------------|--------|
| string | string |
| prefix로 인해 영구적으로 지정되는 Mbox 매개 변수입니다 | string |

## 서명 및 반환된 형식

`startWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예

`startWith("rowing is great', "RO")`

true를 반환합니다.
