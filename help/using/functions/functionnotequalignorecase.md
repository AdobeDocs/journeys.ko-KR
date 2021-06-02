---
product: adobe campaign
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 15%

---

# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

대/소문자 고려 사항을 무시하고 두 번째 인수 문자열이 들어 있는 첫 번째 인수 문자열이 다른지 확인하십시오.

## 카테고리

문자열

## 함수 구문

`notEqualWithIgnoreCase(<parameters>)`

## 매개 변수

* string

## 서명 및 반환된 형식

`notEqualWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예제

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
