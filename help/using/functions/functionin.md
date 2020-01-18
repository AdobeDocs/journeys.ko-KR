---
title: in
description: 함수에 대한 자세한 내용은
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


# in {#in}

첫 번째 인수 값이 목록에 있는지 확인합니다. 각 인수 값에 대해 Equal를 통해 검사가 수행됩니다. 인수 값이 있으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

목록 유형이 목록의 항목과 일치해야 `<expression>` 합니다. 목록의 항목 유형은 미리 알림으로 서로 일치해야 합니다.

## 카테고리

목록

## 함수 구문

`in(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 문자열 | 문자열 |
| 부울 | 부울 |
| 정수 | 정수 |
| 십진수 | 십진수 |
| 지속 시간 | 지속 시간 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listInteger |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |

## 서명 및 반환된 유형

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

부울 값을 반환합니다.

## 예

`in(4,[4,5,3,4])`

true를 반환합니다.

`in(8,[4,5,3,4])`

false를 반환합니다.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
