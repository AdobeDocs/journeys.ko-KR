---
product: adobe campaign
title: 일반 사항
description: 고급 표현식 일반성에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 19%

---

# 일반 사항 {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer를 찾고 계신가요**? [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하여 Journey Optimizer 설명서를 확인할 수 있습니다.
>
>
>_이 설명서는 Journey Optimizer로 대체된 이전 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


## 괄호 및 표현식 우선 순위{#section_edf_fks_bgb}

괄호는 복잡한 표현식을 더 읽기 쉽게 하는 데 사용할 수 있습니다. _(&lt;표현식>)_&#x200B;은(는) _&lt;표현식>_&#x200B;과(와) 동일합니다. 괄호는 또한 평가 순서 및 연관성을 정의하는 데 사용될 수 있다.

표현식은 왼쪽에서 오른쪽으로 평가됩니다. 산술 연산자에 대한 연관성을 적용해야 합니다. 곱과 나눗셈은 덧셈과 뺄셈보다 우선합니다. 특정한 명령을 부과하기 위해서는 반드시 괄호를 추가하여 작업을 구분해야 한다. 예:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 표현식 | 평가 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;가 &#39;+&#39;보다 우선함: 2 * 10은 20→ 평가됨</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>괄호는 우선 순위를 변경합니다. (4 + 2)는 6→ 평가됩니다.</li><li> 6 * 10 → 60</li></ul> |

## 대/소문자 구분{#section_lrb_xh5_dgb}

다른 대소문자 구분 규칙은 다음과 같습니다.

* 모든 연산자(및, 또는 등)는 소문자로 작성해야 합니다. 예를 들어 _`<expression1>`및`<expression2>`_&#x200B;은(는) 올바른 식이지만 _`<expression1>`및`<expression2>`_ 식은 올바른 식이 아닙니다.
* 모든 함수 이름은 대소문자를 구분합니다. 예를 들어 _inSegment()_&#x200B;은(는) 유효하지만 _INSEGMENT()_ 함수는 유효하지 않습니다.
* 필드 참조 및 상수 값은 대소문자를 구분합니다. 연산자 및 함수와 달리 언어의 기본 제공 요소가 아니며, 최종 사용자가 작성합니다.

## 반환된 표현식 유형{#section_gyc_435_53b}

사용 컨텍스트에 따라 표현식 편집기에서 다른 값을 반환할 수 있습니다.

| 고급 표현식 편집기 사용 | 반환된 표현식 유형이 필요합니다. |
|--- |--- |
| 조건(데이터 소스 조건, 날짜 조건) | 부울 |
| 사용자 지정 타이머 | dateTimeOnly |
| 작업 매개 변수 매핑 | 모두 |
