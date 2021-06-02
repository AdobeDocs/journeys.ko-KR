---
product: adobe campaign
title: nowWithDelta
description: 지금 함수 알아보기WithDelta
feature: 여정
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 6%

---

# nowWithDelta {#nowWithDelta}

오프셋을 포함하는 현재 날짜/시간을 반환합니다. 시간대 ID를 지정하면 시간대 오프셋이 적용됩니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

날짜

## 함수 구문

`nowWithDelta(<parameters>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 델타 | 양수 또는 음수 정수 값 |
| 날짜 부분 | 연도, 월, 일, 시간, 분 또는 초를 문자열로 사용합니다 |
| 시간대 id | 시간대 값의 문자열 표시. 자세한 내용은 [데이터 유형](../expression/data-types.md)을 참조하십시오. 시간대 ID는 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다. |

## 서명 및 반환된 유형

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTime 반환

## 예제

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

정확히 2시간 전에 dateTime을 반환합니다.
