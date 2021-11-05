---
product: adobe campaign
title: notEqualIgnoreCase
description: notEqualIgnoreCase 함수에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

대/소문자 고려 사항을 무시하고 두 번째 인수 문자열이 들어 있는 첫 번째 인수 문자열이 다른지 확인하십시오.

## 카테고리

문자열

## 함수 구문

`notEqualIgnoreCase(<parameters>)`

## 매개 변수

* string

## 서명 및 반환된 형식

`notEqualIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
