---
title: toDateTime
description: toDateTime 함수에 대해 알아보기
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

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
| epoch의 정수 값(밀리초) | 정수 |

>[!NOTE]
>
>표준 시간대 ID는 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다. 데이터 유형에 대한 자세한 내용은 을 참조하십시오 [](../expression/data-types.md).

## 서명 및 반환된 유형

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

dateTime을 **반환합니다**.

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

## 예

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
