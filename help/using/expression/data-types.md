---
product: adobe campaign
solution: Journey Orchestration
title: 데이터 유형
description: 고급 표현식의 데이터 유형에 대해 알아보기
translation-type: tm+mt
source-git-commit: f755f92d0479e2889dd7ed6dfa5e72d52c25634f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 4%

---


# 데이터 유형 {#concept_gp3_rj5_dgb}

기술적으로 상수에는 항상 데이터 형식이 포함됩니다. 리터럴 표현식에서는 값만 지정합니다. 값(예: 문자열, 정수, 십진수 등)에서 데이터 유형을 유추할 수 있습니다. 날짜 시간과 같은 특정 경우에는 표현에만 전용 기능을 사용합니다.

아래의 섹션에서는 다양한 데이터 유형 표현식과 표현식에 대한 정보를 제공합니다.

## 문자열 {#string}

**설명**

공통 문자 시퀀스입니다. 사용 가능한 메모리의 양과 같은 환경에서 오는 암묵적인 것을 제외하고는 구체적인 크기가 없습니다.

JSON 형식:문자열

직렬화 형식:UTF-8

**리터럴 표현**

```"<value>"```

```'<value>'```

**예제**

```"hello world"```

```'hello world'```

## 정수 {#integer}

**설명**

-2^63부터 2^63-1까지의 정수 값.

JSON 형식:숫자

**리터럴 표현**

```<integer value>```

**예제**

```42```

## 소수 {#decimal}

**설명**

십진수. 부동 소수점 값:

* double 형식의 가장 큰 양의 유한값(2-2^-52)x2^1023
* double, 2-1022 유형의 양수 정규 값
* double, 2p-1074 유형의 양수 0이 아닌 값

JSON 형식:숫자

직렬화 형식:&#39;.&#39; 사용 을 십진수 구분 기호로 사용합니다.

**리터럴 표현**

```<integer value>.<integer value>```

**예제**

```3.14```

## boolean {#boolean}

**설명**

소문자 기된 부울 값:true 또는 false

JSON 형식:부울

**리터럴 표현**

```true```

```false```

**예제**

```true```

## dateTimeOnly {#date-time-only}

**설명**

연도 시간대가 없는 날짜 시간을 나타내며, 년 개월 시간 분 초 밀리초로 표시됩니다.

표준 시간대를 저장하거나 나타내지 않습니다. 대신, 그것은 근무 시간에 보이는 것과 지역 시간과 함께 생일에 사용되는 날짜의 설명입니다.

오프셋 또는 시간대와 같은 추가 정보 없이 타임라인에서 즉시 표시할 수 없습니다.

직렬화 형식:ISO-8601 확장 오프셋 날짜-시간 형식.

DateTimeFormatter ISO_LOCAL_DATE_TIME을 사용하여 값을 역직렬화하고 직렬화합니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**리터럴 표현**

```toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  ```

## dateTime {#date-time}

**설명**

시간대도 고려하는 날짜 시간 상수입니다. UTC의 오프셋이 있는 날짜 시간을 나타냅니다.

오프셋에 대한 추가 정보와 함께 즉시 볼 수 있습니다. 세계 어느 곳에서 특정 &#39;순간&#39;을 표현하는 방법입니다.

JSON 형식:문자열.

toDateTime 함수로 캡슐화되어야 합니다.

직렬화 형식:ISO-8601 확장 오프셋 날짜-시간 형식.

DateTimeFormatter ISO_OFFSET_DATE_TIME을 사용하여 값을 역직렬화하고 직렬화합니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

epoch 값을 전달하는 정수도 전달할 수 있습니다. [자세한 내용](https://www.epochconverter.com)

시간대는 오프셋 또는 표준 시간대 코드로 지정할 수 있습니다(예:유럽/파리, Z - UTC를 의미합니다.

**리터럴 표현**

```toDateTime("<dateTime in ISO-8601 format>")```

```toDateTime(<integer value of an epoch in milliseconds>)```

**예제**

```toDateTime("1977-04-22T06:00:00Z")```

```toDateTime("2011-12-03T15:15:30Z")```

```toDateTime("2011-12-03T15:15:30.123Z")```

```toDateTime("2011-12-03T15:15:30.123+02:00")```

```toDateTime("2011-12-03T15:15:30.123-00:20")```

```toDateTime(1560762190189)```

## 지속 시간 {#duration}

**설명**

시간 기반 시간(예: &#39;34.5초&#39;)을 나타냅니다. 이 모델은 수량과 시간을 밀리초 단위로 모델링합니다.

지원되는 임시 단위는 다음과 같습니다.밀리초, 초, 분, 시간, 일 중 하루가 24시간으로 연도 및 달은 정해진 시간이 아니므로 지원되지 않습니다.

JSON 형식:문자열.

toDuration 함수로 캡슐화되어야 합니다.

직렬화 형식:표준 시간대 ID를 역직렬화하려면 java 함수 java.time을 사용합니다.

Duration.parse:허용되는 포맷은 정확히 24시간으로 간주되는 날을 가진 ISO-8601 지속 시간 포맷인 PnDTnHn.nS를 기반으로 합니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**리터럴 표현**

```toDuration("<duration in ISO-8601 format>")```

```toDuration(<duration in milliseconds>)```

**예제**

```toDuration("PT5S")``` 5초로 된 구문

```toDuration(500)``` 500ms

```toDuration("PT20.345S")``` 구문: &quot;20.345초&quot;

```toDuration("PT15M") ``` 구문(&quot;15분&quot;, 분(60초)

```toDuration("PT10H") ``` parses as &quot;10hours&quot; (a hour is 3600 초인 경우)

```toDuration("P2D") ``` 구문 &quot;2일&quot;(하루가 24시간 또는 86400초인 경우)

```toDuration("P2DT3H4M") ```&quot;2일, 3시간 4분&quot;으로

```toDuration("P-6H3M") ``` &quot;-6시간 및 +3분&quot;으로

```toDuration("-P6H3M")``` &quot;-6시간 및 -3분&quot;

```toDuration("-P-6H+3M") ``` &quot;+6시간 및 -3분&quot;

## list {#list}

**설명**

구분 기호로 대괄호를 사용하는 쉼표로 구분된 표현식 목록입니다.

다형성은 지원되지 않으므로 목록에 포함된 모든 표현식의 유형이 같아야 합니다.

**리터럴 표현**

```[<expression>, <expression>, ... ]```

**예제**

```["value1","value2"]```

```[3,5]```

```[toDuration(500),toDuration(800)]```
