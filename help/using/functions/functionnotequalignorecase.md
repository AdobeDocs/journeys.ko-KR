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
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

두 번째 인수 문자열이 있는 첫 번째 인수 문자열이 다른 경우 대/소문자 고려 사항을 무시하고 있는지 확인하십시오.

## 범주

문자열

## 함수 구문

`notEqualWithIgnoreCase(<parameters>)`

## 매개 변수

* 문자열

## 서명 및 반환된 문자

`notEqualWithIgnoreCase(<string>,<string>)`

부울을 반환합니다.

## 예제

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
