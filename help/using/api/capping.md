---
product: adobe campaign
title: API 설명 최대 가용량
description: 최대 가용량 API에 대해 자세히 알아보십시오.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# 최대 가용량 API 작업 {#work}

최대 가용량 API를 사용하면 최대 가용량 구성을 생성, 구성 및 모니터링할 수 있습니다.

## API 설명 최대 가용량

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

Postman에 다운로드하여 업로드했으면 다음 세 가지 변수를 추가해야 합니다. `{JO_HOST}`,`{BASE_PATH}` 및 `{SANDBOX_NAME}`.
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
