---
product: adobe campaign
solution: Journey Orchestration
title: toDateTime
description: toDateTime 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# toDateTime {#toDateTime}

유형에 따라 매개 변수를 날짜 시간 값으로 변환합니다.

## 카테고리

전환

## 함수 구문

`toDateTime(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| ISO-8601 형식의 날짜 시간 | 문자열 |
| 시간대 ID | 문자열 |
| 시간대 없는 날짜 시간 | dateTimeOnly |
| epoch의 정수 값(밀리초 단위) | 정수 |

>[!NOTE]
>
>시간대 ID는 문자열 상수여야 합니다. 필드 참조나 표현식이 될 수 없습니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 서명 및 반환된 유형

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

**dateTime**&#x200B;을 반환합니다.

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

## 예제

`toDateTime ("2016-08-18T23:17:59.123Z")`

반환: 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

반환: 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

반환: 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
