---
product: adobe campaign
title: 내보내기 API 설명 가져오기
description: 가져오기 내보내기 API에 대해 자세히 알아보십시오.
products: journeys
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 17%

---


# Export-Import API 작업

단일 API 호출로 여정 버전 및 모든 관련 개체(여정, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 내보냅니다. 내보내기 결과 페이로드는 여정을 다른 환경(인스턴스 또는 샌드박스)으로 쉽게 가져오는 데 사용할 수 있습니다.
이 기능을 사용하면 여러 인스턴스 간에 또는 여러 테스트 환경 워크플로우에 대한 여정을 관리할 수 있습니다.


## 리소스

Journey Orchestration Export-Import API는 [여기](https://adobedocs.github.io/JourneyAPI/docs/)에서 사용할 수 있는 Swagger 파일에 설명되어 있습니다.

Journey Orchestration 인스턴스에서 이 API를 사용하려면 AdobeI/O 콘솔을 사용해야 합니다. 이 [Adobe Developer Console 시작하기](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)를 따라 시작한 다음 이 페이지의 섹션을 사용할 수 있습니다.

통합을 테스트하고 준비하려면 [여기](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)에서 Postman 컬렉션을 사용할 수 있습니다.


## 내보내기-가져오기 흐름

다음 단계에 따라 여러 환경에서 여정을 내보내고 가져오는 것이 좋습니다.

1. 시작 환경에서 여정을 만들고 매개 변수를 지정합니다. [추가 정보](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 여정 버전에 오류가 없는지 확인합니다. [추가 정보](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 여정 **/list/properties** API를 호출하여 UID 여정 및 최신 여정 버전의 UID를 검색합니다. 필요한 경우 **/여정/`{uid}`/최신**&#x200B;에 호출하여 최신 여정 버전의 UID를 찾을 수 있습니다.
1. 시작 환경 매개 변수(orgID 및 sandboxName)를 사용하여 **내보내기** API를 호출합니다.
1. 반환 페이로드를 연 다음 다음 항목을 확인합니다.
   * 내보낸 여정에 **특정 자격 증명**&#x200B;이 포함된 경우 이러한 자격 증명을 새 환경에 해당하는 자격 증명으로 바꾸어야 합니다.
   * 내보낸 여정에 **XDM 스키마**&#x200B;을(를) 가리키는 **events**&#x200B;이 포함된 경우 ID 값이 다른 경우 xdmEntity 노드에서 새 환경의 스키마 ID로 스키마 ID 참조를 수동으로 업데이트해야 합니다. 이 업데이트는 각 이벤트에 대해 수행해야 합니다. [추가 정보](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 여정에 이메일, SMS 또는 푸시 작업이 포함된 경우 대상 환경의 이름이 시작 환경의 이름과 다른 경우 템플릿 이름 또는 mobileApp 이름을 업데이트해야 할 수 있습니다.
1. 대상 환경 매개 변수(orgID 및 sandboxName)를 사용하여 **가져오기** API를 호출합니다. 가져오기 API를 원하는 만큼 호출할 수 있습니다. 가져오기 API를 호출할 때마다 여정에 포함된 각 객체의 UUID 및 이름이 생성됩니다.
1. 여정을 가져오면 Journey Orchestration 애플리케이션에 게시할 수 있습니다. 추가 정보 [여기](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 인증

### API 액세스 설정

Journey Orchestration API 액세스는 아래 단계를 통해 설정됩니다. 각 단계에 대한 자세한 설명은 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)에서 확인할 수 있습니다.

>[!CAUTION]
>
>Adobe I/O의 인증서를 관리하려면 조직에 대한 <b>시스템 관리자</b> 권한이나 Admin Console의 [개발자 계정](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)을 가지고 있어야 합니다.

1. **디지털 인증서가 있는지 확인**&#x200B;하고, 필요한 경우 만들 수 있습니다. 인증서와 함께 제공된 공개 및 비공개 키는 다음 단계에서 필요합니다.
1. **Adobe I/O에서 [!DNL Journey Orchestration] 서비스**&#x200B;에 대한 새 통합을 만들고 구성합니다. Journey Orchestration 및 Adobe Experience Platform에는 제품 프로필 액세스가 필요합니다. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호 등).

>[!CAUTION]
>
>액세스 토큰을 생성하기 위한 JWT 메서드가 더 이상 사용되지 않습니다. 모든 새 통합은 [OAuth 서버 간 인증 방법](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server)을 사용하여 만들어야 합니다. 또한 Adobe은 기존 통합을 OAuth 메서드로 마이그레이션할 것을 권장합니다.
>
>다음 중요 설명서를 참조하십시오.
>[JWT에서 OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)(으)로 애플리케이션에 대한 마이그레이션 안내서,
>[OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)을(를) 사용하는 새 응용 프로그램과 이전 응용 프로그램에 대한 구현 안내서,
>[OAuth 서버 간 자격 증명 메서드 ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)을(를) 사용할 때의 이점


서비스 간 Adobe I/O API 세션을 안전하게 구성하기 위해, Adobe 서비스에 대한 모든 요청의 인증 헤더에 아래 정보를 포함해야 합니다.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;조직>**: 개인 조직 ID이며 각 인스턴스에 대해 Adobe이 제공한 조직 ID가 하나입니다.

   * &lt;조직> : 프로덕션 인스턴스

  조직 ID 값은 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 라이선스 목록에서 검색해 Adobe I/O로 가져올 수도 있습니다([Adobe I/O 설명서](https://www.adobe.io/authentication.html) 참조).

* **&lt;ACCESS_TOKEN>**: 개인 액세스 토큰

* **&lt;API_KEY>**: 사용자의 개인 API 키입니다. [!DNL Journey Orchestration] 서비스 통합을 새로 만든 뒤에 Adobe I/O를 통해 제공됩니다.



## API 내보내기-가져오기 설명

이 API를 사용하면 UID로 식별되는 여정 버전 및 관련된 모든 개체(여정, 이벤트, 데이터 소스, 필드 그룹, 사용자 지정 작업)를 uid로 내보낼 수 있습니다.
결과 페이로드는 다른 환경(샌드박스 또는 인스턴스)에서 여정 버전을 가져오는 데 사용할 수 있습니다.

| 메서드 | 경로 | 설명 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 여정 버전 내보내기로 인한 여정 버전 컨텐츠 가져오기 |
| `[GET]` | /journeyVersions/`{uid}`/export | 여정 버전 내보내기 |
| `[GET]` | /여정/`{uid}`/최신 | 여정에 대한 최신 여정 버전 가져오기 |
| `[POST]` | /list/여정 | 여정 및 해당 여정 버전의 메타데이터 나열 |


### 내보내기 특성 및 보호 기능

* 내보내기 전에 여정이 유효해야 합니다.

* 자격 증명은 내보내지지 않고 자리 표시자(즉, INSERT_SECRET_HERE)가 응답 페이로드에 삽입됩니다.
내보내기 호출 후에 대상 환경에서 페이로드를 가져오기 전에 새 자격 증명(대상 환경에 해당함)을 수동으로 삽입해야 합니다.

* 다음 객체는 내보내지지만 대상 환경에서는 가져오지 않습니다. 이는 Journey Orchestration이 자동으로 관리하는 시스템 리소스입니다. &quot;INSERT_SECRET_HERE&quot;를 바꿀 필요가 없습니다.
   * **DataProviders**: &quot;Adobe Campaign Standard 데이터 공급자&quot;(acsDataProvider) 및 &quot;Experience Platform&quot;(acppsDataProvider)
   * **필드 그룹**(dataEntities): &quot;ProfileFieldGroup&quot;(acppsDataPack)



### 가져오기 특성

* 가져오는 동안 대상 환경(인스턴스 또는 샌드박스)에서 고유성을 보장하기 위해 새 UID와 새 이름으로 여정 개체가 생성됩니다.

* 가져오기 페이로드에 비밀 자리 표시자가 들어 있으면 오류가 발생합니다. 여정을 가져오려면 POST 호출 전에 자격 증명 정보를 바꾸어야 합니다.

## 경고 및 오류

잠재적 오류는 다음과 같습니다.

* **내보내기 시간**&#x200B;에 여정 버전이 잘못된 경우: 오류 500

* **가져오기 시간**&#x200B;에 페이로드가 수정 후 유효하지 않거나 자격 증명이 페이로드에 잘 정의되어 있지 않은 경우 오류 400

* 가져오기 단계 후 이벤트에 대한 XDM 스키마 ID가 대상 환경에서 유효하지 않은 경우 Journey Orchestration 애플리케이션에 오류가 표시됩니다. 이러한 경우 여정을 게시할 수 없습니다.