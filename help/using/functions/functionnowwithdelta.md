---
title: nowWithDelta
description: 기능에 대한 자세한 내용WithDelta
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
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

오프셋을 포함한 현재 날짜/시간을 반환합니다. 표준 시간대 ID를 지정하면 시간대 오프셋이 적용됩니다. 데이터 유형에 대한 자세한 내용은 을 참조하십시오 [](../expression/data-types.md).

## 범주

날짜

## 함수 구문

`nowWithDelta(<parameters>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 델타 | 양의 정수 또는 음의 정수 값 |
| 날짜 부분 | 연도, 월, 일, 시간, 분 또는 초(문자열) |
| 시간대 ID | 표준 시간대 값의 문자열 표현. 자세한 내용은 을 참조하십시오 [](../expression/data-types.md). 시간대 ID는 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다. |

## 서명 및 반환된 문자

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTime을 반환합니다.

## 예제

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

정확히 2시간 전에 dateTime을 반환합니다.
