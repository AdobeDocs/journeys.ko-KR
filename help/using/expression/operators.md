---
product: adobe campaign
title: 연산자
description: 고급 표현식의 연산자에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
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
source-wordcount: '514'
ht-degree: 16%
---
# 연산자 {#concept_wd5_pj5_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer를 찾고 계신가요**? [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하여 Journey Optimizer 설명서를 확인할 수 있습니다.
>
>
>_이 설명서는 Journey Optimizer로 대체된 이전 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


연산자에는 단항 연산자와 이항 연산자의 두 종류가 있다. 왼쪽 단항 연산자와 오른쪽 단항 연산자가 있습니다.

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## 중요 정보{#important-notes}

* 곱셈(`*`)을 사용할 때는 두 연산 필드의 형식이 같아야 합니다(정수 또는 십진수). 예 :
  * 다음 예제는 올바릅니다. `3.0 * 4.0`
  * `3 * 4.0`에 오류가 발생합니다.

## 논리적  {#logical}

### 및

```json
<expression1> and <expression2>
```

&lt;expression1>과 &lt;expression2> 모두 부울이어야 합니다. 결과는 부울입니다.

예:

```json
3.14 > 2 and 3.15 < 1
```

### 또는



```json
<expression1> or <expression2>
```

&lt;expression1>과 &lt;expression2> 모두 부울이어야 합니다. 결과는 부울입니다.

예:

```json
3.14 > 2 or 3.15 < 1
```

### 아님



```json
not <expression>
```

&lt;expression>은(는) 부울이어야 합니다. 결과는 부울입니다.

예:

```json
not 3.15 < 1
```

## 비교 {#comparison}

### null임



```json
<expression> is null
```

결과는 부울입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

예:

```json
@{BarBeacon.location} is null
```

### null이 아님



```json
<expression> is not null
```

결과는 부울입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

예:

```json
@ is not null
```

### 이(가) null임



```json
<expression> has null
```

&lt;expression>은(는) 목록이어야 합니다. 결과는 부울입니다.

목록에 Null 값이 하나 이상 포함되어 있음을 식별하는 데 유용합니다.

예:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

&lt;expression1>과 &lt;expression2> 모두 동일한 데이터 형식을 가져야 합니다. 결과는 부울입니다.

예:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

&lt;expression1>과 &lt;expression2> 모두 동일한 데이터 형식을 가져야 합니다. 결과는 부울입니다.

예:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datetime은 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 십진수는 모두 정수나 십진수와 비교할 수 있습니다.

다른 조합은 사용할 수 없습니다.

결과는 부울입니다.

예:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime은 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 십진수는 모두 정수나 십진수와 비교할 수 있습니다.

다른 조합은 사용할 수 없습니다.

결과는 부울입니다.

예:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime은 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 십진수는 모두 정수나 십진수와 비교할 수 있습니다.

다른 조합은 사용할 수 없습니다.

결과는 부울입니다.

예:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime은 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 십진수는 모두 정수나 십진수와 비교할 수 있습니다.

다른 조합은 사용할 수 없습니다.

결과는 부울입니다.

예:

```json
42 <= 3.14
```

## 산술 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

두 표현식은 모두 숫자(정수 또는 십진수)여야 합니다.

결과도 숫자입니다.

예:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

두 표현식은 모두 숫자(정수 또는 십진수)여야 합니다.

결과도 숫자입니다.

예:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

두 표현식은 모두 숫자(정수 또는 십진수)여야 합니다.

결과도 숫자입니다.

&lt;expression2>는 0이 아니어야 합니다(반환 0).

예:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

두 표현식은 모두 숫자(정수 또는 십진수)여야 합니다.

결과도 숫자입니다.

예:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

두 표현식은 모두 숫자(정수 또는 십진수)여야 합니다.

결과도 숫자입니다.

예:

```json
3 % 2 -- returns 1.
```

## 수학 {#math}

### 숫자임



```json
<expression> is numeric
```

식의 형식은 정수 또는 십진수입니다.

예:

```json
@ is numeric
```

### 정수



```json
<expression> is integer
```

식의 유형은 정수입니다.

예:

```json
@ is integer
```

### 소수임



```json
<expression> is decimal
```

식의 형식은 십진수입니다.

예:

```json
@ is decimal
```

## 문자열 {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

두 표현식을 연결합니다.

하나의 식은 체인 문자열이어야 합니다.

예:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 일자 {#date}

### +



```json
<expression> + <duration>
```

dateTime, dateTimeOnly 또는 duration에 duration을 추가합니다.

예:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
