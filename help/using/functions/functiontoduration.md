---
product: adobe campaign
title: toDuration
description: toDuration 함수에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# toDuration {#toDuration}

인수 값을 기간으로 변환합니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

전환

## 함수 구문

`toDuration(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| string | ISO-8601 지속 시간 형식 PnDTnHnMn.nS를 기반으로 하는 형식(일 수가 정확히 24시간으로 고려됨) |
| 정수 | 밀리초 수 |

문자열 식인 경우:허용되는 형식은 ISO-8601 기간 형식 PnDTnHnMn.n을 기반으로 하며, 일 수는 정확히 24시간으로 간주됩니다.

문자열은 ASCII 음수 또는 양수 기호로 표시된 선택적 기호로 시작합니다. 음수인 경우 전체 기간이 무효화됩니다. ASCII 문자 &quot;P&quot;는 위 또는 아래 케이스에 있습니다. 그 다음 네 개의 섹션이 있는데, 각각 숫자와 접미사로 구성됩니다. 섹션에는 일, 시간, 분 및 초 동안 &quot;D&quot;, &quot;H&quot;, &quot;M&quot; 및 &quot;S&quot;의 ASCII 접미사가 대문자나 소문자로 허용되어 있습니다. 접미사는 순서대로 발생해야 합니다. ASCII 문자 &quot;T&quot;는 1시간, 분 또는 두 번째 섹션의 첫 번째 발생 전에 수행해야 합니다. 4개 섹션 중 적어도 하나가 있어야 하며, &quot;T&quot;가 있으면 &quot;T&quot; 뒤에 섹션이 하나 이상 있어야 합니다. 각 섹션의 숫자 부분은 하나 이상의 ASCII 숫자로 구성되어야 합니다. ASCII 음수 또는 양수 기호 앞에 숫자를 추가할 수 있습니다. 일, 시간 및 분 수가 함께 구문 분석되어야 합니다. 초 수는 선택적 분수와 함께 로 구문 분석해야 합니다. 소수점은 점 또는 쉼표일 수 있습니다. 분수 부분은 0에서 9자리까지입니다.

## 서명 및 반환된 유형

`toDuration(<string>)`

`toDuration(<integer>)`

지속 시간을 반환합니다.

## 예제

`toDuration("PT10H")`

10시간의 지속 시간을 반환합니다.

`toDuration("PT4S")`

4s의 지속 시간을 반환합니다.

`toDuration(4000)`

4s의 지속 시간을 반환합니다.
