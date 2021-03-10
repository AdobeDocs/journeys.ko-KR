---
product: adobe campaign
solution: Journey Orchestration
title: 매핑 API 설명
description: 매핑 API에 대해 자세히 알아보십시오.
products: journeys
feature: 여정
role: 비즈니스 전문가
level: 중간
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 0%

---


# 매핑 API 작업

## 소개

[!DNL Journey Orchestration]의 API는 5000 이벤트/초를 지원하지만 일부 외부 시스템 또는 API는 동일한 처리량을 가질 수 없습니다. 이러한 이유로 [!DNL Journey Orchestration]에 Caping API라는 전용 기능이 포함되어 있어 외부 시스템에 부과하는 속도를 모니터링하고 제한합니다.

데이터 소스 구성 중에 여정에서 사용할 추가 정보를 검색할 시스템 연결을 정의하거나 작업 정의에 대해 메시지 또는 API 호출을 전송하도록 제3자 시스템 연결을 구성합니다. 여정에서 API 호출을 수행할 때마다 설정 API가 쿼리되고 API 엔진을 통해 호출이 수행됩니다. 정의된 제한이 있으면 호출이 거부되고 외부 시스템에 과부하가 발생하지 않습니다.

작업 또는 데이터 소스 구성에 대한 자세한 내용은 [작업 ](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) 또는 [데이터 소스 정보](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)를 참조하십시오.


## 리소스

>[!NOTE]
>
>[!DNL Journey Orchestration] 매핑 API는 [여기](https://adobedocs.github.io/JourneyAPI/docs/)에서 사용할 수 있는 Swagger 파일 내에 설명되어 있습니다.

이 API를 [!DNL Journey Orchestration] 인스턴스와 함께 사용하려면 AdobeI/O 콘솔을 사용해야 합니다. 이 [Adobe 개발자 콘솔 시작](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)을 따라 시작한 다음 이 페이지의 섹션을 사용할 수 있습니다.

통합을 테스트하고 준비하기 위해 Postman 컬렉션은 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)에서 사용할 수 있습니다.

## 인증

### API 액세스 설정

[!DNL Journey Orchestration] API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)에 자세히 설명되어 있습니다.

