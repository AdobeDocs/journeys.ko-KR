---
product: adobe campaign
title: toString
description: 함수 toString에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 9%

---

# toString {#toString}

인수 유형에 따라 인수 값을 문자열 값으로 변환합니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

전환

## 함수 구문

`toString(<parameter>)`

## 매개 변수

| 매개변수 | 설명 |
|--- |--- |
| dateTime | 날짜를 UTC 날짜 형식으로 변환 |
| dateTimeOnly | 날짜를 UTC 날짜 형식으로 변환 |
| 지속 시간 | 문자열로 해당 시간(밀리초)으로 변환 |
| 정수 | 를 값의 문자열 표현으로 변환합니다(1은 &quot;1&quot;이 됨). |
| decimal | 를 값의 문자열 표현으로 변환(1.5가 &quot;1.5&quot;가 됨) |
| 부울 | true이면 &#39;true&#39;로, false이면 &#39;false&#39;로 부울 값 변환 |

## 서명 및 반환된 유형

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

문자열을 반환합니다.

## 예

`toString(4)`

&quot;4&quot;를 반환합니다.
