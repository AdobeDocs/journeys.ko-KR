---
product: adobe campaign
title: nowWithDelta
description: nowWithDelta 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%
---
# nowWithDelta {#nowWithDelta}

오프셋을 포함하여 현재 날짜/시간을 반환합니다. 시간대 ID를 지정하면 시간대 오프셋이 적용됩니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

일자

## 함수 구문

`nowWithDelta(<parameters>)`

## 매개변수

| 매개 변수 | 설명 |
|--- |--- |
| 델타 | 양의 정수 값 또는 음의 정수 값 |
| 날짜 부분 | years, months, days, hours, minutes 또는 seconds as a string |
| 시간대 id | 시간대 값의 문자열 표현입니다. 자세한 내용은 [데이터 형식](../expression/data-types.md)을 참조하세요. 시간대 ID는 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다. |

## 서명 및 반환된 유형

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTime을 반환합니다.

## 예시

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

정확히 2시간 전의 dateTime을 반환합니다.
