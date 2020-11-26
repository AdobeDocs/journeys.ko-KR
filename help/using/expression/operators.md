---
product: adobe campaign
solution: Journey Orchestration
title: 연산자
description: 고급 표현식의 연산자에 대해 알아보기
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

---



# 연산자 {#concept_wd5_pj5_dgb}

두 가지 유형의 연산자가 있습니다.단항 연산자 및 이진 연산자입니다. 왼쪽 연산자와 오른쪽 단항 연산자가 있습니다.

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

## 논리  {#logical}

### and

**리터럴 식**

```<expression1> and <expression2>```

&lt;expression1> 및 &lt;expression2> 모두 부울 값이어야 합니다. 결과는 부울 값입니다.

**예제**

```3.14 > 2 and 3.15 < 1```

### 또는

**리터럴 식**

```<expression1> or <expression2>```

&lt;expression1> 및 &lt;expression2> 모두 부울 값이어야 합니다. 결과는 부울 값입니다.

**예제**

```3.14 > 2 or 3.15 < 1```

### not

**리터럴 식**

```not <expression>```

&lt;expression>은 boolean이어야 합니다. 결과는 부울 값입니다.

**예제**

```not 3.15 < 1```

## 비교 {#comparison}

### 은(는) null입니다.

**리터럴 식**

```<expression> is null```

결과는 부울 값입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

**예제**

```@{BarBeacon.location} is null```

### 은(는) null이 아닙니다.

**리터럴 식**

```<expression> is not null```

결과는 부울 값입니다.

null은 표현식에 평가된 값이 없음을 의미합니다.

**예제**

```@ is not null```

### 은(는) null입니다.

**리터럴 식**

```<expression> has null```

&lt;expression>은(는) 목록이어야 합니다. 결과는 부울 값입니다.

목록에 null 값이 하나 이상 포함되어 있는지 확인하는 데 유용합니다.

**예제**

```["foo", "bar", null] has null``` true를 반환합니다.

```["foo", "bar", ""] has null``` &quot;&quot;이(가) null로 간주되지 않으므로 false를 반환합니다.

### ==

**리터럴 식**

```<expression1> == <expression2>```

&lt;expression1> 및 &lt;expression2> 모두 동일한 데이터 형식을 가져야 합니다. 결과는 부울 값입니다.

**예제**

```3.14 == 42```

```"foo" == "bar"```

### !=

**리터럴 식**

```<expression1> != <expression2>```

&lt;expression1> 및 &lt;expression2> 모두 동일한 데이터 형식을 가져야 합니다. 결과는 부울 값입니다.

**예제**

```3.14 != 42```

```"foo" != "bar"```

### >

**리터럴 식**

```<expression1> > <expression2>```

datetime과 비교할 수 있습니다.

Date timeonly는 Date-timeonly와 비교할 수 있습니다.

정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.

다른 조합은 금지.

결과는 부울 값입니다.

**예제**

```3.14 > 42```

### >=

**리터럴 식**

```<expression1> >= <expression2>```

datetime과 비교할 수 있습니다.

Date timeonly는 Date-timeonly와 비교할 수 있습니다.

정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.

다른 조합은 금지.

결과는 부울 값입니다.

**예제**

```42 >= 3.14```

### &lt;

**리터럴 식**

```<expression1> < <expression2>```

datetime과 비교할 수 있습니다.

Date timeonly는 Date-timeonly와 비교할 수 있습니다.

정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.

다른 조합은 금지.

결과는 부울 값입니다.

**예제**

```42 < 3.14```

### &lt;=

**리터럴 식**

```<expression1> <= <expression2>```

datetime과 비교할 수 있습니다.

Date timeonly는 Date-timeonly와 비교할 수 있습니다.

정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.

다른 조합은 금지.

결과는 부울 값입니다.

**예제**

```42 <= 3.14```

## 산술 {#arithmetic}

### +

**리터럴 식**

```<expression1> + <expression2>```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과는 숫자이기도 합니다.

**예제**

```1 + 2``` 반환 3

### -

**리터럴 식**

```<expression1> - <expression2>```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과는 숫자이기도 합니다.

**예제**

```2 - 1``` 반환 1

### /

**리터럴 식**

```<expression1> / <expression2>```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과는 숫자이기도 합니다.

&lt;expression2>은(는) 0이 아니어야 합니다(0 반환).

**예제**

```4 / 2``` 반환 2

### *

**리터럴 식**

```<expression1> * <expression2>```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과는 숫자이기도 합니다.

**예제**

```3 * 4``` 반환 12

### %

**리터럴 식**

```<expression1> % <expression2>```

두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.

결과는 숫자이기도 합니다.

**예제**

```3 % 2``` 반환 1.

## 수학 {#math}

### 숫자

**리터럴 식**

```<expression> is numeric```

식의 유형은 정수 또는 소수입니다.

**예제**

```@ is numeric```

### 정수

**리터럴 식**

```<expression> is integer```

표현식 유형은 정수입니다.

**예제**

```@ is integer```

### decimal

**리터럴 식**

```<expression> is decimal```

표현식 유형은 소수입니다.

**예제**

```@ is decimal```

## 문자열 {#string}

### +

**리터럴 식**

```<string> + <expression>```

```<expression> + <string>```

두 표현식을 연결합니다.

하나의 표현식은 체인 문자열이어야 합니다.

**예제**

```"the current time is " + (now())``` 반환: &quot;현재 시간은 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` 반환 &quot;2019-09-23T09:30:06.693Z가 현재 시간입니다&quot;

```"a" + "b" + "c" + 1234``` &quot;abc1234&quot;를 반환합니다.

## 날짜 {#date}

### +

**리터럴 식**

```<expression + <duration>```

dateTime, dateTimeOnly 또는 기간에 기간을 추가합니다.

**예제**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` 반환: 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` 반환: 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` 현재 시간으로부터 1시간 후 dateTime(UTC 표준 시간대 포함)을 반환합니다.

```toDuration("PT1H") + toDuration("PT1H")``` 반환: PT2H
