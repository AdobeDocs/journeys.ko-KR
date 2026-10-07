---
product: adobe campaign
title: in
description: 의 기능에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
source-wordcount: '113'
ht-degree: 24%
---
# in {#in}

첫 번째 인수 값이 목록에 있는지 확인합니다. 각 인수 값에 대해 같음 을 통해 확인이 수행됩니다. 인수 값이 발견되면 true를 반환하고, 그렇지 않으면 false를 반환합니다.

`<expression>`의 형식은 목록의 항목과 일치해야 합니다. 미리 알림으로 목록의 항목 유형은 서로 일치해야 합니다.

## 카테고리

목록

## 함수 구문

`in(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 부울 | 부울 |
| 정수 | 정수 |
| 소수 | 소수 |
| 지속 시간 | 지속 시간 |
| 날짜/시간 | 날짜/시간 |
| 날짜/시간만 | 날짜/시간만 |
| 목록 | listString |
| 목록 | list부울 |
| 목록 | list정수 |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

부울 반환.

## 예

`in(4,[4,5,3,4])`

true를 반환합니다.

`in(8,[4,5,3,4])`

false를 반환합니다.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
