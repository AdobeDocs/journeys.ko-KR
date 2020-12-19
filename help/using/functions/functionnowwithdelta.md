---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: WithDelta 기능에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

오프셋을 포함한 현재 날짜/시간을 반환합니다. 표준 시간대 ID를 지정하면 시간대 오프셋이 적용됩니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

날짜

## 함수 구문

`nowWithDelta(<parameters>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 델타 | 양의 정수 또는 음의 정수 값 |
| 날짜 부분 | 연도, 월, 일, 시간, 분 또는 초(문자열) |
| 시간대 ID | 표준 시간대 값의 문자열 표현. 자세한 내용은 [데이터 유형](../expression/data-types.md)을 참조하십시오. 시간대 ID는 문자열 상수여야 합니다. 필드 참조나 표현식이 될 수 없습니다. |

## 서명 및 반환된 유형

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTime을 반환합니다.

## 예제

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

정확히 2시간 전에 dateTime을 반환합니다.
