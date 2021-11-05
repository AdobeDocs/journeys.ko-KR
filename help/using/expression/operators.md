---
product: adobe campaign
title: 연산자
description: 고급 표현식의 연산자에 대해 알아봅니다
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---

# 연산자 {#concept_wd5_pj5_dgb}

다음과 같은 두 가지 유형의 연산자가 있습니다. 단항 연산자 및 이진 연산자입니다. 왼쪽 단항 연산자와 오른쪽 단항 연산자가 있습니다.

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

다음은 지원되는 연산자 목록입니다.

## 논리  {#logical}

### 및

```json
<expression1> and <expression2>
```

둘 다 &lt;expression1> 및 &lt;expression2> 는 부울이어야 합니다. 결과는 부울입니다.

예:

```json
3.14 > 2 and 3.15 < 1
```

### 또는



```json
<expression1> or <expression2>
```

둘 다 &lt;expression1> 및 &lt;expression2> 는 부울이어야 합니다. 결과는 부울입니다.

예:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> 는 부울이어야 합니다. 결과는 부울입니다.

예:

```json
not 3.15 < 1
```

## 비교 {#comparison}

### is null



```json
<expression> is null
```

결과는 부울입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

예:

```json
@{BarBeacon.location} is null
```

### is not null



```json
<expression> is not null
```

결과는 부울입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

예:

```json
@ is not null
```

### null이



```json
<expression> has null
```

&lt;expression> 목록이어야 합니다. 결과는 부울입니다.

목록에 하나 이상의 null 값이 포함되어 있음을 식별하는 데 유용합니다.

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

둘 다 &lt;expression1> 및 &lt;expression2> 에는 동일한 데이터 유형이 있어야 합니다. 결과는 부울입니다.

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

둘 다 &lt;expression1> 및 &lt;expression2> 에는 동일한 데이터 유형이 있어야 합니다. 결과는 부울입니다.

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

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수 또는 십진수는 모두 정수 또는 십진수와 비교할 수 있습니다.

다른 모든 조합은 금지됩니다.

결과는 부울입니다.

예:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수 또는 십진수는 모두 정수 또는 십진수와 비교할 수 있습니다.

다른 모든 조합은 금지됩니다.

결과는 부울입니다.

예:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수 또는 십진수는 모두 정수 또는 십진수와 비교할 수 있습니다.

다른 모든 조합은 금지됩니다.

결과는 부울입니다.

예:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수 또는 십진수는 모두 정수 또는 십진수와 비교할 수 있습니다.

다른 모든 조합은 금지됩니다.

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

&lt;expression2> 0과 같아야 합니다(0을 반환).

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

### 는 숫자입니다.



```json
<expression> is numeric
```

식의 유형은 정수 또는 소수입니다.

예:

```json
@ is numeric
```

### 정수



```json
<expression> is integer
```

표현식의 형식은 정수입니다.

예:

```json
@ is integer
```

### is decimal



```json
<expression> is decimal
```

표현식의 유형은 10진수입니다.

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

## 날짜 {#date}

### +



```json
<expression> + <duration>
```

dateTime, dateTimeOnly 또는 기간에 기간을 추가합니다.

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
