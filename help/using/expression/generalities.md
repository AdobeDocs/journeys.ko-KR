---
title: 일반성
description: 고급 표현식 생성
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


# 일반성 {#concept_rcy_qj5_dgb}

## 괄호 및 표현식 우선 순위{#section_edf_fks_bgb}

괄호를 사용하여 복잡한 표현식을 보다 쉽게 읽을 수 있도록 할 수 있습니다. _(&lt;expression>)_ 는 _&lt;expression>_&#x200B;과 같습니다. 괄호를 사용하여 평가 순서와 연관성을 정의할 수도 있습니다.

표현식은 왼쪽에서 오른쪽으로 평가됩니다. 산술 연산자의 연관을 적용해야 합니다.더하기 및 빼기보다 배합 및 분할이 우선합니다. 특정 순서를 정하려면 작업을 구분하기 위해 괄호를 추가해야 합니다. 예:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 표현식 | 평가 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;은(는) &#39;+&#39;보다 우선 순위가 높습니다.2 * 10은 평가됨 - 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>괄호는 우선 순위를 변경합니다.(4 + 2) 평가→6</li><li> 6 * 10 → 60</li></ul> |

## 대소문자 구분{#section_lrb_xh5_dgb}

다음은 대/소문자 구분 규칙입니다.

* 모든 연산자(및, 또는 등) 은(는) 소문자여야 합니다. 예를 들어, _`<expression1>`와 은`<expression2>`_유효한 표현식이지만 AND 표현식은_`<expression1>` 그렇지 `<expression2>`_ 않습니다.
* 모든 함수 이름은 대/소문자를 구분합니다. 예를 들어 _getBestSendTime()_ 은 유효하지만 GETBESTSENDTIME() __ 함수는 유효하지 않습니다.
* 필드 참조 및 상수 값은 대/소문자를 구분합니다.이 구성 요소는 언어의 기본 요소(연산자 및 기능이 아님)가 아니라 최종 사용자가 작성하게 됩니다.

## 반환된 표현식 유형{#section_gyc_435_53b}

사용 컨텍스트에 따라 표현식 편집기는 다른 값을 반환할 수 있습니다.

| 고급 표현식 편집기 사용 | 반환된 표현식 유형이 필요합니다. |
|--- |--- |
| 조건(데이터 소스 조건, 날짜 조건) | boolean |
| 사용자 정의 타이머 | dateTimeOnly |
| 사용자 지정 표준 시간대 | timeZone 또는 문자열(예: 유럽/파리) |
| 작업 매개 변수 매핑 | 임의 |
