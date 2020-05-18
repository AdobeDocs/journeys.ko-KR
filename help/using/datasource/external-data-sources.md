---
title: '외부 데이터 소스 '
description: '외부 데이터 소스를 구성하는 방법 살펴보기 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1c4eed8360efcbfcaa5e54c8831e1a4b2ecc02e
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 0%

---



# 외부 데이터 소스 {#concept_t2s_kqt_52b}

외부 데이터 소스를 사용하면 타사 시스템에 대한 연결을 정의할 수 있습니다. 예를 들어 호텔 예약 시스템을 사용하여 개인이 회의실을 등록한 적이 있는지 확인할 수 있습니다. 내장된 경험 플랫폼 데이터 소스와 달리 외부 데이터 소스를 원하는 만큼 만들 수 있습니다.

POST 또는 GET 및 반환 JSON을 사용하는 REST API가 지원됩니다. API 키, 기본 및 사용자 정의 인증 모드가 지원됩니다.

제가 사용하고자 하는 날씨 API 서비스의 예를 들어, 실시간 기상 데이터에 따라 고객 여정의 행동을 맞춤화할 수 있습니다.

다음은 API 호출의 두 가지 예입니다.

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

이 호출은 기본 URL(_https://api.adobeweather.org/weather_), 두 개의 매개 변수 세트(도시의 경우 &quot;city&quot;, 위도 및 경도의 경우 &quot;위도/긴&quot;) 및 API 키(appid)로 구성됩니다.

다음은 새 외부 데이터 소스를 만들고 구성하는 주요 단계입니다.

1. 데이터 소스 목록에서 새 외부 데이터 소스 **[!UICONTROL Add]** 를 만들려면 을 클릭합니다.

   ![](../assets/journey25.png)

   화면의 오른쪽에 데이터 소스 구성 창이 열립니다.

   ![](../assets/journey26.png)

1. 데이터 소스의 이름을 입력합니다.

   >[!NOTE]
   >
   >공백이나 특수 문자는 사용하지 마십시오. 30자를 초과하여 사용하지 마십시오.

1. 데이터 소스에 설명을 추가합니다. 이 단계는 선택 사항입니다.
1. 외부 서비스의 URL을 추가합니다. Adobe 예제: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >보안상의 이유로 HTTPS를 사용하는 것이 좋습니다. 또한 공개적으로 사용할 수 없는 Adobe 주소 및 IP 주소 사용은 허용되지 않습니다.

   ![](../assets/journey27.png)

1. 외부 서비스 구성에 따라 인증을 구성합니다. **[!UICONTROL No authentication]**, **[!UICONTROL Basic]****[!UICONTROL Custom]** 또는 **[!UICONTROL API key]**. 사용자 정의 인증 모드에 대한 자세한 내용은 을(를) 참조하십시오 [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). 이 예에서는 다음을 선택합니다.


   * **[!UICONTROL Type]**: &quot;API 키&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot;(API 키의 값입니다)
   * **[!UICONTROL Name]**: &quot;appid&quot;(API 키 매개 변수 이름)
   * **[!UICONTROL Location]**: &quot;쿼리 매개 변수&quot;(API 키는 URL에 있음)
   ![](../assets/journey28.png)

1. 클릭하여 각 API 매개 변수 세트에 대한 새 필드 그룹을 추가합니다 **[!UICONTROL Add a New Field Group]**. 필드 그룹 이름에 공백이나 특수 문자를 사용하지 마십시오. 이 예에서는 각 매개 변수 세트(구/군/도)에 대해 하나씩 두 개의 필드 그룹을 만들어야 합니다.

&quot;long/lat&quot; 매개 변수 세트의 경우 다음 정보가 있는 필드 그룹을 만듭니다.

* **[!UICONTROL Used in]**: 필드 그룹을 사용하는 여정 수를 표시합니다. 이 필드 그룹을 사용하는 여행 목록을 표시하려면 **[!UICONTROL View journeys]** 아이콘을 클릭할 수 있습니다.
* **[!UICONTROL Method]**: POST 또는 GET 메서드를 선택합니다. GET 방법을 선택합니다.
* **[!UICONTROL Cache duration]**: 우리의 경우, 우리는 날씨를 10분 동안 캐시하기를 원합니다.
* **[!UICONTROL Response Payload]**: 필드 내부를 **[!UICONTROL Payload]** 클릭하고 호출에서 반환된 페이로드 예제를 붙여 넣습니다. 예를 들어 날씨 API 웹 사이트에서 발견된 페이로드를 사용했습니다. 필드 유형이 올바른지 확인합니다. API가 호출될 때마다 시스템은 페이로드 예제에 포함된 모든 필드를 검색합니다. 현재 전달된 페이로드를 변경하려면 **[!UICONTROL Paste a new payload]** 클릭을 할 수 있습니다.
* **[!UICONTROL Dynamic Values]**: 이 예에서는 &quot;long,lat&quot;라는 혼수상태로 구분된 다른 매개 변수를 입력합니다. 매개 변수 값은 실행 컨텍스트에 따라 달라지므로 여정에서 정의됩니다. 을 참조하십시오 [](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: 이 필드는 예제에 표시되지 않습니다. POST 메서드를 선택한 경우에만 사용할 수 있습니다. 타사 시스템으로 보낼 페이로드를 붙여넣습니다.

매개 변수가 필요한 GET 호출의 경우 필드에 매개 변수를 **[!UICONTROL Parameters]** 입력하면 호출 끝에 매개 변수가 자동으로 추가됩니다. POST 호출의 경우 다음을 수행해야 합니다.

* 필드의 호출 시간에 전달할 매개 변수를 **[!UICONTROL Parameter]** 나열합니다(아래 예: &quot;identifier&quot;).
* 전송된 페이로드 본문에 동일한 구문을 사용하여 지정합니다. 이렇게 하려면 다음을 추가해야 합니다. &quot;param&quot;: &quot;name of your parameter&quot;(아래 예에서) &quot;identifier&quot;). 아래 구문을 따르십시오.

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

클릭 **[!UICONTROL Save]**.

이제 데이터 소스가 구성되며, 여정의 조건에서 또는 이메일을 개인화하기 위해 사용될 준비가 되었습니다. 기온이 섭씨 30도를 넘으면 특정한 통신을 하기로 결정할 수 있다.

## 사용자 정의 인증 모드{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="사용자 정의 인증 정보"
>abstract="사용자 정의 인증 모드는 OAuth2와 같은 API 래핑 프로토콜을 호출하는 복잡한 인증에 사용됩니다. 작업 실행은 두 단계로 이루어집니다. 첫째, 액세스 토큰을 생성하기 위해 끝점에 대한 호출이 수행됩니다. 그런 다음 액세스 토큰이 동작의 HTTP 요청에 삽입됩니다."

이 인증 모드는 작업에 대한 실제 HTTP 요청에서 주입되는 액세스 토큰을 검색하기 위해 OAuth2와 같은 API 래핑 프로토콜을 호출하는 데 자주 사용되는 복잡한 인증에 사용됩니다.

사용자 정의 인증을 구성할 때 아래 단추를 클릭하여 사용자 정의 인증 페이로드가 올바르게 구성되어 있는지 확인할 수 있습니다.

![](../assets/journey29-bis.png)

테스트가 성공하면 단추가 녹색으로 바뀝니다.

![](../assets/journey29-ter.png)

이 인증을 통해 작업 실행은 두 단계로 이루어집니다.

1. 끝점을 호출하여 액세스 토큰을 생성합니다.
1. 올바른 방식으로 액세스 토큰을 삽입하여 REST API를 호출합니다.

이 인증에는 두 부분이 있습니다.

액세스 토큰을 생성하기 위해 호출할 끝점의 정의입니다.

* endpoint: 끝점을 생성하는 데 사용할 URL
* 끝점에 대한 HTTP 요청의 메서드(GET 또는 POST)
* 헤더: 필요한 경우 이 호출에서 헤더로 주입할 키/값 쌍
* body: 메서드가 POST인 경우 호출의 본문을 설명합니다. bodyParams(키/값 쌍)에 정의된 제한된 본문 구조를 지원합니다. bodyType은 호출에서 본문의 형식 및 인코딩에 대해 설명합니다.
   * &#39;form&#39;: 즉, 컨텐츠 유형이 application/x-www-form-urlencoded(charset UTF-8)이고 키/값 쌍은 다음과 같이 직렬화됩니다. key1=value1&amp;key2=value2&amp;..
   * &#39;json&#39;: 즉, 컨텐츠 유형이 application/json(charset UTF-8)이 되고 키 값 쌍은 다음과 같이 json 개체로 직렬화됩니다. _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ..}_

작업의 HTTP 요청에서 액세스 토큰을 삽입해야 하는 방식에 대한 정의:

* authorizationType: 생성된 액세스 토큰을 작업에 대한 HTTP 호출에 삽입하는 방법을 정의합니다. 가능한 값은 다음과 같습니다.

   * wrider: 권한 부여 헤더에 다음과 같은 액세스 토큰을 삽입해야 함을 나타냅니다. _인증: 베어러 &lt;액세스 토큰>_
   * header: 액세스 토큰을 헤더로 삽입해야 하며 속성 tokenTarget에 의해 정의된 헤더 이름을 나타냅니다. 예를 들어 tokenTarget이 myHeader인 경우 액세스 토큰은 다음과 같이 헤더로 주입됩니다. _myHeader: &lt;액세스 토큰>_
   * queryParam: access 토큰이 속성 tokenTarget에 의해 정의된 쿼리 매개 변수 이름인 queryParam으로 삽입되어야 함을 나타냅니다. 예를 들어 tokenTarget이 myQueryParam인 경우 작업 호출의 URL은 다음과 같습니다. _&lt;url>?myQueryParam=&lt;액세스 토큰>_

* tokenInResponse: 인증 호출에서 액세스 토큰을 추출하는 방법을 나타냅니다. 이 속성은 다음을 수행할 수 있습니다.
   * &#39;response&#39;: HTTP 응답이 액세스 토큰임을 나타냅니다.
   * json의 선택기(응답이 json이라고 가정할 경우, XML과 같은 다른 형식은 지원하지 않습니다.) 이 선택기의 형식은 _json://&lt;액세스 토큰 속성에 대한 경로>입니다_. 예를 들어, 호출의 응답이 _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_&#x200B;토큰은 다음과 같습니다. _json: //access_token_

이 인증의 형식은 다음과 같습니다.

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```
