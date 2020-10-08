---
title: 데이터 유형
description: 고급 표현식의 데이터 유형에 대해 알아보기
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
source-wordcount: '675'
ht-degree: 3%

---


# 데이터 유형 {#concept_gp3_rj5_dgb}

기술적으로 상수에는 항상 데이터 형식이 포함됩니다. 리터럴 표현식에서는 값만 지정합니다. 값(예: 문자열, 정수, 십진수 등)에서 데이터 유형을 유추할 수 있습니다. 날짜 시간과 같은 특정 경우에는 표현에만 전용 기능을 사용합니다.

데이터 유형 표현식은 다음과 같습니다.

<table>
    <thead>
        <tr>
        <td>데이터 유형</td>
        <td>설명</td>
        <td>리터럴 표현</td>
        <td>예제</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>문자열</td>
        <td><p>공통 문자 시퀀스입니다.</p><p>사용 가능한 메모리의 양과 같은 환경에서 오는 암묵적인 것을 제외하고는 구체적인 크기가 없습니다.</p><p>JSON 형식:문자열</p><p>직렬화 형식:UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>정수</td>
        <td><p>-2^63부터 2^63-1까지의 정수 값.</p><p>JSON 형식:숫자</p></td>
        <td>&lt;정수 값&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>소수</td>
        <td><p>십진수.</p><p>부동 소수점 값:</p>
        <p>- double 형식의 가장 큰 양의 유한값(2-2^-52)x2^1023</p>
        <p> - 2-1022 유형의 양수 정규 값</p>
        <p> - 2p-1074 유형의 양수 0이 아닌 값</p><p>JSON 형식:숫자</p><p>직렬화 형식:'.' 사용 을 십진수 구분 기호로 사용합니다.</p></td>
        <td>&lt;정수 값&gt;.&lt;정수 값&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>소문자 기된 부울 값:true 또는 false</p><p>JSON 형식:부울</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>연도 시간대가 없는 날짜 시간을 나타내며, 년 개월 시간 분 초 밀리초로 표시됩니다.</p><p>표준 시간대를 저장하거나 나타내지 않습니다.</p><p>대신, 그것은 근무 시간에 보이는 것과 지역 시간과 함께 생일에 사용되는 날짜의 설명입니다.</p><p>오프셋 또는 시간대와 같은 추가 정보 없이 타임라인에서 즉시 표시할 수 없습니다.</p><p>직렬화 형식:ISO-8601 확장 오프셋 날짜-시간 형식.</p><p>DateTimeFormatter를 사용합니다.</p><p>ISO_LOCAL_DATE_TIME을 사용하여 값을 역직렬화하고 직렬화할 수 있습니다.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">자세히 알아보기</a></td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>시간대도 고려하는 날짜 시간 상수입니다.</p><p>UTC의 오프셋이 있는 날짜 시간을 나타냅니다. 오프셋에 대한 추가 정보와 함께 즉시 볼 수 있습니다. </p><p>세계 어느 곳에서 특정 '순간'을 표현하는 방법입니다.</p><p>JSON 형식:문자열.</p><p> toDateTime 함수로 캡슐화되어야 합니다.</p><p>
        직렬화 형식:ISO-8601 확장 오프셋 날짜-시간 형식.</p><p> DateTimeFormatter.ISO_OFFSET_DATE_TIME을 사용하여 값을 역직렬화하고 직렬화합니다.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">자세히 알아보기</a> 
        <p>epoch 값을 전달하는 정수도 전달할 수 있습니다.</p> <a href="https://www.epochconverter.com/">자세한 내용</a></p>
        <p>시간대는 오프셋 또는 표준 시간대 코드로 지정할 수 있습니다(예:유럽/파리, Z - UTC를 의미합니다.</p></td>
        <td><p>toDateTime("&lt;dateTime in ISO-8601 format&gt;")</p>
        <p>toDateTime(&lt;epoch의 정수 값(밀리초)&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>지속 시간</td>
        <td><p>시간 기반 시간(예: '34.5초')을 나타냅니다.</p><p> 이 모델은 수량과 시간을 밀리초 단위로 모델링합니다.</p><p>지원되는 임시 단위는 다음과 같습니다.밀리초, 초, 분, 시간, 일 중 하루가 24시간으로</p><p> 연도 및 달은 정해진 시간이 아니므로 지원되지 않습니다.</p><p>JSON 형식:문자열. toDuration 함수로 캡슐화되어야 합니다.</p><p>직렬화 형식:표준 시간대 ID를 역직렬화하려면 java 함수 java.time을 사용합니다.</p><p>Duration.parse:허용되는 포맷은 정확히 24시간으로 간주되는 날을 가진 ISO-8601 지속 시간 포맷인 PnDTnHn.nS를 기반으로 합니다.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">자세히 알아보기</a></td>
        <td><p>toDuration("&lt;duration in ISO-8601 format&gt;")</p><p>toDuration(&lt;duration in milliseconds&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5초</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— 구문: "20.345초"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — 구문: "15분"</pre></p>
        <p><pre>(분이 60초인 경우)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— 구문 분석: "10시간"</pre></p>
        <p><pre>(시간이 3600초인 경우)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— 구문: "2일"</pre></p>
        <p><pre>(하루 </pre></p>
        <p><pre>24시간 또는 86400초)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— parses as</pre></p>
        <p><pre>"2일, 3시간 4분"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— parses as</pre></p>
        <p><pre>"-6시간 + 3분"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— parses as</pre></p>
        <p><pre>"-6시간 및 -3분"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— parses as</pre></p>
        <p><pre>"+6시간 및 -3분"</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>구분 기호로 대괄호를 사용하는 쉼표로 구분된 표현식 목록입니다. 다형성은 지원되지 않으므로 목록에 포함된 모든 표현식의 유형이 같아야 합니다.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
