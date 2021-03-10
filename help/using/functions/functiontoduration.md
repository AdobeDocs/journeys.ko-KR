---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: toDuration 함수에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 2%

---


# toDuration {#toDuration}

인수 값을 지속 시간으로 변환합니다. 데이터 유형에 대한 자세한 내용은 [이 페이지](../expression/data-types.md)를 참조하십시오.

## 카테고리

전환

## 함수 구문

`toDuration(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | ISO-8601 지속 시간 형식 PnDTnHun.nS를 기반으로 하는 형식(일 수가 정확히 24시간으로 간주됨) |
| 정수 | 밀리초 수 |

문자열 표현식인 경우:허용되는 포맷은 정확히 24시간으로 간주되는 일이 있는 ISO-8601 지속 시간 형식 PnDTnHn.nS를 기반으로 합니다.

문자열은 ASCII 네거티브 또는 양수 기호를 나타내는 선택적 부호로 시작합니다. 음수이면 전체 기간이 무효화됩니다. ASCII 문자 &quot;P&quot;는 대문자 또는 소문자의 옆에 있습니다. 그런 다음 각각 숫자와 접미어로 구성된 4개의 섹션이 있습니다. 섹션에 일, 시간, 분 및 초 동안 &quot;D&quot;, &quot;H&quot;, &quot;M&quot; 및 &quot;S&quot;의 ASCII 접미어가 포함되며 대문자 또는 소문자로 허용됩니다. 접미어는 순서대로 발생해야 합니다. ASCII 문자 &quot;T&quot;는 시간, 분 또는 두 번째 섹션의 첫 번째 발생 전에 발생해야 합니다. 4개 섹션 중 적어도 하나가 있어야 하며, &quot;T&quot;가 있는 경우 &quot;T&quot; 뒤에 최소한 한 개의 섹션이 있어야 합니다. 각 섹션의 숫자 부분은 하나 이상의 ASCII 숫자로 구성되어야 합니다. 숫자 접두어는 ASCII 네거티브 또는 양수 기호를 사용할 수 있습니다. 일, 시간, 분 수가 따라 분석되어야 합니다. 시간(초)은 선택적 분수와 함께 구문 분석해야 합니다. 소수점은 점 또는 쉼표일 수 있습니다. 분수 부분은 0에서 9자리 숫자를 가질 수 있습니다.

## 서명 및 반환된 유형

`toDuration(<string>)`

`toDuration(<integer>)`

지속 기간을 반환합니다.

## 예제

`toDuration("PT10H")`

지속 시간을 10시간으로 반환합니다.

`toDuration("PT4S")`

4s 지속 기간을 반환합니다.

`toDuration(4000)`

4s 지속 기간을 반환합니다.
