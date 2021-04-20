---
product: adobe campaign
solution: Journey Orchestration
title: 일반성
description: 고급 표현식 일반에 대한 자세한 내용
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---


# 일반성 {#concept_rcy_qj5_dgb}

## 괄호 및 표현식 우선 순위{#section_edf_fks_bgb}

괄호를 사용하여 복잡한 표현식을 보다 쉽게 읽을 수 있도록 할 수 있습니다. _(&lt;expression>)_ 는 과 같습니다 _&lt;expression>_. 괄호를 사용하여 평가 순서와 연관성을 정의할 수도 있습니다.

표현식은 왼쪽에서 오른쪽으로 평가됩니다. 산술 연산자에 대한 연관성을 적용해야 합니다.더하기 및 빼기보다 여러 구분이 우선합니다. 특정 순서를 정하려면 작업을 구분하기 위해 괄호를 추가해야 합니다. 예제:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 표현식 | 평가 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;은(는) &#39;+&#39;보다 우선 순위가 높습니다.2 * 10은 → 20으로 평가됩니다.</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>괄호는 우선 순위를 변경합니다.(4 + 2) 평가됨 → 6</li><li> 6 * 10 → 60</li></ul> |

## 대/소문자 구분{#section_lrb_xh5_dgb}

다음은 대/소문자 구분 규칙입니다.

* 모든 연산자(및, 또는 등) 은(는) 소문자로 써야 합니다. 예를 들어 _`<expression1>`및`<expression2>`_ 표현식은 유효한 표현식이지만 _`<expression1>`AND`<expression2>`_ 표현식은 유효하지 않습니다.
* 모든 함수 이름은 대/소문자를 구분합니다. 예를 들어 _inSegment()_ 함수는 유효하지만 _INSEGMENT()_ 함수는 유효하지 않습니다.
* 필드 참조 및 상수 값은 대/소문자를 구분합니다.연산자와 함수가 아닌 기본 제공 언어 요소가 아니라 최종 사용자가 작성합니다.

## 표현식 유형{#section_gyc_435_53b} 반환

사용 컨텍스트에 따라 표현식 편집기는 다른 값을 반환할 수 있습니다.

| 고급 표현식 편집기 사용 | 반환된 표현식 유형이 필요합니다. |
|--- |--- |
| 조건(데이터 소스 조건, 날짜 조건) | boolean |
| 사용자 정의 타이머 | dateTimeOnly |
| 작업 매개 변수 매핑 | 임의 |
