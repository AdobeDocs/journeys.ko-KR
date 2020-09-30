---
title: 가져오기 내보내기 API 설명
description: 가져오기 내보내기 API에 대한 자세한 내용을 살펴보십시오.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c92d7a4e5ef02f87f705871cd0fdb8c2523966d2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 1%

---


# 내보내기 가져오기 API 작업

단일 API 호출을 사용하여 경로 버전 및 모든 관련 개체(여정, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 내보낼 수 있습니다. 내보내기 결과 페이로드를 사용하여 다른 환경(인스턴스 또는 샌드박스)으로 이동을 쉽게 가져올 수 있습니다.
이 기능을 사용하면 여러 인스턴스 간 또는 여러 테스트 환경 워크플로우의 경로를 관리할 수 있습니다.


## 리소스

Journey Orchestration 가져오기 내보내기 API는 [여기에서](https://adobedocs.github.io/JourneyAPI/docs/)사용할 수 있는 Swagger 파일 내에 설명되어 있습니다.

Journey Orchestration 인스턴스에서 이 API를 사용하려면 AdobeI/O 콘솔을 사용해야 합니다. 먼저 이 Adobe 개발자 콘솔 [로 시작하기를](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 시작한 다음 이 페이지의 섹션을 사용할 수 있습니다.

통합을 테스트하고 준비하려면 [여기에서 Postman 컬렉션을 이용할 수 있습니다](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## 내보내기-가져오기 흐름

다음 단계에 따라 여러 환경에서 경로를 내보내고 가져오는 것이 좋습니다.

1. 시작 환경에서 여정을 만들고 매개 변수를 지정합니다. [자세한 내용](https://docs.adobe.com/content/help/ko-KR/journeys/using/building-journeys/about-journey-building/journey.html)
1. 경로 버전에 오류가 없는지 확인합니다. [자세한 내용](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. UID **/list/journeys** API를 호출하여 최신 경로 버전의 UID를 검색합니다. 필요한 경우 최신 고객 경로 버전의 UID를 **찾아 볼 수`{uid}`있습니다** .
1. 시작 환경 매개 변수(orgID 및 sandboxName)를 사용하여 **내보내기** API를 호출합니다.
1. 반환 페이로드를 열고 다음 항목을 확인합니다.
   * 내보낸 여정에 **특정 자격 증명이**&#x200B;포함되어 있는 경우 이러한 자격 증명을 새 환경에 해당하는 자격 증명으로 대체해야 합니다.
   * 내보낸 여정에 **XDM 스키마를** 가리키는 **이벤트가**&#x200B;포함되어 있는 경우 ID 값이 다른 경우 xdmEntity 노드에서 새 환경의 스키마 ID로 스키마 ID 참조를 수동으로 업데이트해야 합니다. 각 이벤트에 대해 이 업데이트를 수행해야 합니다. [자세한 내용](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 여정에서 이메일, sms 또는 푸시 동작이 포함된 경우 대상 환경의 이름이 시작 환경의 이름과 다른 경우 템플릿 이름이나 mobileApp 이름을 업데이트해야 할 수 있습니다.
1. 대상 환경에서 **가져오기** API를 호출합니다. 가져오기 API를 원하는 만큼 호출할 수 있습니다. Import API를 호출할 때마다 UUID와 경로의 각 노드에 포함된 이름이 생성됩니다.
1. 여정을 가져오면 새로운 샌드박스 또는 환경에 게시할 수 있습니다.


## 인증

### API 액세스 설정

Journey Orchestration API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe I/O 설명서에 자세히 설명되어 있습니다](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Adobe I/O에서 인증서를 관리하려면 조직 또는 <b>개발자 계정에</b> 대한 [시스템 관리자](https://helpx.adobe.com/enterprise/using/manage-developers.html) 권한이 있어야 합니다. 관리 콘솔에서는개발자 계정이관리되어야 합니다.

1. **디지털 인증서가 있는지**&#x200B;확인하거나 필요한 경우 디지털 인증서를 만듭니다. 인증서와 함께 제공된 공개 및 개인 키는 다음 단계에 필요합니다.
1. **Adobe I/O에서[!DNL Journey Orchestration]서비스** 통합을 새로 만들어 구성합니다. Journey Orchestration 및 Adobe Experience Platform에 대한 제품 프로필 액세스 권한이 필요합니다. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호...).
1. **이전에 생성된 자격 증명에서 JWT(JSON Web Token)** 을 만들어 개인 키로 서명합니다. JWT는 Adobe이 ID를 확인하고 API에 대한 액세스 권한을 부여하는 데 필요한 모든 ID 및 보안 정보를 인코딩합니다. 이 단계는 이 [섹션에 자세히 설명되어 있습니다](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **POST 요청이나 개발자 콘솔 인터페이스를 통해 JWT를 액세스 토큰과** 교환합니다. 이 액세스 토큰은 API 요청의 각 헤더에서 사용해야 합니다.

안전한 서비스 간 Adobe I/O API 세션을 설정하려면 Adobe 서비스에 대한 모든 요청은 인증 헤더에 아래 정보가 포함되어야 합니다.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;조직>**:개인 조직 ID이며, 각 인스턴스에 대해 Adobe에서 하나의 조직 ID가 제공됩니다.

   * &lt;조직>:프로덕션 인스턴스
   조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새로운 통합을 만들 때 Adobe I/O로 가져올 수도 있습니다( [Adobe I/O 설명서 참조](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>**:POST 요청을 통해 JWT를 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;API_KEY>**:개인 API 키. 서비스에 대한 새 통합을 만든 후 Adobe I/O로 [!DNL Journey Orchestration] 제공됩니다.



## 내보내기 가져오기 API 설명

이 API를 사용하면 경로 버전과 모든 관련 개체(경로, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 uid로 내보낼 수 있습니다.
결과 페이로드를 사용하여 다른 환경(샌드박스 또는 인스턴스)에서 경로 버전을 가져올 수 있습니다.

| 메서드 | 경로 | 설명 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 경로 버전 내보내기로 인한 여정 버전 컨텐츠 가져오기 |
| `[GET]` | /journeyVersions/`{uid}`/export | 고객 여정 버전 내보내기 |
| `[GET]` | /journeys/`{uid}`/latest | 최신 고객 여정 버전 이용 |
| `[POST]` | /list/journeys | 여정의 메타데이터와 여정 버전 목록 |


### 수출 특성 및 가드레일

* 자격 증명은 내보내지지 않고 자리 표시자(예: INSERT_SECRET_HERE)가 삽입됩니다.
페이로드를 내보낸 후 대상 환경에서 페이로드를 가져오기 전에 새 자격 증명(대상 환경에 해당)을 수동으로 삽입해야 합니다.

* 데이터 소스에 **builtIn:true**&#x200B;매개 변수가 포함되어 있으면 &quot;INSERT_SECRET_HERE&quot;를 대체할 필요가 없습니다. 고객 여정 환경에서 자동으로 관리되는 시스템 데이터 소스입니다.

* 다음 개체는 내보내지지만 대상 환경에서는 가져올 수 없습니다.
   * **데이터 제공업체**: acsDataProvider 및 acppsDataProvider
   * **필드 그룹**:acppsFieldGroup
   * **사용자 지정 작업**:acsAction

* 내보내기 전에 여정이 유효해야 합니다.

### 가져오기 특성

* 가져오는 동안 경로 개체는 새 UUID와 새 이름으로 만들어져 대상 환경(인스턴스 또는 샌드박스)에서 고유성을 보장합니다.

* 가져오기 페이로드에 비밀 자리 표시자가 포함된 경우 오류가 발생합니다. POST 호출 전에 자격 증명 정보를 교체하여 경로를 가져와야 합니다.

## 경고 및 오류

잠재적 오류는 다음과 같습니다.

* 내보내기 **시**, 경로 버전이 유효하지 않은 경우:오류 500

* 가져오기 **시**&#x200B;페이로드가 수정 후 유효하지 않거나 페이로드에서 자격 증명이 잘 정의되지 않은 경우:오류 400

* 가져오기 단계 후에 이벤트의 XDM 스키마 ID를 변경하지 않고 대상 환경에서 경로를 게시하려고 하면 오류가 표시됩니다.

