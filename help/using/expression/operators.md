---
product: adobe campaign
solution: Journey Orchestration
title: 연산자
description: 고급 표현식의 연산자에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---



# 연산자 {#concept_wd5_pj5_dgb}

다음과 같은 두 가지 유형의 연산자가 있습니다.단항 연산자 및 이진 연산자입니다. 왼쪽 연산자 및 오른쪽 연산자가 있습니다.

```
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

지원되는 연산자 목록은 다음과 같습니다.

## 논리 {#logical}

### and

```
<expression1> and <expression2>
```

&lt;expression1> 및 &lt;expression2> 모두 부울 값이어야 합니다. 결과는 부울 값입니다.

예제:

```
3.14 > 2 and 3.15 < 1
```

### 또는



```
<expression1> or <expression2>
```

&lt;expression1> 및 &lt;expression2> 모두 부울 값이어야 합니다. 결과는 부울 값입니다.

예제:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> 은 boolean이어야 합니다. 결과는 부울 값입니다.

예제:

```
not 3.15 < 1
```

## 비교 {#comparison}

### 은(는) null입니다.



```
<expression> is null
```

결과는 부울 값입니다.

null은 표현식에 평가 값이 없음을 의미합니다.

예제:

```
@{BarBeacon.location} is null
```

### 은(는) null이 아닙니다.



```
<expression> is not null
```

결과는 부울 값입니다.

null은 표현식에 평가 값이 없음을 의미합니다.

예제:

```
@ is not null
```

### 은(는) null입니다.



```
<expression> has null
```

&lt;expression> 은(는) 목록이어야 합니다. 결과는 부울 값입니다.

목록에 null 값이 하나 이상 포함되어 있는지 확인하는 데 유용합니다.

예제:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;expression1> 및 &lt;expression2> 모두 동일한 데이터 유형을 가져야 합니다. 결과는 부울 값입니다.

예제:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;expression1> 및 &lt;expression2> 모두 동일한 데이터 유형을 가져야 합니다. 결과는 부울 값입니다.

예제:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 소수를 모두 정수나 소수로 비교할 수 있습니다.

다른 모든 조합은 금지된다.

결과는 부울 값입니다.

예제:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 소수를 모두 정수나 소수로 비교할 수 있습니다.

다른 모든 조합은 금지된다.

결과는 부울 값입니다.

예제:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 소수를 모두 정수나 소수로 비교할 수 있습니다.

다른 모든 조합은 금지된다.

결과는 부울 값입니다.

예제:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

Datetime을 Datetime과 비교할 수 있습니다.

Datetimeonly는 Datetimeonly와 비교할 수 있습니다.

정수나 소수를 모두 정수나 소수로 비교할 수 있습니다.

다른 모든 조합은 금지된다.

결과는 부울 값입니다.

예제:

```
42 <= 3.14
```

## 산술 {#arithmetic}

### +



```
<expression1> + <expression2>
```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과도 숫자입니다.

예제:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과도 숫자입니다.

예제:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과도 숫자입니다.

&lt;expression2> 0은(는) 아니어야 합니다(0 반환).

예제:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과도 숫자입니다.

예제:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과도 숫자입니다.

예제:

```
3 % 2 -- returns 1.
```

## 수학 {#math}

### 숫자



```
<expression> is numeric
```

표현식 유형은 정수 또는 소수입니다.

예제:

```
@ is numeric
```

### 정수입니다.



```
<expression> is integer
```

표현식 유형은 정수입니다.

예제:

```
@ is integer
```

### decimal



```
<expression> is decimal
```

표현식 유형은 소수입니다.

예제:

```
@ is decimal
```

## 문자열 {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

두 표현식을 연결합니다.

하나의 표현식은 연결된 문자열이어야 합니다.

예제:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 날짜 {#date}

### +



```
<expression + <duration>
```

dateTime, dateTimeOnly 또는 기간에 기간을 추가합니다.

예제:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
