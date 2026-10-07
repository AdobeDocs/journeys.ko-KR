---
product: adobe campaign
title: toString
description: 함수 toString에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 9%
---
# toString {#toString}

인수 유형에 따라 인수 값을 문자열 값으로 변환합니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

전환

## 함수 구문

`toString(<parameter>)`

## 매개변수

| 매개 변수 | 설명 |
|--- |--- |
| dateTime | 날짜를 UTC 날짜 형식으로 변환 |
| dateTimeOnly | 날짜를 UTC 날짜 형식으로 변환 |
| 지속 시간 | 문자열로 해당 시간(밀리초)으로 변환 |
| 정수 | 를 값의 문자열 표현으로 변환합니다(1은 &quot;1&quot;이 됨). |
| decimal | 를 값의 문자열 표현으로 변환(1.5가 &quot;1.5&quot;가 됨) |
| 부울 | true이면 &#39;true&#39;로, false이면 &#39;false&#39;로 부울 값 변환 |

## 서명 및 반환된 유형

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

문자열을 반환합니다.

## 예

`toString(4)`

&quot;4&quot;를 반환합니다.
