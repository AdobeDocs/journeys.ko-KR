---
title: 함수
description: 기능에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: ac2ca77e2ba7c56217199dbd487f57cfe207f7d7
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 73%

---


# 함수 {#concept_p1r_qj5_dgb}

함수에는 서로 다른 서명(순서가 다른 매개 변수 세트)이 있을 수 있습니다. 함수 서명에 지정된 매개 변수로 0N 식을 사용할 수 있습니다.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

각 함수에는 특정 반환 형식이 있습니다.

다음은 지원되는 함수 목록입니다.

## 주요 함수

| 범주 | 함수 |
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
| 목록 | [distinctCount](../functions/functiondistinctcount.md) |
| 목록 | [in](../functions/functionin.md) |
| 목록 | [listSize](../functions/functionlistsize.md) |
| 목록 | [serializeList](../functions/functionserializelist.md) |
| 목록 | [sort](../functions/functionsort.md) |
| 수학 | [random](../functions/functionrandom.md) |
| 수학 | [round](../functions/functionround.md) |
| 문자열 | [concat](../functions/functionconcat.md) |
| 문자열 | [contain](../functions/functioncontain.md) |
| 문자열 | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 문자열 | [endWith](../functions/functionendwith.md) |
| 문자열 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 문자열 | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| 문자열 | [indexOf](../functions/functionindexof.md) |
| 문자열 | [isEmpty](../functions/functionisempty.md) |
| 문자열 | [isNotEmpty](../functions/functionisnotempty.md) |
| 문자열 | [lastIndexOf](../functions/functionlastindexof.md) |
| 문자열 | [length](../functions/functionlength.md) |
| 문자열 | [lower](../functions/functionlower.md) |
| 문자열 | [matchRegExp](../functions/functionmatchregexp.md) |
| 문자열 | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| 문자열 | [replace](../functions/functionreplace.md) |
| 문자열 | [replaceAll](../functions/functionreplaceall.md) |
| 문자열 | [startWith](../functions/functionstartwith.md) |
| 문자열 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 문자열 | [substr](../functions/functionsubstr.md) |
| 문자열 | [trim](../functions/functiontrim.md) |
| 문자열 | [upper](../functions/functionupper.md) |
| 문자열 | [uuid](../functions/functionuuid.md) |