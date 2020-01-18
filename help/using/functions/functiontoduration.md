---
title: toDuration
description: toDuration 함수에 대한 자세한 내용
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

---


# toDuration {#toDuration}

인수 값을 지속 시간으로 변환합니다. 데이터 유형에 대한 자세한 내용은 을 참조하십시오 [](../expression/data-types.md).

## 카테고리

전환

## 함수 구문

`toDuration(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 |
|--- |--- |
| 문자열 | ISO-8601 지속 시간 형식 PnDTnHnMn.nS를 기반으로 하는 형식(일 수가 정확히 24시간) |
| 정수 | 밀리초 수 |

문자열 표현식인 경우:허용되는 형식은 정확히 24시간으로 간주되는 ISO-8601 지속 시간 형식 PnDTnHn.NS를 기반으로 합니다.

문자열은 ASCII 네거티브 또는 양수 기호로 표시된 선택적 기호로 시작됩니다. 음수이면 전체 기간이 무효화됩니다. ASCII 문자 &quot;P&quot;는 대/소문자를 구분합니다. 그런 다음 각각 숫자와 접미어로 구성된 네 개의 섹션이 있습니다. 이 섹션에는 일, 시간, 분 및 초 동안 &quot;D&quot;, &quot;H&quot;, &quot;M&quot; 및 &quot;S&quot;의 ASCII 접미어가 포함되며 대문자 또는 소문자로 허용됩니다. 접미사가 순서대로 이루어져야 합니다. ASCII 문자 &quot;T&quot;는 시간, 분 또는 두 번째 섹션이 있을 경우 첫 번째 발생 전에 발생해야 합니다. 4개 섹션 중 적어도 하나가 있어야 하며, &quot;T&quot;가 있는 경우 &quot;T&quot; 뒤에 섹션이 하나 이상 있어야 합니다. 각 섹션의 숫자 부분은 하나 이상의 ASCII 숫자로 구성되어야 합니다. 숫자 접두사는 ASCII 네거티브 또는 긍정 기호로 묶을 수 있습니다. 일, 시간, 분 수가 따라 분석되어야 합니다. 시간(초)은 선택 분수(초)와 함께 구문 분석해야 합니다. 소수점은 점 또는 쉼표일 수 있습니다. 분수 부분은 0에서 9자리 숫자를 가질 수 있습니다.

## 서명 및 반환된 문자

`toDuration(<string>)`

`toDuration(<integer>)`

기간을 반환합니다.

## 예

`toDuration("PT10H")`

10시간의 기간을 반환합니다.

`toDuration("PT4S")`

4s의 지속 기간을 반환합니다.

`toDuration(4000)`

4s의 지속 기간을 반환합니다.
