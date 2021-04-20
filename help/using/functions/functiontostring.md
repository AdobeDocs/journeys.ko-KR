---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: toString 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---


# toString {#toString}

유형에 따라 인수 값을 문자열 값으로 변환합니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

전환

## 함수 구문

`toString(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| dateTime | 날짜를 UTC 날짜 형식으로 변환합니다. |
| dateTimeOnly | 날짜를 UTC 날짜 형식으로 변환합니다. |
| 지속 시간 | 해당 밀리초 수를 문자열로 변환 |
| 시간대 | 표준 시간대 ID 문자열 표현(JODA ID)으로 변환 |
| 정수 | 값을 문자열 표현으로 변환합니다(1은 &quot;1&quot;이 됨). |
| decimal | 값을 문자열 표현으로 변환합니다(1.5는 &quot;1.5&quot;가 됨). |
| boolean | 부울 값을 true이면 true, false이면 &#39;false&#39;로 변환합니다. |

## 서명 및 반환된 유형

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
