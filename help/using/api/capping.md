---
product: adobe campaign
title: API 설명 최대 가용량
description: 최대 가용량 API에 대해 자세히 알아보십시오.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 3%

---

# API 최대 가용량 작업

## 소개

[!DNL Journey Orchestration]의 API는 5000 이벤트/초 를 지원하지만 일부 외부 시스템 또는 API에는 동일한 처리량을 가질 수 없습니다. 그래서 [!DNL Journey Orchestration] 에는 외부 시스템에 적용하는 비율을 모니터링하고 제한하는 최대 가용량 API라는 전용 기능이 포함되어 있습니다.

데이터 소스 구성 중에 여정에 사용할 추가 정보를 검색할 시스템에 대한 연결을 정의하거나, 작업 정의에 대해 메시지나 API 호출을 전송할 서드파티 시스템의 연결을 구성합니다. 여정에 의해 API 호출이 수행될 때마다 최대 가용량 API가 쿼리되고, 호출이 API 엔진을 통해 옵니다. 정의된 제한이 있으면 호출이 거부되고 외부 시스템이 오버로드되지 않습니다.

외부 데이터 소스의 경우 초당 최대 호출 수는 15로 설정됩니다. 호출 수가 초당 15개를 초과하는 경우 나머지 호출은 무시됩니다. 비공개 외부 데이터 소스에 대해 이 제한을 늘릴 수 있습니다. 엔드포인트를 Adobe에 포함하려면에 허용 목록에 추가하다 문의하십시오. 이는 공용 외부 데이터 소스에는 사용할 수 없습니다. 외부 시스템을 통합할 때 모범 사례 및 보안 문제에 대한 자세한 내용은 다음을 참조하십시오 [페이지](../about/external-systems.md).

