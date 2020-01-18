---
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase 함수에 대해 알아보기
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


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

두 번째 인수 문자열이 있는 첫 번째 인수 문자열이 다른지 확인하고 대/소문자 고려 사항을 무시합니다.

## 카테고리

문자열

## 함수 구문

`notEqualWithIgnoreCase(<parameters>)`

## 매개 변수

* 문자열

## 서명 및 반환된 유형

`notEqualWithIgnoreCase(<string>,<string>)`

부울 값을 반환합니다.

## 예

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
