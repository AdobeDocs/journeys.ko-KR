---
product: adobe campaign
title: 여정 API 사용 시작
description: 여정 API에 대해 자세히 알아보기
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 87d5cf223d9adec27eabcb55f2e09aa6d40b23a6
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 87%

---

# 여정 API 사용 시작

## Capping 및 Throttling API 정보

데이터 소스나 작업을 구성할 때는 여정에서 사용할 추가 정보를 검색하거나 메시지 또는 API 호출을 보내기 위해 특정 시스템에 대한 연결을 설정하게 됩니다.

여정 API는 이벤트를 초당 최대 5,000개까지 지원하지만, 일부 외부 시스템이나 API의 처리량은 이 수준이 아닐 수 있습니다. 이런 시스템의 과부하를 방지하기 위해 **Capping** 및 **Throttling** API로 초당 보낼 이벤트의 수를 제한할 수 있습니다.

여정이 API를 호출할 때마다 호출은 API 엔진을 통과합니다. 이때 API에서 설정한 제한에 도달한 경우 API 엔진은 호출을 거부하거나(Capping API를 사용하는 경우), 호출을 최대 6시간까지 큐에 보관했다가 최대한 빨리 수신한 순서대로 처리합니다(Throttling API를 사용하는 경우).

예를 들어 외부 시스템에 대해 초당 100개의 호출 제한 또는 제한 규칙을 정의했다고 가정해 보겠습니다. 서로 다른 여정 10개에서 사용자 정의 작업이 이 시스템을 호출합니다. 한 여정에서 초당 200회의 호출을 수신하는 경우 이 여정은 지금 사용할 수 있는 100회의 호출 처리 슬롯을 사용하고 나머지 100회는 무시하거나 큐로 보냅니다. 최대 처리량을 초과했으므로 다른 9개의 여정에는 호출을 처리할 슬롯이 남아 있지 않습니다. 이런 단위 설정을 통해 외부 시스템을 과부하 및 충돌으로부터 보호할 수 있습니다.

>[!IMPORTANT]
>
>**한도 설정 규칙**&#x200B;은 샌드박스 수준에서 특정 엔드포인트(호출 대상 URL)에 대해 구성되지만 해당 샌드박스의 모든 여정에 적용됩니다.
>
>**스로틀링 규칙**&#x200B;은 프로덕션 샌드박스에서만 특정 엔드포인트에 대해 구성되지만 모든 샌드박스의 모든 여정에 적용됩니다. 스로틀링 구성은 한 조직에 하나씩만 가질 수 있습니다.

이 API를 사용하는 자세한 방법은 다음 섹션을 참조하십시오.

* [Capping API](capping.md)
* [Throttling API](throttling.md)

[여기](https://adobedocs.github.io/JourneyAPI/docs/)에 있는 Swagger 파일에서도 두 파일 모두에 대한 설명을 확인할 수 있습니다.

## 데이터 소스 및 사용자 정의 작업 용량 {#capacity}

**외부 데이터 소스**&#x200B;에 대한 초당 최대 호출 수는 15회로 제한됩니다. 이 제한을 넘기면 사용하는 API에 따라 초과 호출을 삭제하거나 큐에 추가합니다. 비공개 외부 데이터 소스의 경우 Adobe에 문의하여 허용 목록에 엔드포인트를 추가함으로써 이 제한을 늘릴 수 있지만, 공개 외부 데이터 소스에 대해서는 불가능합니다. * [데이터 소스를 구성하는 방법을 알아봅니다](../datasource/about-data-sources.md).

>[!NOTE]
>
>데이터 소스에서 해당 데이터 소스에 사용한 것과 다른 엔드포인트를 사용하는 사용자 정의 인증을 사용하는 경우에는 Adobe 문의를 통해 해당 엔드포인트도 허용 목록에 추가해야 합니다.

**사용자 정의 작업**&#x200B;을 구성할 때는 외부 API의 용량을 예상해야 합니다. 예를 들어 Journey Optimizer가 초당 1000개의 호출을 보내는데 시스템은 초당 100개의 호출만 지원할 수 있는 경우 시스템이 포화되지 않도록 한도 설정이나 스로틀링 구성을 정의해야 합니다. [작업을 구성하는 방법 알아보기](../action/action.md)

## API 액세스 설정 {#api}

[!DNL Journey Orchestration] 인스턴스에 이런 API를 사용하려면 Adobe I/O Console을 사용해야 합니다. [!DNL Journey Orchestration] API 액세스는 아래 단계를 통해 설정할 수 있습니다. 각 단계에 대한 자세한 설명은 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)에서 확인할 수 있습니다.

>[!CAUTION]
>
>Adobe I/O의 인증서를 관리하려면 조직에 대한 <b>시스템 관리자</b> 권한이나 Admin Console의 [개발자 계정](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)을 가지고 있어야 합니다.

1. **디지털 인증서가 있는지 확인**&#x200B;하고, 필요한 경우 만들 수 있습니다. 인증서와 함께 제공된 공개 및 비공개 키는 다음 단계에서 필요합니다.
1. **Adobe I/O에서 [!DNL Journey Orchestration] 서비스**&#x200B;에 대한 새 통합을 만들고 구성합니다. [!DNL Journey Orchestration] 및 Adobe Experience Platform에 대한 제품 프로필 액세스 권한이 필요합니다. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호 등).

>[!CAUTION]
>
>액세스 토큰을 생성하기 위한 JWT 메서드가 더 이상 사용되지 않습니다. 모든 새 통합은 [OAuth 서버 간 인증 방법](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). 또한 Adobe은 기존 통합을 OAuth 메서드로 마이그레이션할 것을 권장합니다.
>
>다음 중요 설명서를 참조하십시오.
>[JWT에서 OAuth로의 애플리케이션 마이그레이션 안내서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[OAuth를 사용하는 신규 및 기존 애플리케이션에 대한 구현 안내서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[OAuth 서버 간 자격 증명 메서드 사용의 이점](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

서비스 간 Adobe I/O API 세션을 안전하게 구성하기 위해, Adobe 서비스에 대한 모든 요청의 인증 헤더에 아래 정보를 포함해야 합니다.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: 사용자 개인의 조직 ID이며, Adobe는 한 인스턴스에 조직 ID를 하나씩 제공합니다. 조직 ID 값은 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 라이선스 목록에서 검색해 Adobe I/O로 가져올 수도 있습니다([Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 참조).

* **&lt;access_token>**: 개인 액세스 토큰

* **&lt;API_KEY>**: 사용자의 개인 API 키입니다. [!DNL Journey Orchestration] 서비스 통합을 새로 만든 뒤에 Adobe I/O를 통해 제공됩니다.
