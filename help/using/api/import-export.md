---
product: adobe campaign
title: 가져오기 내보내기 API 설명
description: 가져오기 내보내기 API에 대해 자세히 알아보십시오.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---


# Export-Import API 작업

단일 API 호출로 여정 버전 및 모든 관련 개체(여정, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 내보냅니다. 내보내기 결과 페이로드를 사용하여 여정을 다른 환경(인스턴스 또는 샌드박스)으로 쉽게 가져올 수 있습니다.
이 기능을 사용하면 여러 인스턴스 또는 여러 테스트 환경 워크플로우의 여정을 관리할 수 있습니다.


## 리소스

Journey Orchestration Export-Import API는 사용 가능한 Swagger 파일 내에 설명되어 있습니다 [여기](https://adobedocs.github.io/JourneyAPI/docs/).

Journey Orchestration 인스턴스에서 이 API를 사용하려면 AdobeI/O 콘솔을 사용해야 합니다. 다음을 수행하여 시작할 수 있습니다 [Adobe 개발자 콘솔 시작하기](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 그런 다음 이 페이지의 섹션을 사용합니다.

통합을 테스트하고 준비하기 위해 Postman 컬렉션을 사용할 수 있습니다 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## 내보내기-가져오기 흐름

다음 단계에 따라 환경 간에 여정을 내보내고 가져오는 것이 좋습니다.

1. 시작 환경에서 여정을 만들고 매개 변수를 지정합니다. [추가 정보는 여기에서 확인하십시오](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 여정 버전에 오류가 없는지 확인합니다. [추가 정보는 여기에서 확인하십시오](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 호출 **/list/여정** UID 여정 및 최신 여정 버전의 UID를 검색하기 위한 API 필요한 경우 를 호출할 수 있습니다 **/여정/`{uid}`/최신** 최신 여정 버전의 UID를 찾으려면
1. 호출 **내보내기** 시작 환경 매개 변수(orgID 및 sandboxName)가 있는 API입니다.
1. 반환 페이로드를 열고 다음 항목을 확인합니다.
   * 내보낸 여정에 다음이 포함된 경우 **특정 자격 증명**&#x200B;를 채울 때는 이러한 자격 증명을 새 환경에 해당하는 자격 증명으로 바꿔야 합니다.
   * 내보낸 여정에 다음이 포함된 경우 **events** 그 점이 **XDM 스키마**&#x200B;를 지정하는 경우, ID 값이 다른 경우 xdmEntity 노드에서 새 환경의 스키마 ID로 스키마 ID 참조를 수동으로 업데이트해야 합니다. 이 업데이트는 각 이벤트에 대해 수행해야 합니다. [추가 정보는 여기에서 확인하십시오](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 여정에 이메일, sms 또는 푸시 작업이 포함된 경우, 대상 환경의 이름이 시작 환경의 이름과 다른 경우 템플릿 이름 또는 mobileApp 이름을 업데이트해야 할 수 있습니다.
1. 호출 **가져오기** target 환경 매개 변수(orgID 및 sandboxName)를 사용하는 API. 가져오기 API를 원하는 만큼 호출할 수 있습니다. 가져오기 API를 호출할 때마다 여정에 포함된 각 개체의 이름과 UUID가 생성됩니다.
1. 여정을 가져온 후에는 Journey Orchestration 애플리케이션에 게시할 수 있습니다. 추가 정보 [여기](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 인증

### API 액세스 설정

Journey Orchestration API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Adobe I/O에서 인증서를 관리하려면 <b>시스템 관리자</b> 조직 또는 [개발자 계정](https://helpx.adobe.com/kr/enterprise/using/manage-developers.html) 를 클릭하십시오.

1. **디지털 인증서가 있는지 확인**&#x200B;또는 필요한 경우 만들 수 있습니다. 인증서와 함께 제공된 공개 및 개인 키는 다음 단계에 필요합니다.
1. **에 대한 새 통합 만들기 [!DNL Journey Orchestration] 서비스** Adobe I/O 및 구성합니다. Journey Orchestration 및 Adobe Experience Platform에 대한 제품 프로필 액세스 권한이 필요합니다. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호...).
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
   조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 라이선스 목록에서 Adobe I/O으로 검색할 수도 있습니다( [Adobe I/O 설명서](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: POST 요청을 통해 JWT를 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;api_key>**: 개인 API 키 를 참조하십시오. 새 통합을 만든 후 Adobe I/O에 제공됩니다 [!DNL Journey Orchestration] 서비스.



## Export-Import API 설명

이 API를 사용하면 UID로 식별된 여정 버전과 모든 관련 개체(여정, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 해당 uid로 내보낼 수 있습니다.
결과 페이로드를 사용하여 다른 환경(샌드박스 또는 인스턴스)에서 여정 버전을 가져올 수 있습니다.

| 메서드 | 경로 | 설명 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 여정 버전 내보내기로 인한 여정 버전 콘텐츠 가져오기 |
| `[GET]` | /journeyVersions/`{uid}`/export | 여정 버전 내보내기 |
| `[GET]` | /여정/`{uid}`/최신 | 여정에 대한 최신 여정 버전 가져오기 |
| `[POST]` | /list/여정 | 여정 및 해당 여정 버전의 메타데이터 나열 |


### 내보내기 특성 및 보호 기능

* 내보내기 전에 여정이 유효해야 합니다.

* 자격 증명을 내보내지 않고 자리 표시자(즉, INSERT_SECRET_HERE)가 응답 페이로드에 삽입됩니다.
내보내기 호출 후에 대상 환경에서 페이로드를 가져오기 전에 새 자격 증명(대상 환경에 해당)을 수동으로 삽입해야 합니다.

* 다음 개체는 내보내지지만 대상 환경에서는 가져오지 않습니다. Journey Orchestration에서 자동으로 관리하는 시스템 리소스입니다. &quot;INSERT_SECRET_HERE&quot;를 바꿀 필요가 없습니다.
   * **DataProviders**: &quot;Adobe Campaign Standard 데이터 공급자&quot;(acsDataProvider) 및 &quot;Experience Platform&quot;(acppsDataProvider)
   * **필드 그룹** (dataEntities): &quot;ProfileFieldGroup&quot;(acppsDataPack)



### 가져오기 특성

* 가져오는 동안 여정 개체는 타겟 환경(인스턴스 또는 샌드박스)에서 고유성을 보장하기 위해 새 UID와 새 이름으로 만들어집니다.

* 가져오기 페이로드에 비밀 자리 표시자가 포함된 경우 오류가 발생합니다. 여정을 가져오려면 POST 호출 전에 자격 증명 정보를 바꾸어야 합니다.

## 경고 및 오류

잠재적 오류는 다음과 같습니다.

* at **내보내기 시간**, 여정 버전이 올바르지 않은 경우: 오류 500

* at **가져오기 시간**&#x200B;수정 후 페이로드가 올바르지 않거나 페이로드에 자격 증명이 잘 정의되어 있지 않은 경우: 오류 400

* 가져오기 단계 후에 이벤트에 대한 XDM 스키마 ID가 대상 환경에서 유효하지 않으면 Journey Orchestration 애플리케이션에 오류가 표시됩니다. 이러한 경우에는 여정을 게시할 수 없습니다.