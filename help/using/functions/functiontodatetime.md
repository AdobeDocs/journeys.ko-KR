---
product: adobe campaign
title: toDateTime
description: 함수 toDateTime에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
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
source-wordcount: '97'
ht-degree: 11%
---
# toDateTime {#toDateTime}

유형에 따라 매개 변수를 날짜/시간 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateTime(<parameters>)`

## 매개변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 형식의 날짜 시간 | 문자열 |
| 시간대 id | 문자열 |
| 시간대 없는 날짜 시간 | dateTimeOnly |
| 에포크의 정수 값(밀리초) | 정수 |

>[!NOTE]
>
>시간대 ID는 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 서명 및 반환된 유형

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

**dateTime** 반환

<!--
`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## 예시

`toDateTime ("2016-08-18T23:17:59.123Z")`

2016-08-18T23 반환:17:59.123Z

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

2016-08-18T23 반환:17:59.123Z

`toDateTime(1560762190189)`

2019-06-17T09:03:10.189Z 반환

<!--
`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.
-->