작업 또는 데이터 소스 구성에 대한 자세한 내용은 [작업](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) 또는 [데이터 소스](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## 리소스

>[!NOTE]
>
>다음 [!DNL Journey Orchestration] 최대 가용량 API는 Swagger 파일 내에 설명되어 있습니다 [여기](https://adobedocs.github.io/JourneyAPI/docs/).

와 함께 이 API를 사용하려면 [!DNL Journey Orchestration] 예를 들어 AdobeI/O 콘솔을 사용해야 합니다. 다음을 수행하여 시작할 수 있습니다 [Adobe 개발자 콘솔 시작하기](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 그런 다음 이 페이지의 섹션을 사용합니다.

통합을 테스트하고 준비하기 위해 Postman 컬렉션을 사용할 수 있습니다 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## 인증

### API 액세스 설정

[!DNL Journey Orchestration] API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Adobe I/O에서 인증서를 관리하려면 <b>시스템 관리자</b> 조직 또는 [개발자 계정](https://helpx.adobe.com/kr/enterprise/using/manage-developers.html) 를 클릭하십시오.

1. **디지털 인증서가 있는지 확인**&#x200B;또는 필요한 경우 만들 수 있습니다. 인증서와 함께 제공된 공개 및 개인 키는 다음 단계에 필요합니다.
1. **에 대한 새 통합 만들기 [!DNL Journey Orchestration] 서비스** Adobe I/O 및 구성합니다. 에 대한 제품 프로필 액세스 권한이 필요합니다 [!DNL Journey Orchestration] 및 Adobe Experience Platform. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호...).
1. **JSON 웹 토큰(JWT) 만들기** 이전에 생성된 자격 증명에서 개인 키로 서명합니다. JWT는 Adobe이 ID를 확인하고 API에 대한 액세스 권한을 부여하는 데 필요한 모든 ID 및 보안 정보를 인코딩합니다. 이 단계는 다음 사항에 자세히 설명되어 있습니다 [섹션](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **JWT를 액세스 토큰으로 교환** POST 요청 또는 개발자 콘솔 인터페이스를 통해 이 액세스 토큰은 API 요청의 각 헤더에서 사용해야 합니다.

보안 서비스 간 Adobe I/O API 세션을 설정하려면 Adobe 서비스에 대한 모든 요청은 인증 헤더에 아래 정보를 포함해야 합니다.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: 개인 조직 ID이며, 각 인스턴스에 대해 Adobe이 하나의 조직 ID를 제공합니다.

   * &lt;organization> : 프로덕션 인스턴스

   조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 라이선스 목록에서 Adobe I/O으로 검색할 수도 있습니다( <a href="https://www.adobe.io/authentication.html">Adobe I/O 설명서</a>).

* **&lt;access_token>**: POST 요청을 통해 JWT를 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;api_key>**: 개인 API 키 를 참조하십시오. 새 통합을 만든 후 Adobe I/O에 제공됩니다 [!DNL Journey Orchestration] 서비스.



## API 설명 최대 가용량

최대 가용량 API를 사용하면 최대 가용량 구성을 생성, 구성 및 모니터링할 수 있습니다.

| 메서드 | 경로 | 설명 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 끝점 최대 가용량 구성 목록 가져오기 |
| [!DNL POST] | /endpointConfigs | 끝점 최대 가용량 구성 만들기 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 끝점 최대 가용량 구성 배포 |
| [!DNL POST] | /endpointConfigs/`{uid}`/배포 취소 | 끝점 최대 가용량 구성 배포 취소 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 끝점 최대 가용량 구성을 배포할 수 있는지 여부를 확인합니다 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 끝점 최대 가용량 구성 업데이트 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 끝점 최대 가용량 구성 검색 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 엔드포인트 캡핑 구성 삭제 |

구성을 만들거나 업데이트할 때 페이로드의 구문과 무결성을 보장하기 위해 검사가 자동으로 수행됩니다.
일부 문제가 발생하면 작업을 통해 경고 또는 오류를 반환하여 구성을 수정할 수 있습니다.



## 끝점 구성

다음은 끝점 구성의 기본 구조입니다.

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### 예:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## 경고 및 오류

다음의 경우 **canDeploy** 메서드가 호출되면 프로세스가 구성을 확인하고 고유 ID로 식별된 유효성 검사 상태를 반환합니다.

```
"ok" or "error"
```

잠재적 오류는 다음과 같습니다.

* **ERR_ENDPOINTCONFIG_100**: 최대 가용량 구성: URL이 없거나 잘못되었습니다.
* **ERR_ENDPOINTCONFIG_101**: 최대 가용량 구성: 잘못된 url
* **ERR_ENDPOINTCONFIG_102**: 최대 가용량 구성: 잘못된 url: url의 와일드카드 문자는 host:port에서 허용되지 않습니다.
* **ERR_ENDPOINTCONFIG_103**: 최대 가용량 구성: HTTP 메서드 누락
* **ERR_ENDPOINTCONFIG_104**: 최대 가용량 구성: 정의된 통화 등급 없음
* **ERR_ENDPOINTCONFIG_107**: 최대 가용량 구성: 잘못된 최대 호출 수(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: 최대 가용량 구성: 잘못된 최대 호출 수(periodInMs)입니다.
* **ERR_ENDPOINTCONFIG_11**: 최대 가용량 구성: 끝점 구성을 만들 수 없습니다. 잘못된 페이로드
* **ERR_ENDPOINTCONFIG_112**: 최대 가용량 구성: 끝점 구성을 만들 수 없습니다. json 페이로드 필요
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: 잘못된 서비스 이름 `<!--<given value>-->`: &#39;dataSource&#39; 또는 &#39;action&#39;이어야 합니다.


잠재적 경고는 다음과 같습니다.

**ERR_ENDPOINTCONFIG_106**: 최대 가용량 구성: 최대 HTTP 연결이 정의되지 않았습니다. 기본적으로 제한되지 않음



## 사용 사례

이 섹션에서는 에서의 최대 가용량 구성을 관리하기 위해 수행할 수 있는 5가지 기본 사용 사례를 확인할 수 있습니다 [!DNL Journey Orchestration].

테스트 및 구성에 도움이 되도록 Postman 컬렉션을 사용할 수 있습니다 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

이 Postman 컬렉션은 다음을 통해 생성된 Postman 변수 컬렉션을 공유하도록 설정되었습니다 __[Adobe I/O 콘솔의 통합](https://console.adobe.io/integrations) > 사용해 보기 > Postman용 다운로드__: 선택한 통합 값으로 Postman 환경 파일을 생성합니다.

Postman에 다운로드하여 업로드했으면 다음 세 가지 변수를 추가해야 합니다. `{JO_HOST}`,`{Base_Path}` 및 `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] 게이트웨이 URL
* `{BASE_PATH}` : API의 시작 지점입니다. 값은 &#39;/authoring&#39;입니다.
* `{SANDBOX_NAME}` : 헤더 **x-sandbox-name** 예를 들어, API 작업이 발생할 샌드박스 이름에 해당하는 &#39;prod&#39;)입니다. 자세한 내용은 [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko) 추가 정보.

다음 섹션에서는 사용 사례를 수행할 Rest API 호출 순서 목록을 확인할 수 있습니다.

사용 사례°1: **새 최대 가용량 구성 만들기 및 배포**

1. 목록에 있는 참조 페이지를 나타냅니다
1. 만들기
1. 배포
1. 배포

사용 사례°2: **아직 배포되지 않은 최대 가용량 구성 업데이트 및 배포**

1. 목록에 있는 참조 페이지를 나타냅니다
1. get
1. 업데이트
1. 배포
1. 배포

사용 사례°3: **배포된 최대 가용량 구성 배포 취소 및 삭제**

1. 목록에 있는 참조 페이지를 나타냅니다
1. 배포 취소
1. delete

사용 사례°4: **배포된 최대 가용량 구성을 삭제합니다.**

한 개의 API 호출만 사용할 수 있으며 forceDelete 매개 변수를 사용하여 구성을 배포 취소하고 삭제할 수 있습니다.
1. 목록에 있는 참조 페이지를 나타냅니다
1. delete, forceDelete 매개 변수 사용

사용 사례°5: **이미 배포된 최대 가용량 구성 업데이트**

1. 목록에 있는 참조 페이지를 나타냅니다
1. get
1. 업데이트
1. 배포 취소
1. 배포
1. 배포
