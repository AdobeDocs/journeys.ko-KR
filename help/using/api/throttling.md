---
product: adobe campaign
title: 조정 API 작업
description: 조절 API에 대한 자세한 정보
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 2%

---

# 조정 API 작업

Throttling API를 사용하면 조절 구성을 생성, 구성 및 모니터링할 수 있습니다.

>[!IMPORTANT]
>
>조직당 현재 하나의 구성만 허용됩니다. 구성은 프로덕션 샌드박스에서 정의해야 합니다(헤더에서 x-sandbox-name을 통해 제공).
>
>구성은 조직 수준에서 적용됩니다.

## 조절 API 설명 {#description}

| 메서드 | 경로 | 설명 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | 전송률 조절 구성 목록 가져오기 |
| [!DNL POST] | /throttlingConfigs | 전송률 조절 구성 만들기 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | 전송률 조절 구성 배포 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/배포 취소 | 전송률 조절 구성 배포 취소 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | 전송률 조절 구성을 배포할 수 있는지 확인합니다. |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | 조절 구성 업데이트 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | 조절 구성 검색 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | 조절 구성 삭제 |

## 조정 구성 {#configuration}

다음은 조절 구성의 구조입니다. **이름** 및 **설명** 속성은 선택 사항입니다.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

예:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## 오류

구성을 만들거나 업데이트할 때 프로세스는 해당 구성을 확인하고 고유 ID로 식별된 검증 상태를 반환합니다.

```
"ok" or "error"
```

>[!IMPORTANT]
>
>속성 **maxThroughput**, **urlPattern** 및 **메서드** 는 필수입니다.
>
>**maxThroughput** 값은 200-5000 범위 내에 있어야 합니다.

조절 구성을 생성, 삭제 또는 배포할 때 다음 오류가 발생할 수 있습니다.

* **ERR_THROTTLING_CONFIG_100**: 조정 구성: `<mandatory attribute>` 필수
* **ERR_THROTTLING_CONFIG_101**: 조정 구성: maxThroughput이 필요하며 200보다 크거나 같고 5000보다 작거나 같아야 합니다.
* **ERR_THROTTLING_CONFIG_104**: 조정 구성: 잘못된 url 패턴
* **ERR_THROTTLING_CONFIG_105**: 조정 구성: url 패턴의 호스트 부분에는 와일드카드를 사용할 수 없습니다
* **ERR_THROTTLING_CONFIG_106**: 조정 구성: 잘못된 페이로드
* **THROTTLING_CONFIG_DELETE_금지된_ERROR: 1456년**, &quot;배포된 전송률 조절 구성을 삭제할 수 없습니다. 삭제하기 전에 배포 취소&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457년**, &quot;조정 구성을 삭제할 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458년**, &quot;조정 구성을 배포할 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459년**, &quot;전송률 조절 구성을 배포할 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_GET_ERROR: 1460년**, &quot;조정 구성을 가져올 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461년**, &quot;조정 구성을 업데이트할 수 없습니다. 런타임 버전이 활성화되어 있지 않습니다.&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462년**, &quot;조정 구성을 업데이트할 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463년**, &quot;조정 구성에서 작업을 수행할 수 없습니다. 비prod sandbox
* **THROTTLING_CONFIG_CREATE_ERROR: 1464년**, &quot;조정 구성을 만들 수 없습니다. 예기치 않은 오류가 발생했습니다.
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465년**, &quot;조정 구성을 만들 수 없습니다. 조직당 하나의 구성이 허용됨
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, &quot;조정 구성을 배포할 수 없습니다. 이미 배포됨
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, &quot;throttling config not found&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, &quot;전송률 조절 구성을 배포할 수 없습니다. 아직 배포되지 않음&quot;

**오류 예**

비prod 샌드박스에서 구성을 작성하려고 할 때:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

지정된 sanbox가 없는 경우:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

다른 구성을 만들 때:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 사용 사례 {#uc}

테스트 및 구성에 도움이 되도록 Postman 컬렉션을 사용할 수 있습니다 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

이 Postman 컬렉션은 다음을 통해 생성된 Postman 변수 컬렉션을 공유하도록 설정되었습니다 __[Adobe I/O 콘솔의 통합](https://console.adobe.io/integrations) > 사용해 보기 > Postman용 다운로드__: 선택한 통합 값으로 Postman 환경 파일을 생성합니다.

Postman에 다운로드하여 업로드했으면 다음 세 가지 변수를 추가해야 합니다. `{JO_HOST}`,`{BASE_PATH}` 및 `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] 게이트웨이 URL
* `{BASE_PATH}` : API의 시작 지점입니다. 값은 &#39;/authoring&#39;입니다.
* `{SANDBOX_NAME}` : 헤더 **x-sandbox-name** 예를 들어, API 작업이 발생할 샌드박스 이름에 해당하는 &#39;prod&#39;)입니다. 자세한 내용은 [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko) 추가 정보.

다음 섹션에서는 사용 사례를 수행할 Rest API 호출 순서 목록을 확인할 수 있습니다.

사용 사례°1: **새로운 전송률 조절 구성 생성 및 배포**

1. 목록에 있는 참조 페이지를 나타냅니다
1. 만들기
1. 배포
1. 배포

사용 사례°2: **아직 배포되지 않은 조정 구성 업데이트 및 배포**

1. 목록에 있는 참조 페이지를 나타냅니다
1. get
1. 업데이트
1. 배포
1. 배포

사용 사례°3: **배포된 전송률 조절 구성 배포 취소 및 삭제**

1. 목록에 있는 참조 페이지를 나타냅니다
1. 배포 취소
1. delete

사용 사례°4: **배포된 전송률 조절 구성 삭제**

한 개의 API 호출만 사용할 수 있으며 forceDelete 매개 변수를 사용하여 구성을 배포 취소하고 삭제할 수 있습니다.

1. 목록에 있는 참조 페이지를 나타냅니다
1. delete, forceDelete 매개 변수 사용

사용 사례°5: **이미 배포된 전송률 조절 구성 업데이트**

>[!NOTE]
>
>업데이트하기 전에 구성 배포를 취소할 필요가 없습니다

1. 목록에 있는 참조 페이지를 나타냅니다
1. get
1. 업데이트

## 런타임 수준의 구성 수명 주기 {#config}

구성이 배포되지 않으면 런타임 수준에서 비활성 상태로 표시되고 보류 중인 이벤트는 24시간 동안 계속 처리됩니다. 그런 다음 런타임 서비스에서 삭제됩니다.

구성을 배포하지 않은 후 구성을 업데이트 및 재배포할 수 있습니다. 그러면 향후 작업 실행에서 고려되는 새 런타임 구성이 만들어집니다.

이미 배포된 구성을 업데이트할 때 새 값이 즉시 고려됩니다. 기본 시스템 리소스는 자동으로 조정됩니다. 이는 배포를 해제한 다음 구성을 재배포하는 것과 비교하여 최적입니다.

## 응답 예 {#responses}

**만들기 - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**업데이트 - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**읽기(업데이트 후) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**읽기(배포 후) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