>[!CAUTION]
>
>Adobe I/O에서 인증서를 관리하려면 조직에 대한 <b>시스템 관리자</b> 권한이 있는지 또는 관리 콘솔에 [개발자 계정](https://helpx.adobe.com/enterprise/using/manage-developers.html)이(가) 있는지 확인합니다.

1. **디지털 인증서가 있는지** 확인하거나 필요한 경우 디지털 인증서를 만듭니다. 인증서와 함께 제공된 공개 및 개인 키는 다음 단계에 필요합니다.
1. **서비스 Adobe I/O에 대한 새  [!DNL Journey Orchestration]** 통합을 만들고 구성합니다. 제품 프로필 액세스 권한은 [!DNL Journey Orchestration] 및 Adobe Experience Platform에 필요합니다. 자격 증명이 생성됩니다(API 키, 클라이언트 암호...).
1. **이전에 생성된 자격 증명** 에서 JWT(JSON 웹 토큰)를 만들고 개인 키로 서명합니다. JWT는 ID를 확인하고 API에 대한 액세스 권한을 부여하기 위해 Adobe에 필요한 모든 ID 및 보안 정보를 인코딩합니다. 이 단계는 이 [섹션](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)에 자세히 설명되어 있습니다.
1. **POST 요청을** 통하거나 개발자 콘솔 인터페이스를 통해 JWT를 액세스 토큰으로 교환합니다. 이 액세스 토큰은 API 요청의 각 헤더에서 사용해야 합니다.

안전한 서비스 간 Adobe I/O API 세션을 설정하려면 Adobe 서비스에 대한 모든 요청에는 인증 헤더에 아래 정보가 포함되어야 합니다.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:개인 조직 ID이며 각 인스턴스에 대해 Adobe에서 하나의 조직 ID를 제공합니다.

   * &lt;organization> :프로덕션 인스턴스

   조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 Adobe I/O으로 검색할 수도 있습니다(라이선스 목록에서 <a href="https://www.adobe.io/authentication.html">Adobe I/O 설명서</a> 참조).

* **&lt;access_token>**:POST 요청을 통해 JWT를 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;api_key>**:개인 API 키. [!DNL Journey Orchestration] 서비스에 대한 새 통합을 만든 후 Adobe I/O에서 제공됩니다.



## 매핑 API 설명

매핑 API를 사용하면 매핑 구성을 만들고, 구성하고, 모니터링할 수 있습니다.

| 방법 | 경로 | 설명 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 끝점 매핑 구성 목록 가져오기 |
| [!DNL POST] | /endpointConfigs | 끝점 매핑 구성 만들기 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 끝점 매핑 구성 배포 |
| [!DNL POST] | /endpointConfigs/`{uid}`/배포 취소 | 끝점 매핑 구성 배포 취소 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 끝점 매핑 구성을 배포할 수 있는지 여부 확인 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 끝점 매핑 구성 업데이트 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 끝점 매핑 구성 검색 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 끝점 매핑 구성 삭제 |

구성을 만들거나 업데이트할 때 페이로드의 구문과 무결성을 보장하기 위해 검사가 자동으로 수행됩니다.
일부 문제가 발생하면, 작업을 통해 경고 또는 오류를 반환하여 구성을 수정할 수 있습니다.



## 끝점 구성

끝점 구성의 기본 구조는 다음과 같습니다.

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

### 예제:

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

**canDeploy** 메서드가 호출되면 프로세스는 구성을 검증하고 고유 ID로 식별된 유효성 검사 상태를 반환합니다.

```
"ok" or "error"
```

잠재적 오류는 다음과 같습니다.

* **ERR_ENDPOINTCONFIG_100**:매핑 구성:없거나 잘못된 url
* **ERR_ENDPOINTCONFIG_101**:매핑 구성:잘못된 url
* **ERR_ENDPOINTCONFIG_102**:매핑 구성:잘못된 url:host:port에서 사용할 수 없는 wildchar in url
* **ERR_ENDPOINTCONFIG_103**:매핑 구성:HTTP 메서드가 없습니다.
* **ERR_ENDPOINTCONFIG_104**:매핑 구성:호출 등급이 정의되지 않음
* **ERR_ENDPOINTCONFIG_107**:매핑 구성:잘못된 최대 호출 수(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:매핑 구성:잘못된 최대 호출 수(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:매핑 구성:끝점 구성을 만들 수 없습니다.잘못된 페이로드
* **ERR_ENDPOINTCONFIG_112**:매핑 구성:끝점 구성을 만들 수 없습니다.JSON 페이로드 필요
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:잘못된 서비스 이름  `<!--<given value>-->`:은(는) &#39;dataSource&#39; 또는 &#39;action&#39;이어야 합니다.


잠재적 경고는 다음과 같습니다.

**ERR_ENDPOINTCONFIG_106**:매핑 구성:정의되지 않은 최대 HTTP 연결:기본적으로 제한 없음



## 활용 사례

이 섹션에서는 [!DNL Journey Orchestration]에서 매핑 구성을 관리하기 위해 수행할 수 있는 5가지 주요 사용 사례를 확인할 수 있습니다.

테스트 및 구성에 도움이 되도록 Postman 컬렉션을 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)에 사용할 수 있습니다.

이 Postman 컬렉션은 __[Adobe I/O 콘솔의 통합](https://console.adobe.io/integrations) > Try it out > Postman__&#x200B;을 통해 생성된 Postman 변수 컬렉션을 공유하도록 설정되었으며, 이 컬렉션은 선택한 통합 값으로 Postman 환경 파일을 생성합니다.

다운로드해서 Postman에 업로드한 후에는 다음 3가지 변수를 추가해야 합니다.`{JO_HOST}`,`{Base_Path}` 및 `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] 게이트웨이 URL
* `{BASE_PATH}` :API의 시작 지점. 값은 &#39;/authoring&#39;입니다.
* `{SANDBOX_NAME}` :API 작업이 발생할 샌드박스 이름에 해당하는  **x-sandbox-name** (예: &#39;prod&#39;) 헤더 자세한 내용은 [샌드박스 개요](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html)를 참조하십시오.

다음 섹션에서는 사용 사례를 수행하기 위한 Rest API 호출 순서 목록을 확인할 수 있습니다.

Use-Case n &quot;1:**새 매핑 구성 만들기 및 배포**

1. list
1. create
1. candeploy
1. 배포

Use-Case n &quot;2:**아직 배포되지 않은 매핑 구성 업데이트 및 배포**

1. list
1. get
1. update
1. candeploy
1. 배포

Use-Case n &quot;3:**배포된 매핑 구성 제거 및 삭제**

1. list
1. 배포 취소
1. delete

Use-Case n &quot;4:**배포된 매핑 구성을 삭제합니다.**

하나의 API 호출에서만 forceDelete 매개 변수를 사용하여 구성을 배포 취소 및 삭제할 수 있습니다.
1. list
1. delete(forceDelete 매개 변수 사용)

Use-Case(&quot;5&quot;의 경우):**이미 배포된 매핑 구성 업데이트**

1. list
1. get
1. update
1. 배포 취소
1. candeploy
1. 배포

