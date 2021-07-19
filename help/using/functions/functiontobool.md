---
product: adobe campaign
title: toBool
description: Bool에 대한 함수 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%

---

# toBool {#toBool}

인수 값을 유형에 따라 부울 값으로 변환합니다.

* 문자열: 문자열 값이 &quot;true&quot;이면 &quot;true&quot;에서 부울로 문자열 값을 변환하려고 하고, 그렇지 않으면 false입니다.
* 숫자: 숫자 값이 0이 아니면 true, 그렇지 않으면 false

## 카테고리

전환

## 함수 구문

`toBool(<parameter>)`

## 매개 변수

* 십진수
* 부울
* string
* 정수

## 서명 및 반환된 형식

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

부울을 반환합니다.

## 예

`toBool("true")`

`toBool(1)`

true를 반환합니다.

`toBool("this is not a boolean")`

false를 반환합니다.
