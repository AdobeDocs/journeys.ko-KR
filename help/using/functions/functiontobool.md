---
product: adobe campaign
title: toBool
description: toBool 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# toBool {#toBool}

인수 유형에 따라 인수 값을 부울 값으로 변환합니다.

* From string: 문자열 값을 부울로 변환하고 문자열 값이 &quot;true&quot;이면 &quot;true&quot;를 반환하고 그렇지 않으면 false를 반환합니다
* 숫자에서: 숫자 값이 0이 아니면 true이고, 그렇지 않으면 false입니다

## 카테고리

전환

## 함수 구문

`toBool(<parameter>)`

## 매개변수

* decimal
* 부울
* 문자열
* 정수

## 서명 및 반환된 유형

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

부울 반환.

## 예시

`toBool("true")`

`toBool(1)`

true를 반환합니다.

`toBool("this is not a boolean")`

false를 반환합니다.
