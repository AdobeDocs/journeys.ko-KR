---
product: adobe campaign
title: 최대 가용량 API 설명
description: 최대 가용량 API에 대해 자세히 알아보십시오.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 27%

---


# 최대 가용량 API 작업 {#work}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


최대 가용량 API를 사용하면 최대 가용량 구성을 만들고, 구성하고, 모니터링할 수 있습니다.

## 최대 가용량 API 설명

| 메서드 | 경로 | 설명 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 끝점 제한 구성 목록 가져오기 |
| [!DNL POST] | /endpointConfigs | 엔드포인트 제한 구성 만들기 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 끝점 제한 구성 배포 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 끝점 제한 구성 배포 해제 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 끝점 제한 구성을 배포할 수 있는지 확인 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 끝점 제한 구성 업데이트 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 끝점 제한 구성 검색 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 끝점 제한 구성 삭제 |

구성을 만들거나 업데이트할 때 페이로드의 구문 및 무결성을 보장하기 위해 자동으로 검사가 수행됩니다.
일부 문제가 발생하면 작업을 수행할 때 경고 또는 오류가 반환되어 구성을 수정하는 데 도움이 됩니다.

## 끝점 구성

다음은 끝점 구성의 기본 구조입니다.

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>**maxHttpConnections** 매개 변수는 선택 사항입니다. 이를 통해 Journey Optimizer이 외부 시스템에 대해 여는 연결 수를 제한할 수 있습니다.
>
>설정할 수 있는 최대값은 400입니다. 아무 것도 지정되지 않은 경우, 시스템은 시스템의 동적 확장에 따라 최대 수천 개의 연결을 열 수 있습니다.

### 예:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## 경고 및 오류

**canDeploy** 메서드가 호출되면 이 프로세스는 구성을 확인하고 다음 중 하나의 고유 ID로 확인된 유효성 검사 상태를 반환합니다.

```
"ok" or "error"
```

잠재적 오류는 다음과 같습니다.

* **ERR_ENDPOINTCONFIG_100**: 최대 구성: 누락되었거나 잘못된 url
* **ERR_ENDPOINTCONFIG_101**: 구성 제한: url 형식이 잘못되었습니다.
* **ERR_ENDPOINTCONFIG_102**: 최대 구성: url 형식이 잘못되었습니다. host:port에서 url의 와일드문자를 사용할 수 없습니다.
* **ERR_ENDPOINTCONFIG_103**: 최대 구성: HTTP 메서드가 없습니다.
* **ERR_ENDPOINTCONFIG_104**: 최대 구성: 호출 등급이 정의되지 않았습니다.
* **ERR_ENDPOINTCONFIG_107**: 최대 호출 수 제한 구성: 잘못된 최대 호출 수(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: 최대 호출 수 제한 구성: 잘못된 최대 호출 수(periodInMs)
* **ERR_ENDPOINTCONFIG_111**: 최대 구성: 끝점 구성을 만들 수 없음: 잘못된 페이로드
* **ERR_ENDPOINTCONFIG_112**: 최대 구성: 끝점 구성을 만들 수 없습니다. JSON 페이로드가 필요합니다.
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: 잘못된 서비스 이름 `<!--<given value>-->`: &#39;dataSource&#39; 또는 &#39;action&#39;이어야 합니다.

잠재적인 경고는 다음과 같습니다.

**ERR_ENDPOINTCONFIG_106**: 최대 구성: 최대 HTTP 연결이 정의되지 않음: 기본적으로 제한 없음

## 사용 사례

이 섹션에서는 [!DNL Journey Orchestration]에서 최대 가용량 구성을 관리하기 위해 수행할 수 있는 5가지 주요 사용 사례를 확인할 수 있습니다.

[여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)에서 테스트 및 구성에 도움이 되는 Postman 컬렉션을 사용할 수 있습니다.

이 Postman 컬렉션은 __[Adobe I/O Console의 통합](https://console.adobe.io/integrations) > 사용해 보기 > Postman용으로 다운로드__&#x200B;를 통해 생성된 Postman 변수 컬렉션을 공유하는 용도로 설정되었습니다. 이 옵션은 선택한 통합 값을 가진 Postman 환경 파일을 생성합니다.

다운로드하여 Postman에 업로드한 다음에는 `{JO_HOST}`, `{BASE_PATH}`, `{SANDBOX_NAME}` 세 가지 변수를 추가해야 합니다.
* `{JO_HOST}`: [!DNL Journey Orchestration] 게이트웨이 URL입니다.
* `{BASE_PATH}`: API의 시작 지점입니다. 값은 ‘/authoring’입니다.
* `{SANDBOX_NAME}`: API 작업이 발생할 샌드박스 이름에 해당하는 헤더 **x-sandbox-name**(예: ‘prod’)입니다.  자세한 내용은 [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko)를 참조하십시오.

다음 섹션에서는 사용 사례를 수행하기 위한 Rest API 호출 목록을 순서대로 확인할 수 있습니다.

사용 사례 n°1: **새 최대 가용량 구성 만들기 및 배포**

1. list
1. create
1. candeploy
1. deploy

사용 사례 n°2: **아직 배포되지 않은 최대 가용량 구성 업데이트 및 배포**

1. list
1. get
1. update
1. candeploy
1. deploy

사용 사례 n°3: **배포된 최대 가용량 구성 배포 취소 및 삭제**

1. list
1. undeploy
1. delete

사용 사례 n°4: **배포된 최대 가용량 구성을 삭제합니다.**

forceDelete 매개 변수를 사용하면 API 호출 단 한 번에 구성의 배포를 취소하고 삭제할 수 있습니다.
1. list
1. delete, with forceDelete param

사용 사례 n°5: **이미 배포된 최대 가용량 구성 업데이트**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
