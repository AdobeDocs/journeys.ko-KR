---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase 함수에 대해 알아보기
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

두 번째 인수 문자열이 있는 첫 번째 인수 문자열이 다르는지 여부를 확인하십시오. 이때 대소문자 고려 사항은 무시됩니다.

## 카테고리

문자열

## 함수 구문

`notEqualWithIgnoreCase(<parameters>)`

## 매개 변수

* 문자열

## 서명 및 반환된 유형

`notEqualWithIgnoreCase(<string>,<string>)`

부울 값을 반환합니다.

## 예제

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
