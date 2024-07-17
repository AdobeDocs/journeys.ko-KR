---
product: adobe campaign
title: toDateTime
description: 함수 toDateTime에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 2aa73498f44f22a70bb2268afca7d1a62e434542
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 11%

---

# toDateTime {#toDateTime}

유형에 따라 매개 변수를 날짜/시간 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateTime(<parameters>)`

## 매개 변수

| 매개변수 | 유형 |
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

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

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

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
