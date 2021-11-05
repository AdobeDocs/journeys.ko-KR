---
product: adobe campaign
title: 함수
description: 기능에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 73%

---

# 함수 {#concept_p1r_qj5_dgb}

함수에는 서로 다른 서명(순서가 지정된 다른 매개 변수 세트)이 있을 수 있습니다. 함수 시그니처에는 순서가 지정된 매개 변수로 0-N 식이 있을 수 있습니다.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

각 함수에는 특정 반환 유형이 있습니다.

다음은 지원되는 함수 목록입니다.

## 기본 함수

| 카테고리 | 함수 |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| 집계 | [avg](../functions/functionavg.md) |
| 집계 | [count](../functions/functioncount.md) |
| 집계 | [countOnlyNull](../functions/functioncountonlynull.md) |
| 집계 | [countWithNull](../functions/functioncountwithnull.md) |
| 집계 | [distinctCount](../functions/functiondistinctcount.md) |
| 집계 | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| 집계 | [max](../functions/functionmax.md) |
| 집계 | [min](../functions/functionmin.md) |
| 집계 | [sum](../functions/functionsum.md) |
| 전환 | [toBool](../functions/functiontobool.md) |
| 전환 | [toDateOnly](../functions/functiontodateonly.md) |
| 전환 | [toDateTime](../functions/functiontodatetime.md) |
| 전환 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 전환 | [toDecimal](../functions/functiontodecimal.md) |
| 전환 | [toDuration](../functions/functiontoduration.md) |
| 전환 | [toInteger](../functions/functiontointeger.md) |
| 전환 | [toString](../functions/functiontostring.md) |
| 날짜 | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| 날짜 | [inLastDays](../functions/functioninlastdays.md) |
| 날짜 | [inLastHours](../functions/functioninlasthours.md) |
| 날짜 | [inLastMonths](../functions/functioninlastmonths.md) |
| 날짜 | [inLastYears](../functions/functioninlastyears.md) |
| 날짜 | [inNextDays](../functions/functioninnextdays.md) |
| 날짜 | [inNextHours](../functions/functioninnexthours.md) |
| 날짜 | [inNextMonths](../functions/functioninnextmonths.md) |
| 날짜 | [inNextYears](../functions/functioninnextyears.md) |
| 날짜 | [now](../functions/functionnow.md) |
| 날짜 | [nowWithDelta](../functions/functionnowwithdelta.md) |
| 날짜 | [setHours](../functions/functionsethours.md) |
| 날짜 | [setDays](../functions/functionsetdays.md) |
| 목록 | [distinct](../functions/functiondistinct.md) |
| 목록 | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| 목록 | [filter](../functions/functionfilter.md) |
| 목록 | [getListItem](../functions/functiongetlistitem.md) |
| 목록 | [in](../functions/functionin.md) |
| 목록 | [intersect](../functions/functionintersect.md) |
| 목록 | [listSize](../functions/functionlistsize.md) |
| 목록 | [serializeList](../functions/functionserializelist.md) |
| 목록 | [sort](../functions/functionsort.md) |
| 수학 | [random](../functions/functionrandom.md) |
| 수학 | [round](../functions/functionround.md) |
| 문자열 | [concat](../functions/functionconcat.md) |
| 문자열 | [contain](../functions/functioncontain.md) |
| 문자열 | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 문자열 | [endWith](../functions/functionendwith.md) |
| 문자열 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 문자열 | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| 문자열 | [indexOf](../functions/functionindexof.md) |
| 문자열 | [isEmpty](../functions/functionisempty.md) |
| 문자열 | [isNotEmpty](../functions/functionisnotempty.md) |
| 문자열 | [lastIndexOf](../functions/functionlastindexof.md) |
| 문자열 | [length](../functions/functionlength.md) |
| 문자열 | [lower](../functions/functionlower.md) |
| 문자열 | [matchRegExp](../functions/functionmatchregexp.md) |
| 문자열 | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| 문자열 | [replace](../functions/functionreplace.md) |
| 문자열 | [replaceAll](../functions/functionreplaceall.md) |
| 문자열 | [startWith](../functions/functionstartwith.md) |
| 문자열 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 문자열 | [substr](../functions/functionsubstr.md) |
| 문자열 | [trim](../functions/functiontrim.md) |
| 문자열 | [upper](../functions/functionupper.md) |
| 문자열 | [uuid](../functions/functionuuid.md) |
