---
product: adobe campaign
title: Throttling API로 작업하기
description: Throttling API에 대해 자세히 알아보기
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 7b8c9d2bfe244b040a9064a7a240ea6f43cc8b41
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 96%

---

# Throttling API로 작업하기

Throttling API를 사용하면 초당 전송되는 이벤트 수를 제한하기 위해 제한 구성을 만들고 구성하고 모니터링할 수 있습니다.

>[!IMPORTANT]
>
>현재 조직당 하나의 구성만 허용됩니다. 구성은 프로덕션 샌드박스서 정의해야 합니다(헤더의 x-sandbox-name을 통해 지정).
>
>구성은 조직 수준에서 적용됩니다.
>
>API에서 설정한 제한에 도달하면 이를 초과하는 이벤트는 최대 6시간 동안 큐에 보관됩니다. 이 값은 수정할 수 없습니다.

## Throttling API 설명 {#description}

| 메서드 | 경로 | 설명 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | 스로틀링 구성 목록 가져오기 |
| [!DNL POST] | /throttlingConfigs | 스로틀링 구성 만들기 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | 스로틀링 구성 배포 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | 스로틀링 구성 배포 취소 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | 스로틀링 구성을 배포할 수 있는지 확인 |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | 스로틀링 구성 업데이트 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | 스로틀링 구성 검색 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | 스로틀링 구성 삭제 |

## 스로틀링 구성 {#configuration}

다음은 스로틀링 구성의 구조입니다. **name** 및 **description** 속성은 선택 사항입니다.

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

구성을 만들거나 업데이트하면 프로세스는 해당 구성을 확인하고 고유 ID로 식별되는 검증 상태를 반환합니다.

```
"ok" or "error"
```

>[!IMPORTANT]
>
>속성 **maxThroughput**, **urlPattern**, **methods**&#x200B;는 필수 입력 사항입니다.
>
>**maxThroughput** 값은 200~5000 사이에 있어야 합니다.

스로틀링 구성을 만들거나 삭제 또는 배포할 때 다음 오류가 발생할 수 있습니다.

* **ERR_THROTTLING_CONFIG_100**: 스로틀링 구성: `<mandatory attribute>` 필수
* **ERR_THROTTLING_CONFIG_101**: 스로틀링 구성: maxThroughput은 필수 입력 사항이며 200~5000 사이여야 합니다.
* **ERR_THROTTLING_CONFIG_104**: 스로틀링 구성: 잘못된 URL 패턴
* **ERR_THROTTLING_CONFIG_105**: 스로틀링 구성: URL 패턴의 호스트 부분에는 와일드카드를 사용할 수 없습니다.
* **ERR_THROTTLING_CONFIG_106**: 스로틀링 구성: 잘못된 페이로드
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, “배포한 스로틀링 구성을 삭제할 수 없습니다. 삭제하기 전에 배포를 취소하십시오.”
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, “스로틀링 구성을 삭제할 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, “스로틀링 구성을 배포할 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, “스로틀링 구성의 배포를 취소할 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_GET_ERROR: 1460**, “스로틀링 구성을 가져올 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, “스로틀링 구성을 업데이트할 수 없습니다. 런타임 버전이 활성 상태가 아닙니다.”
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, “스로틀링 구성을 업데이트할 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, “스로틀링 구성 작업을 수행할 수 없습니다. 비프로덕션 샌드박스입니다.”
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, “스로틀링 구성을 만들 수 없습니다. 예기치 않은 오류가 발생했습니다.”
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, “스로틀링 구성을 만들 수 없습니다. 조직당 하나의 구성만 허용됩니다.”
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, “스로틀링 구성을 배포할 수 없습니다. 이미 배포되었습니다.”
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, “스로틀링 구성을 찾을 수 없습니다.”
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, “스로틀링 구성의 배포를 취소할 수 없습니다. 아직 배포되지 않은 상태입니다.”

**오류 예시**

비프로덕션 샌드박스에서 구성을 작성하려는 경우:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

지정한 샌드박스가 존재하지 않는 경우:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

다른 구성을 만들려는 경우:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 사용 사례 {#uc}

[여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json)에서 테스트 및 구성에 도움이 되는 Postman 컬렉션을 사용할 수 있습니다.

이 Postman 컬렉션은 __[Adobe I/O Console의 통합](https://console.adobe.io/integrations) > 사용해 보기 > Postman용으로 다운로드__&#x200B;를 통해 생성된 Postman 변수 컬렉션을 공유하는 용도로 설정되었습니다. 이 옵션은 선택한 통합 값을 가진 Postman 환경 파일을 생성합니다.

다운로드하여 Postman에 업로드한 다음에는 `{JO_HOST}`, `{BASE_PATH}`, `{SANDBOX_NAME}` 세 가지 변수를 추가해야 합니다.
* `{JO_HOST}`: [!DNL Journey Orchestration] 게이트웨이 URL입니다.
* `{BASE_PATH}`: API의 시작 지점입니다. 값은 ‘/authoring’입니다.
* `{SANDBOX_NAME}`: API 작업이 발생할 샌드박스 이름에 해당하는 헤더 **x-sandbox-name**(예: ‘prod’)입니다.  자세한 내용은 [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko)를 참조하십시오.

다음 섹션에서는 사용 사례를 수행하기 위한 Rest API 호출 목록을 순서대로 확인할 수 있습니다.

사용 사례 1번: **새로운 스로틀링 구성을 만들고 배포하기**

1. list
1. create
1. candeploy
1. deploy

사용 사례 2번: **아직 배포하지 않은 스로틀링 구성을 업데이트하여 배포하기**

1. list
1. get
1. update
1. candeploy
1. deploy

사용 사례 3번: **배포한 스로틀링 구성의 배포를 취소하고 삭제하기**

1. list
1. undeploy
1. delete

사용 사례 4번: **배포한 스로틀링 구성 삭제하기**

forceDelete 매개 변수를 사용하면 API 호출 단 한 번에 구성의 배포를 취소하고 삭제할 수 있습니다.

1. list
1. delete, with forceDelete param

사용 사례 5번: **이미 배포한 스로틀링 구성 업데이트하기**

>[!NOTE]
>
>업데이트하기 전에 구성의 배포를 취소할 필요는 없습니다.

1. list
1. get
1. update

## 런타임 수준에서 본 구성의 수명 주기 {#config}

배포를 취소한 구성은 런타임 수준에서 비활성 상태로 표시되고 대기 중인 이벤트는 24시간 동안 계속 처리됩니다. 그 다음에는 해당 구성이 런타임 서비스에서 삭제됩니다.

구성의 배포를 취소한 후에 업데이트하여 재배포할 수 있습니다. 그러면 향후 작업 실행 시 고려할 새 런타임 구성이 만들어집니다.

이미 배포한 구성을 업데이트하면 새로운 값을 즉시 고려합니다. 기본 시스템 리소스는 자동으로 조정됩니다. 구성의 배포를 취소한 다음 재배포하는 것보다 적합한 방법입니다.

## 응답 예제 {#responses}

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
