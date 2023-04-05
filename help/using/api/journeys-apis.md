---
product: adobe campaign
title: 여정 API 시작
description: 여정 API에 대해 자세히 알아보기
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 2%

---

# 여정 API 시작

## 최대 가용량 및 조정 API 정보

데이터 소스 또는 작업을 구성할 때 시스템에 연결을 설정하여 여정에서 사용할 추가 정보를 검색하거나 메시지 또는 API 호출을 보냅니다.

여정 API는 초당 최대 5000개의 이벤트를 지원하지만, 일부 외부 시스템 또는 API에는 동등한 처리량이 없을 수 있습니다. 이러한 시스템이 오버로드되지 않도록 하려면 **최대 가용량** 및 **조절** 초당 전송된 이벤트 수를 제한하는 API입니다.

여정에 의해 API 호출이 수행될 때마다 API 엔진을 통과합니다. API에 설정된 제한에 도달하는 경우 최대 6시간 동안 캡핑 API를 사용하는 경우 호출이 거부되거나, 제한 API를 사용하는 경우 수신한 순서대로 가능한 한 빨리 처리됩니다.

예를 들어 외부 시스템에 대해 초당 100회 호출의 최대 가용량 또는 조정 규칙을 정의했다고 가정합니다. 시스템이 10개의 다른 여정에서 사용자 지정 작업에 의해 호출됩니다. 한 여정이 초당 200개의 호출을 받으면 사용 가능한 100개의 슬롯을 사용하고 100개의 나머지 슬롯을 삭제하거나 대기시킵니다. 최대 속도를 초과했으므로 다른 9개의 여정에 슬롯이 남아 있지 않습니다. 이러한 세부기간을 통해 외부 시스템을 오버로드 및 충돌으로부터 보호할 수 있습니다.

>[!IMPORTANT]
>
>**최대 가용량 규칙** 은 특정 엔드포인트(호출된 URL)에 대해 샌드박스 수준에서 구성되지만 해당 샌드박스의 모든 여정에 적용됩니다.
>
>**조절 규칙** 특정 종단점에 대해서만 프로덕션 샌드박스에서 구성되지만 모든 샌드박스의 모든 여정에 대해 글로벌 상태로 전환됩니다. 조직당 하나의 조절 구성만 가질 수 있습니다.

이러한 API를 사용하는 방법에 대한 자세한 내용은 다음 섹션을 참조하십시오.

* [API 최대 가용량](capping.md)
* [조절 API](throttling.md)

두 API 모두 사용 가능한 Swagger 파일에도 설명되어 있습니다 [여기](https://adobedocs.github.io/JourneyAPI/docs/).

## 데이터 소스 및 사용자 지정 작업 용량 {#capacity}

대상 **외부 데이터 소스**&#x200B;인 경우 초당 최대 호출 수는 15개로 제한됩니다. 이 제한을 초과하는 경우 사용 중인 API에 따라 추가 호출이 삭제되거나 큐에 추가됩니다. Adobe에 종단점을 포함하도록에 연락하여 비공개 외부 데이터 소스에 대한 이 제한을 늘릴 수 허용 목록에 추가하다 있지만 공개 외부 데이터 소스에 대한 옵션이 아닙니다. * [데이터 소스를 구성하는 방법 알아보기](../datasource/about-data-sources.md).

>[!NOTE]
>
>데이터 소스가 데이터 소스에 사용된 끝점과 다른 끝점이 있는 사용자 지정 인증을 사용하는 경우 Adobe에 연락하여 해당 끝점도에 포함해야 허용 목록에 추가하다 합니다.

대상 **사용자 지정 작업**&#x200B;를 채울 때는 외부 API의 용량을 평가해야 합니다. 예를 들어, Journey Optimizer이 초당 1000개의 호출을 전송하고 시스템이 초당 100개의 호출만 지원할 수 있는 경우 시스템이 포화되지 않도록 최대 가용량 또는 제한 구성을 정의해야 합니다. [작업 구성 방법 알아보기](../action/action.md)

## API 액세스 설정 {#api}

와 함께 이러한 API를 사용하려면 [!DNL Journey Orchestration] 예를 들어 AdobeI/O 콘솔을 사용해야 합니다. [!DNL Journey Orchestration] API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe I/O 설명서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Adobe I/O에서 인증서를 관리하려면 <b>시스템 관리자</b> 조직 또는 [개발자 계정](https://helpx.adobe.com/enterprise/using/manage-developers.html) 를 클릭하십시오.

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

* **&lt;organization>**: 개인 조직 ID이며, 각 인스턴스에 대해 Adobe이 하나의 조직 ID를 제공합니다. 조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 새 통합을 만들 때 라이선스 목록에서 Adobe I/O으로 검색할 수도 있습니다( <a href="https://www.adobe.io/authentication.html">Adobe I/O 설명서</a>).

* **&lt;access_token>**: POST 요청을 통해 JWT를 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;api_key>**: 개인 API 키 를 참조하십시오. 새 통합을 만든 후 Adobe I/O에 제공됩니다 [!DNL Journey Orchestration] 서비스.
