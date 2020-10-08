---
title: 연산자
description: 고급 표현식의 연산자에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

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

## 논리

<table>
<thead>
<tr ><th  >연산자</th><th  >리터럴 식</th><th  >예제</th></tr>
</thead>
<tbody>
<tr >&gt;<td>and</td><td><p><pre>&lt;expression1&gt; 및 &lt;expression2&gt;</pre></p>&lt;expression1&gt; 및 &lt;expression2&gt; 모두 부울 값이어야 합니다. 결과는 부울 값입니다.</td><td><pre>3.14 &gt; 2 및 3.15 &lt; 1</pre></td></tr>
<tr ><td>또는</td><td><p><pre>&lt;expression1&gt; 또는 &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; 및 &lt;expression2&gt; 모두 부울 값이어야 합니다.</p><p> 결과는 부울 값입니다.</p></td><td><p><pre>3.14 &gt; 2 또는 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt;은 boolean이어야 합니다.</p><p> 결과는 부울 값입니다.</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## 비교

<table>
<thead>
<tr ><th  >연산자</th><th  >리터럴 식 </th><th  >예제</th></tr>
</thead>
<tbody><tr ><td>은(는) null입니다.</td><td><p><pre>&lt;expression&gt;이(가) null입니다.</pre></p><p>결과는 부울 값입니다.</p><p>null은 표현식에 평가된 값이 없음을 의미합니다.</p></td><td><pre>@{BarBeacon.location}이(가) null입니다.</pre></td></tr>
<tr ><td>은(는) null이 아닙니다.</td><td><p><pre>&lt;expression&gt;이(가) null이 아닙니다.</pre></p><p>결과는 부울 값입니다.</p><p>null은 표현식에 평가된 값이 없음을 의미합니다.</p></td><td><pre>@ null이 아님</pre></td></tr>
<tr ><td>은(는) null입니다.</td><td><p><pre>&lt;expression&gt;에 null이 있습니다.</pre>&lt;expression&gt;은(는) 목록이어야 합니다.</p><p>결과는 부울 값입니다.</p><p>목록에 null 값이 하나 이상 포함되어 있는지 확인하는 데 유용합니다.</p></td><td><p><pre>["foo", "bar", null]이 null입니다.</pre></p>return true<p><pre>["foo", "bar", ""]이(가) null입니다.</pre></p> ""이(가) null로 간주되지 않으므로 false를 반환합니다.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; 및 &lt;expression2&gt; 모두 동일한 데이터 형식을 가져야 합니다.</p><p> 결과는 부울 값입니다.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> &lt;expression1&gt; 및 &lt;expression2&gt; 모두 동일한 데이터 형식을 가져야 합니다.</p><p> 결과는 부울 값입니다.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo"!= "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>datetime과 비교할 수 있습니다.</p><p>Date timeonly는 Date-timeonly와 비교할 수 있습니다.</p><p>정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.</p><p>다른 조합은 금지.</p><p>결과는 부울 값입니다.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>datetime과 비교할 수 있습니다.</p><p>Date timeonly는 Date-timeonly와 비교할 수 있습니다.</p><p>정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.</p><p>다른 조합은 금지.</p><p>결과는 부울 값입니다.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>datetime과 비교할 수 있습니다.</p><p>Date timeonly는 Date-timeonly와 비교할 수 있습니다.</p><p>정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.</p><p>다른 조합은 금지.</p><p>결과는 부울 값입니다.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>datetime과 비교할 수 있습니다.</p><p>Date timeonly는 Date-timeonly와 비교할 수 있습니다.</p><p>정수 또는 소수는 모두 정수 또는 소수와 비교할 수 있습니다.</p><p>다른 조합은 금지.</p><p>결과는 부울 값입니다.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## 산술

<table>
<thead>
<tr ><th  >연산자</th><th>리터럴 식 </th><th  >예제</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>두 표현식은 모두 숫자(정수 또는 소수)여야 합니다. </p><p>결과는 숫자이기도 합니다.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>반환 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> 두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.</p><p> 결과는 숫자이기도 합니다.</p></td><td><p><pre>2 - 1</pre></p>반환 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>두 표현식은 모두 숫자(정수 또는 소수)여야 합니다. </p><p>결과는 숫자이기도 합니다.</p><p>&lt;expression2&gt;은(는) 0이 아니어야 합니다(0 반환).</p></td><td><p><pre>4 / 2</pre></p>반환 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> 두 표현식은 모두 숫자(정수 또는 소수)여야 합니다. </p><p>결과는 숫자이기도 합니다.</p></td><td><p><pre>3 * 4</pre></p>반환 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>두 표현식은 모두 숫자(정수 또는 소수)여야 합니다.</p><p> 결과는 숫자이기도 합니다.</p></td><td><p><pre>3 % 2</pre></p>반환 1.</td></tr>
</tbody>
</table>

## 수학

<table>
<thead>
<tr ><th  >연산자</th><th  >리터럴 식 </th><th  >예제</th></tr>
</thead>
<tbody><tr ><td>숫자</td><td><p><pre>&lt;expression&gt; is numeric</pre></p><p>식의 유형은 정수 또는 소수입니다.</p></td><td><pre>@ 숫자</pre></td></tr>
<tr ><td>정수</td><td><p><pre>&lt;expression&gt;은(는) 정수입니다.</pre></p><p>표현식 유형은 정수입니다.</p></td><td><pre>@ is 정수</pre></td></tr>
<tr ><td>decimal</td><td><p><pre>&lt;expression&gt; is decimal</pre></p><p>표현식 유형은 소수입니다.</p></td><td><pre>@ decimal</pre></td></tr>

## 문자열

<table>
<thead>
<tr ><th  >연산자</th><th  >리터럴 식 </th><th  >예제</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;식&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;문자열&gt;</pre></p><p>두 표현식을 연결합니다. </p><p>하나의 표현식은 체인 문자열이어야 합니다.</p></td><td><p><pre>"현재 시간은 " + (now()입니다.</pre></p> 반환 "현재 시간은 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " 는 현재 시간입니다."</pre></p>"2019-09-23T09:30:06.693Z가 현재 시간입니다"를 반환합니다.<p><pre>"a" + "b" + "c" + 1234</pre></p> "abc1234"를 반환합니다.</td></tr>
</tbody>
</table>

## 날짜

<table>
<thead>
<tr ><th  >연산자</th><th  >리터럴 식 </th><th  >예제</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>dateTime, dateTimeOnly 또는 기간에 기간을 추가합니다.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>반환: 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>반환: 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>현재 시간으로부터 1시간 후 dateTime(UTC 표준 시간대 포함)을 반환합니다.</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>PT2H 반환</p></td></tr>
</tbody>
</table>