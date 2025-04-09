---
product: adobe campaign
title: 데이터 유형
description: 고급 표현식의 데이터 유형에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 5%

---

# 데이터 유형 {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


기술적으로, 상수는 항상 데이터 형식을 포함합니다. 리터럴 표현식에서는 값만 지정합니다. 값(예: 문자열, 정수, 십진수 등)에서 데이터 형식을 유추할 수 있습니다. 날짜 시간과 같은 특정한 경우에, 우리는 표현에 전용 함수를 사용한다.

아래 섹션에서는 다양한 데이터 유형 표현식과 표현식을 표시하는 방법에 대한 정보를 제공합니다.

## 문자열 {#string}

**설명**

일반적인 문자 시퀀스. 사용 가능한 메모리 양과 같은 환경에서 발생하는 암시적 크기 외에는 특정 크기가 없습니다.

JSON 형식: 문자열

직렬화 형식: UTF-8

**리터럴 표시**

```json
"<value>"
```

```json
'<value>'
```

**예**

```json
"hello world"
```

```json
'hello world'
```

## 정수 {#integer}

**설명**

-2^63부터 2^63-1까지의 정수 값입니다.

JSON 형식: 숫자

**리터럴 표시**

```json
<integer value>
```

**예**

```json
42
```

## decimal {#decimal}

**설명**

10진수입니다. 부동 값을 나타냅니다.

* double 유형의 가장 큰 양의 유한 값, (2-2^-52)x2^1023
* double 유형의 가장 작은 양의 정규 값, 2-1022
* double, 2 p-1074 유형의 가장 작은 양수 nonzero 값

JSON 형식: 숫자

직렬화 형식: &#39;.&#39; 사용 를 소수점 구분 기호로 사용하십시오.

**리터럴 표시**

```json
<integer value>.<integer value>
```

**예**

```json
3.14
```

## 부울 {#boolean}

**설명**

소문자로 작성된 부울 값: true 또는 false

JSON 형식: 부울

**리터럴 표시**

```json
true
```

```json
false
```

**예**

```json
true
```

## dateOnly {#date-only}

**설명**

표준 시간대 없이 1년 1개월로 표시된 날짜만 나타냅니다.

생일에 사용되는 날짜에 대한 설명입니다.

JSON 형식: 문자열.

형식은 YYYY-MM-DD(ISO-8601)입니다(예: &quot;2021-03-11&quot;).

toDateOnly 함수에 캡슐화할 수 있습니다.

DateTimeFormatter ISO_LOCAL_DATE_TIME을 사용하여 값을 deserialize 및 serialize합니다. [자세히 알아보기](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**리터럴 표시**

```json
date("<dateOnly in ISO-8601 format>")  
```

**예**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**설명**

표준 시간대 없이 연-월-일-시간-분-초(밀리초)로 표시되는 날짜 시간을 나타냅니다.

JSON 형식: 문자열.

시간대를 저장하거나 나타내지 않습니다. 대신, 월시계에서 본 현지 시간과 결합하여 생일 때 사용되는 날짜의 설명입니다.

오프셋이나 시간대와 같은 추가 정보 없이 타임라인에서 순간을 나타낼 수 없습니다.

toDateTimeOnly 함수에 캡슐화할 수 있습니다.

직렬화 포맷: ISO-8601 확장 오프셋 날짜-시간 포맷.

DateTimeFormatter ISO_LOCAL_DATE_TIME을 사용하여 값을 deserialize 및 serialize합니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**리터럴 표시**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**예**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**설명**

시간대도 고려하는 날짜 시간 상수입니다. UTC의 오프셋이 있는 날짜-시간을 나타냅니다.

오프셋의 추가적 정보를 가지고 순간적으로 볼 수 있다. 세계의 일정한 장소에서 특정한 &#39;순간&#39;을 나타내는 방법이다.

JSON 형식: 문자열.

toDateTime 함수에 캡슐화할 수 있습니다.

직렬화 포맷: ISO-8601 확장 오프셋 날짜-시간 포맷.

DateTimeFormatter ISO_OFFSET_DATE_TIME을 사용하여 값을 deserialize 및 serialize합니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

에포크 값을 전달하는 정수를 전달할 수도 있습니다. [자세히 보기](https://www.epochconverter.com)

시간대는 오프셋 또는 시간대 코드(예: 유럽/파리, Z - UTC 의미)로 지정할 수 있습니다.

**리터럴 표시**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**예**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## 지속 시간 {#duration}

**설명**

이는 &#39;34.5초&#39;와 같이 시간 기반 시간을 나타냅니다. 그것은 밀리초로 수량이나 시간을 모델링한다.

지원되는 시간 단위는 밀리초, 초, 분, 시간, 일수가 24시간과 같은 경우입니다. 연도 및 월은 고정된 시간이 아니므로 지원되지 않습니다.

JSON 형식: 문자열.

toDuration 함수에 캡슐화해야 합니다.

직렬화 형식: 시간대 ID를 역직렬화하려면 java 함수 java.time을 사용합니다.

Duration.parse: 허용되는 형식은 ISO-8601 기간 형식 PnDTnHnMn.nS를 기반으로 하며, 일은 정확히 24시간으로 간주됩니다. [자세히 알아보기](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**리터럴 표시**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**예**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**설명**

대괄호를 구분 기호로 사용하여 쉼표로 구분된 표현식 목록입니다.

다형성은 지원되지 않으므로 목록에 포함된 모든 표현식의 유형이 같아야 합니다.

**리터럴 표시**

```json
[<expression>, <expression>, ... ]
```

**예**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
