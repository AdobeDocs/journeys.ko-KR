---
title: toBool
description: toBool 기능에 대한 자세한 내용
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


# toBool {#toBool}

인수 값의 유형에 따라 인수 값을 부울 값으로 변환합니다.

* 문자열:문자열 값이 &quot;true&quot;이면 &quot;true&quot;이고, 그렇지 않으면 false인 경우 문자열 값을 부울로 변환하려고 합니다.
* 숫자:숫자 값이 0과 같지 않으면 true, 그렇지 않으면 false

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

## 예

`toBool("true")`

`toBool(1)`

true를 반환합니다.

`toBool("this is not a boolean")`

false를 반환합니다.
