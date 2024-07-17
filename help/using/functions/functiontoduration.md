---
product: adobe campaign
title: toDuration
description: 함수 toDuration에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 3%

---

# toDuration {#toDuration}

인수 값을 duration으로 변환합니다. 데이터 형식에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하세요.

## 카테고리

전환

## 함수 구문

`toDuration(<parameter>)`

## 매개 변수

| 매개변수 | 설명 |
|--- |--- |
| 문자열 | ISO-8601 기간 형식 PnDTnHnMn.nS를 기반으로 하는 형식이며, 일 수는 정확히 24시간으로 간주됩니다. |
| 정수 | 시간(밀리초) |

문자열 표현식: 허용되는 형식은 ISO-8601 기간 형식 PnDTnHnMn.nS를 기반으로 하며, 일은 정확히 24시간으로 간주됩니다.

문자열은 ASCII 음수 또는 양수 기호로 표시되는 선택적 기호로 시작합니다. 음수이면 전체 기간이 무효화됩니다. ASCII 문자 &quot;P&quot;는 다음으로 대문자 또는 소문자로 구성됩니다. 그 다음에는 4개의 섹션이 있는데, 각각의 섹션은 숫자와 접미사로 구성되어 있다. 섹션에는 일, 시간, 분 및 초 동안 &quot;D&quot;, &quot;H&quot;, &quot;M&quot; 및 &quot;S&quot;의 ASCII 접미사가 있으며, 대문자나 소문자로 허용됩니다. 접미사는 순서대로 수행되어야 합니다. ASCII 문자 &quot;T&quot;는 시간, 분 또는 초 구간의 첫 번째 항목(있는 경우) 전에 발생해야 합니다. 4개의 섹션 중 적어도 하나가 있어야 하며, &quot;T&quot;가 있으면 &quot;T&quot; 다음에 적어도 하나의 섹션이 있어야 합니다. 각 섹션의 숫자 부분은 하나 이상의 ASCII 숫자로 구성되어야 합니다. 숫자는 ASCII 음수 또는 양수 기호로 접두사로 사용될 수 있습니다. 일, 시간 및 분 수는 함께 구문 분석해야 합니다. 초 수는 선택적 분수와 함께 로 구문 분석해야 합니다. 소수점은 점 또는 쉼표일 수 있습니다. 분수 부분은 0부터 9자리까지 가질 수 있다.

## 서명 및 반환된 유형

`toDuration(<string>)`

`toDuration(<integer>)`

기간을 반환합니다.

## 예시

`toDuration("PT10H")`

10시간의 기간을 반환합니다.

`toDuration("PT4S")`

기간을 4초로 반환합니다.

`toDuration(4000)`

기간을 4초로 반환합니다.
