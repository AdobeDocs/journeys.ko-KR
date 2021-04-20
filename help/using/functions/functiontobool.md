---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: toBool 기능에 대해 알아봅니다.
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# toBool {#toBool}

유형에 따라 인수 값을 부울 값으로 변환합니다.

* 문자열:문자열 값이 &quot;true&quot;이면 &quot;true&quot;이고, 그렇지 않으면 false로 문자열 값을 부울로 변환하려고 합니다.
* 숫자:숫자 값이 0이 아니면 true, 그렇지 않으면 false

## 카테고리

전환

## 함수 구문

`toBool(<parameter>)`

## 매개 변수

* decimal
* boolean
* 문자열
* 정수

## 서명 및 반환된 유형

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

부울 값을 반환합니다.

## 예제

`toBool("true")`

`toBool(1)`

true를 반환합니다.

`toBool("this is not a boolean")`

false를 반환합니다.
