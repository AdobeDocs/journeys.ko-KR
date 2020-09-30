---
title: toString
description: toString 함수에 대해 알아보기
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
source-git-commit: 70bc6653a8cdd552a0441f4b661341d3f095b112
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# toString {#toString}

유형에 따라 인수 값을 문자열 값으로 변환합니다. 데이터 유형에 대한 자세한 내용은 을 참조하십시오 [](../expression/data-types.md).

## 범주

전환

## 함수 구문

`toString(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| dateTime | 날짜를 UTC 날짜 형식으로 변환합니다. |
| dateTimeOnly | 날짜를 UTC 날짜 형식으로 변환합니다. |
| 지속 시간 | 해당 밀리초 수로 문자열 변환 |
| 시간대 | 표준 시간대 ID 문자열 표현(JODA ID)으로 변환 |
| 정수 | 값을 문자열 표현으로 변환합니다(1은 &quot;1&quot;이 됨). |
| 소수 | 값을 문자열 표현으로 변환합니다(1.5는 &quot;1.5&quot;가 됨). |
| boolean | 부울 값을 true이면 true, false이면 &#39;false&#39;로 변환합니다. |

## 서명 및 반환된 문자

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

문자열을 반환합니다.

## 예제

`toString(4)`

&quot;4&quot;를 반환합니다.
