---
product: adobe campaign
title: 릴리스 정보
description: 릴리스 정보에 대해 알아보기
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 77b7979b2023e58298298c88240cb2855b55d56b
workflow-type: tm+mt
source-wordcount: '4232'
ht-degree: 99%

---

# 릴리스 정보 {#release-notes}

이 페이지에는 Journey Orchestration의 새로운 기능과 개선 사항이 모두 포함되어 있습니다. Experience Platform의 기능을 확인하려면 다음 [릴리스 정보](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html)를 참조하십시오.

>[!NOTE]
>
>2022년과 2023년에 릴리스된 기능의 경우 링크는 Adobe Journey Optimizer 설명서로 연결됩니다.

## 2023년 8월 릴리스 {#aug-rn-2023}

### 개선 사항 {#aug-2023-improvements}

* 이제 사용자 정의 작업에 API 호출 응답을 활용하고, 이 응답을 기반으로 여정을 오케스트레이션할 수 있습니다. 이 기능은 현재 Private Beta로 사용할 수 있습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html)를 참조하십시오.

## 2023년 4월 릴리스 {#apr-rn-2023}

### 개선 사항 {#april-2023-improvements}

* 작업과 데이터 소스, 이벤트 및 여정에 표시되는 구성 창의 레이아웃을 개선했습니다.
* 이제 사용자 정의 작업에서 정적 또는 동적 쿼리 매개 변수를 정의할 수 있습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=ko#url-configuration)를 참조하십시오.
* 여정을 통해 제공하는 경험의 증가량을 관리할 수 있는 새로운 가드레일:
   * 여정의 성능과 가독성, QA, 문제 해결을 위해 노드 수를 50개 이하로 제한하는 것이 좋습니다. 활동 수는 여정 캔버스의 왼쪽 위 섹션에 표시됩니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ko#journeys-guardrails-journeys)를 참조하십시오
   * 여정을 개발하고 시작한 뒤 한 번에 100개의 실시간 여정을 실행하는 마일스톤에 도달하면 알림을 보내 드리겠습니다. 기획에 한 번에 100개가 넘는 여정이 필요한 경우 알림을 확인한 뒤 지원 티켓을 개설해 주시면 Adobe가 도와 드리겠습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ko#journeys-guardrails-journeys)를 참조하십시오

## 2023년 3월 릴리스 {#mar-2023}

### 개선 사항 {#mar-2023-improvements}

* 새로운 **Throttling API**&#x200B;를 통해 초당 전송 이벤트 수에 제한을 설정하여 외부 시스템 또는 API에서 급격한 트래픽 스파이크가 발생하는 것을 방지할 수 있습니다. 설정한 제한에 도달하면 그 뒤의 API 호출은 수신되는 순서로 모두 큐에 올려 가능한 한 빨리 처리합니다. 이 기능은 모든 샌드박스를 통틀어 하나의 스로틀링 구성만 지원합니다. [자세히 알아보기](../api/throttling.md)
* 여정 캔버스가 보다 간단하고 개선된 사용자 경험을 제공하도록 향상되었습니다. 캔버스에서 각 경로의 끝에 있던 빈 자리 표시자를 제거했습니다. 이제 활동을 추가하려면 간단히 경로 끝에 끌어다 놓기만 하면 됩니다.
* 이제 여정 캔버스의 **종료** 태그가 자동으로 이전 활동의 이름으로 설정되지 않습니다. 필요한 경우 사용자가 수동으로 사용자 정의 레이블을 추가할 수 있습니다.
* 여정 속성의 기본 시간 제한 및 오류 지속 시간을 5초에서 30초로 변경했습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html?lang=ko#timeout)를 참조하십시오.
* 테스트 모드에 인터페이스를 통해 보낸 이벤트만 수신하도록 하는 가드레일을 추가했습니다. 외부 도구를 통해 보낸 이벤트는 고려하지 않습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html?lang=ko-KR)를 참조하십시오.

## 2023년 2월 릴리스 {#feb-2023}

### 개선 사항 {#feb-2023-improvements}

* 여정 속성에 **재입장 대기 시간** 필드가 추가되었습니다. 이 필드에서는 단일 여정(이벤트 또는 세그먼트 검증으로 시작)에서 프로필이 다시 여정에 들어오려면 기다려야 하는 시간을 정의할 수 있습니다. 이를 통해 동일한 이벤트에 대해 여정을 여러 번 트리거하는 오류를 방지할 수 있습니다. 이 필드는 기본적으로 5분으로 설정되어 있습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ko#entrance)를 참조하십시오.
* **여정 시작 및 종료 일자**&#x200B;를 개선했습니다. 이제 시작 일자를 지정하지 않은 경우 게시할 때 자동으로 추가됩니다. 이렇게 하면 해당 일자가 되었을 때 프로필이 자동으로 종료됩니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ko#dates)를 참조하십시오.

## 2023년 1월 릴리스 {#jan-2023-release}

### 개선 사항 {#jan-2023-improvements}

* 이제 여정에 **세그먼트 검증**&#x200B;을 추가할 때 네임스페이스를 기본적으로 미리 채웁니다. 마지막으로 사용한 네임스페이스가 자동으로 미리 입력됩니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html?lang=ko#about-segment-qualification)를 참조하십시오.
* 여정 캔버스에서 도구 모음의 새 버튼을 통해 여정의 스크린샷을 다운로드할 수 있습니다.

## 2022년 9월 릴리스{#sept-2022-release}

### 새로운 기능{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>데이터 거버넌스 및 개인 정보 보호</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Orchestration이 이제 DULE(데이터 사용 라벨링 및 적용) 거버넌스 프레임워크를 통해 Adobe Experience Platform 거버넌스 정책을 활용할 수 있습니다. 이 방법으로 사용자 정의 작업 시 중요한 정보가 있는 필드를 서드파티 시스템으로 내보내는 것을 방지할 수 있습니다. 시스템이 사용자 지정 작업 매개 변수에서 제한된 필드를 식별하면 여정을 게시하지 못하게 하는 오류가 표시됩니다.</p>
<p>DULE(데이터 사용 레이블 및 적용) 사용은 현재 선택한 고객으로 제한되며, 향후 릴리스의 모든 환경에 배포될 예정입니다.</p>
<p>자세한 내용은 Journey Optimizer <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html?lang=ko">설명서</a>를 참조하십시오.
</td>
</tr>
</tbody>
</table>

### 개선 사항{#sept-2022-improvements}

* 동일한 이벤트에 대해 여정이 여러 번 잘못 트리거되는 것을 방지하기 위해 단일 여정(이벤트 또는 세그먼트 자격 조건 시작)에 새로운 보호 기능이 추가되었습니다. 프로필 재입장은 이제 기본 5분 동안 일시적으로 차단됩니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=kol#events-g)를 참조하십시오.

### 기타 변경 사항{#sept-2022-other}

* 성능을 향상시키기 위해 [세그먼트 자격 조건] 활동으로 시작하는 여정에서는 더 이상 [경험 이벤트] 필드 그룹을 사용할 수 없습니다. 이 변경 사항은 새로운 여정에만 적용됩니다. 기존 동작은 현재 동작을 유지합니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ko#expression-editor)를 참조하십시오.

### 개선 사항

* **여정 종료** - 여정 캔버스에서 **종료** 활동이 팔레트에서 제거되었습니다. 이제 종료 태그가 각 경로 끝에 기본적으로 추가되므로 제거할 수 없습니다. 이 개선 사항을 통해 고객이 여정에서 드롭된 위치를 여정 전문가의 작업 없이 더 잘 보고할 수 있습니다. Journey Optimizer [설명서](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html?lang=ko)를 참조하십시오.

* 이제 여정 속성에서 **프로필 시간대** 옵션이 기본적으로 선택되지 않습니다. [자세히 보기](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html?lang=ko#timezone-from-profiles).

## 2022년 5월 릴리스 {#may-2022-release}

### 개선 사항

* **표현식 편집기** - 목록의 항목 수를 제한할 수 있도록 [limit](../functions/functionlimit.md) 함수가 추가되었습니다. 이제 [sort](../functions/functionsort.md) 함수를 사용하여 목록 개체를 정렬할 수 있습니다. 또한 [disctinct](../functions/functiondistinct.md) 및 [distinctWithNull](../functions/functiondistinctwithnull.md) 함수에 listObject에 대한 지원도 추가되었습니다.

## 2022년 3월 릴리스 {#feb-2022-release}

### 개선 사항

* 통합 프로필 스키마에 불필요한 필드가 없도록 하기 위해, 여정 단계 이벤트 스키마는 이제 프로필에서 기본적으로 사용하도록 설정되지 않습니다. 필요한 경우 활성화할 수 있습니다. [자세히 알아보기](../building-journeys/sharing-overview.md)
* 내보내기 작업 관련 새로운 단계 이벤트는 이제 Journey Optimizer에서 Adobe Experience Platform으로 보내집니다. 쿼리 예시를 설명서에 추가했습니다. [자세히 알아보기](../building-journeys/query-examples.md)

## 2022년 2월 릴리스 {#february-2022-release}

### 개선 사항

* 성능을 최적화하고 오래된 리소스의 사용을 방지하기 위해 1주일 동안 트리거되지 않은 테스트 모드의 모든 여정이 이제 초안 상태로 다시 전환니다. [자세히 보기](../building-journeys/testing-the-journey.md#important_notes)

## 2022년 1월 릴리스 {#january-2022-release}

### 개선 사항

* 이제 Journey Orchestration 단계 이벤트를 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ko)의 다른 데이터 세트에 연결할 수 있습니다. 기본 제공 여정 단계 이벤트 스키마의 **profileID** 필드가 이제 ID 필드로 정의됩니다. [자세히 알아보기](../building-journeys/sharing-overview.md#integration-cja)
* Adobe Campaign Standard 작업에 대한 최대 가용량 규칙이 5분당 호출 4,000건으로 변경되었습니다. [자세히 보기](../action/working-with-adobe-campaign.md)

## 2021년 10월 릴리스 {#october-2021-release}

### 개선 사항

* **표현식 편집기** - 이제 고급 사용자는 여정 지도 작업에 함수를 사용할 수 있습니다. [자세히 보기](../expression/field-references.md)
* **접근성** - 접근성을 개선했습니다. 이제 Journey Orchestration은 접근성 측면에서 완전히 규정을 준수합니다.
* **컬렉션** - 이제 하위 개체가 포함된 개체 배열이 지원됩니다. [자세히 보기](../usecase/collections.md)
* **모니터링** - 실시간 여정 및 테스트 모드에 대한 단계 이벤트를 개선했습니다. 프로필 내보내기 작업과 관련하여 [새 필드](../building-journeys/sharing-field-list.md#serviceevents)를 추가했습니다. 더 나은 사용자 경험을 위해 이제 단계 이벤트 필드가 Journey Orchestration의 여정 단계 이벤트 스키마에서 다른 카테고리로 구성됩니다. 이전 단계 이벤트 필드는 [stepEvents](../building-journeys/sharing-legacy-fields.md) 카테고리에서 계속 사용할 수 있습니다.

## 2021년 9월 릴리스 {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>사용자 지정 작업으로 데이터 목록을 동적으로 보내기</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 사용자 지정 작업 매개 변수에 컬렉션이나 데이터 목록을 전달할 수 있으며 그 내용은 실시간으로, 동적으로 채워집니다. 지원되는 컬렉션은 단순 컬렉션과 개체 컬렉션, 두 가지입니다. 이전에 만든 사용자 지정 작업은 계속 작동합니다. </p>
<p>컬렉션에 대한 자세한 내용은 <a href="../usecase/collections.md">자세한 설명서</a>를 참조하세요. </p>
<p>고급 표현식 편집기에서 사용할 수 있는 함수 목록에 필터링 및 교차 함수가 추가되었습니다. 이 함수를 통해 컬렉션을 더욱 다양하게 필터링 및 비교할 수 있습니다.</p>
<p><a href="../functions/functionfilter.md">필터링</a> 및 <a href="../functions/functionintersect.md">교차</a> 함수에 대한 설명서를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

### 개선 사항

* 단계 이벤트를 프로비전하는 동안 시스템에서 생성한 스키마 및 데이터 세트가 이제 읽기 전용 모드로 변경됩니다. 이를 통해 중요한 스키마를 실수로 수정하는 것을 방지할 수 있습니다. [자세히 알아보기](../building-journeys/sharing-overview.md)
* **대기** 활동에 레이블을 지정하면 캔버스에 명확하게 표시됩니다. 이 레이블은 보고 및 테스트 모드 로그에서 수행할 작업을 정확하게 확인하는 데에도 사용됩니다. [자세히 알아보기](../building-journeys/using-the-journey-designer.md)
* 검색 사용 시 **이벤트** 및 **작업** 카테고리로 요소를 필터링하여 이벤트 및 작업을 보다 신속하게 찾을 수 있습니다. 오케스트레이션 활동은 더 이상 필터링되지 않습니다. [자세히 알아보기](../building-journeys/using-the-journey-designer.md)
* 이제 규칙 기반으로 이벤트 ID 조건을 정의할 때 문자열 유형 필드에 &quot;포함&quot; 연산자를 사용할 수 있습니다. [자세히 알아보기](../event/about-creating.md)

## 2021년 8월 릴리스 {#august-2021-release}

### 개선 사항

**여정**

* **동적 헤더** - 이제 HTTP 헤더 매개 변수에서 동적 데이터를 전달할 수 있습니다. 이러한 매개 변수는 여정 작업 HTTP 호출(예: 타임스탬프 또는 추적 ID)을 수신하는 통합 시스템에서 사용할 수 있습니다. [자세히 보기](../action/url-configuration.md)
* **동적 URL 경로** - 이제 사용자 지정 작업에 대해 동적 URL 경로를 설정할 수 있습니다. [자세히 보기](../action/url-configuration.md)

## 2021년 7월 릴리스 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>스키마 관계 활용</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform을 사용하면 한 데이터 세트를 다른 데이터 세트에 대한 조회 테이블로 사용하기 위해 스키마 간의 관계를 정의할 수 있습니다. 이제 Journey Orchestration은 연결된 스키마에서 가져온 데이터를 활용할 수 있습니다.</p>
<p>이러한 필드는 단일 이벤트 구성, 여정 조건 및 사용자 지정 작업 개인화에서 사용할 수 있습니다.
<p>자세한 내용은 <a href="../event/experience-event-schema.md#leverage_schema_relationships">자세한 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

### 개선 사항

* **캐시 기간** 필드가 데이터 소스 구성 창에서 제거되었습니다. [자세히 보기](../datasource/about-data-sources.md)

## 2021년 6월 릴리스 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic 통합</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 Adobe Campaign Classic 통합과의 통합을 일반적으로 사용할 수 있습니다(GA). Adobe Campaign v7 또는 v8 트랜잭션 메시지 기능을 사용하여 이메일, 푸시 알림, SMS를 전송할 수 있습니다.</p>
<p>Journey Orchestration 인스턴스와 Campaign 인스턴스 간의 연결은 프로비저닝 시 Adobe에 의해 설정됩니다.</p>
<p>자세한 내용은 <a href="../action/acc-action.md">자세한 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

### 개선 사항

* 이제 외부 데이터 소스의 경우 초당 최대 15회 호출할 수 있는 가용량 규칙이 자동으로 정의됩니다. [자세히 보기](../about/external-systems.md#capping)
* 이제 단순 및 고급 표현식 편집기에서 XDM 날짜 형식을 지원합니다.
* 여정 목록 화면에 새로운 필터를 추가했습니다. 이제 **[!UICONTROL Unitary event]** 또는 **[!UICONTROL Segment qualification]** 여정 유형별로 필터링할 수 있습니다. [자세히 보기](../about/user-interface.md#section_lgm_hpz_pgb)
* 이제 실시간 여정의 여정 속성 화면에 게시 날짜와 여정을 게시한 사용자의 이름이 표시됩니다. 이 정보는 여정의 기술 세부 사항을 복사할 때도 사용할 수 있습니다. [자세히 보기](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## 2021년 4월 릴리스 {#april-2021-release}

### 개선 사항

* 이제 테스트 모드의 **이벤트 구성** 화면에서 열거형을 기대하는 필드에 대한 드롭다운이 표시됩니다. 사용 가능한 값 중 하나를 선택하면 됩니다. 이렇게 하면 잘못된 값이 정의된 경우 이벤트를 트리거할 때 오류가 발생하지 않습니다. [자세히 보기](../building-journeys/testing-the-journey.md#firing_events)

## 2021년 3월 릴리스 {#march-2021-release}

### 개선 사항

* 여정에 새 상태가 추가되었습니다. 여정이 종료되거나 수동으로 종료되면 해당 상태는 닫힌 날짜로부터 30일 후에 **닫힘**&#x200B;에서 **완료됨**&#x200B;으로 변경됩니다. 이렇게 하면 비활성 상태의 여정을 보다 쉽게 식별할 수 있을 뿐만 아니라 아직 여정에 참여 중인 모든 개인이 여정을 완료할 시간이 있는지 확인할 수 있습니다. [자세히 보기](../building-journeys/journey.md#ending_a_journey)
* 초안 여정의 활동 오른쪽 창에서 이제 읽기 전용 필드가 기본적으로 숨겨집니다. 이 인터페이스 간소화는 활동을 보다 쉽게 구성하는 데 도움이 됩니다. 이를 표시하려면 활동 구성 창의 왼쪽 상단 모서리에 있는 **읽기 전용 필드 표시** 아이콘을 클릭하십시오. [자세히 보기](../building-journeys/using-the-journey-designer.md#configuration_pane)
* 사용자 경험을 개선하기 위해 테스트 모드의 **이벤트 구성** 화면에서 테스트 프로필의 ID를 정의하는 데 사용되는 **키** 필드의 이름이 **프로필 식별자**&#x200B;로 변경되었습니다. [자세히 보기](../building-journeys/testing-the-journey.md).
* 반응 이벤트의 경우, 이제 시간 제한 기간을 40초~30일 사이로만 설정할 수 있습니다. 반응 이벤트를 사용하는 여정을 테스트할 때 테스트 모드 **[!UICONTROL Wait time]**&#x200B;의 기본값과 최소값은 이제 40초입니다. [자세히 보기](../building-journeys/reaction-events.md).

## 2021년 2월 릴리스 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>프로필 활동 업데이트</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이 새 작업 활동을 사용하면 이벤트, 데이터 소스 또는 특정 값을 사용하여 도출하는 데이터로 기존 Adobe Experience Platform 프로필을 업데이트할 수 있습니다.</p>
<p>자세한 내용은 <a href="../building-journeys/update-profiles.md">자세한 설명서</a>를 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

### 기타 개선 사항

* 이제 이벤트를 구성할 때 XDM 유효성 검사에 필수인 필드만 기본적으로 미리 선택됩니다. 이러한 필드는 선택 취소할 수 없습니다.
* 여정 팔레트에서 새 필터가 추가되었습니다. 기본 이벤트 및 작업 외에 가장 최근에 사용된 5건의 이벤트와 작업만 표시할 수 있습니다. 이는 각 사용자에게만 해당됩니다. 기본적으로 모든 항목이 표시됩니다. [자세히 보기](../building-journeys/using-the-journey-designer.md#palette)
* 새 여정을 시작할 때 첫 번째 단계가 숨겨지므로 캔버스에 놓을 수 없는 요소가 이제 숨겨집니다. 이는 모든 작업, 조건 활동, 대기 및 반응과 관련되어 있습니다.
* 고급 표현식 편집기의 왼쪽 부분에서 함수가 이제 목록 끝에 있는 **함수** 섹션 아래에 다시 그룹화되었습니다.

## 2021년 1월 릴리스 {#january-2021-release}

이벤트 구성에서 스키마를 선택할 경우, Journey Orchestration에서 이벤트를 제대로 수신하기 위해 반드시 필요한 필드만 선택됩니다. [자세히 보기](../event/defining-the-payload-fields.md)

이제 단순 표현식 편집기에서 여정 속성 특성을 사용할 수 있습니다. [자세히 보기](../expression/journey-properties.md)

두 개의 새 여정 속성 특성(sandboxName 및 organizationId)이 추가되었습니다. [자세히 보기](../expression/journey-properties.md)

Adobe Campaign Standard SLA에 맞추기 위해 이제 Adobe Campaign Standard 통합이 설정되는 즉시 Adobe Campaign Standard 작업에 대해 초당 13개의 호출 제한 규칙이 자동으로 정의됩니다. [자세히 보기](../action/working-with-adobe-campaign.md)

이제 이벤트 시간 제한 기간이 시간 제한 경로에 더 명확하게 지정됩니다. [자세히 보기](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

고급 표현식 편집기에서 사용할 수 있는 함수 목록에 [getListItem](../functions/functiongetlistitem.md) 및 [split](../functions/functionsplit.md) 함수가 추가되었습니다. 이에 따라 문자열 계산 사용 사례에서 더 많은 가능성을 사용할 수 있습니다.

## 2020년 11월 릴리스 {#november-release}

<table>
<thead>
<tr>
<th><strong>여정 간 이동</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>새 작업 활동을 사용하면 한 여정에서 다른 여정으로 개인 사용자를 푸시할 수 있습니다. <strong>Jump</strong> 활동을 통해 다음을 수행할 수 있습니다.
</p>
<ul>
<li>여러 개로 분할하여 매우 복잡한 여정의 디자인을 간소화 </li>
<li>공통 및 재사용 가능한 여정 패턴을 기반으로 여정 구축</li>
</ul>
<p>자세한 내용은 <a href="../building-journeys/jump.md">상세 설명서</a> 및 <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=ko-KR">튜토리얼 비디오</a>를 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>표현식 편집기에서 여정 속성 사용</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>고급 표현식 편집기에서 필드 및 함수 목록에 새 카테고리를 추가했습니다. 여정 ID 또는 발생한 특정 오류와 같은 라이브 여정 시스템에서 검색한 정보입니다. 여정을 구축하면 가능성이 높아집니다. 예를 들어 조건이나 작업에서 오류가 발생한 경우 서드파티 시스템에 경고할 수 있습니다.
</p>
<p>자세한 내용은 <a href="../expression/journey-properties.md">세부 설명서</a>를 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>규칙 기반 이벤트  (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 eventID를 사용하지 않고 이벤트를 보다 쉽게 설정하는 새로운 방법을 사용할 수 있습니다. 규칙 기반 이벤트는 조건에 따라 이벤트를 트리거해야 하는지 여부를 평가합니다. "시스템 생성"이라는 기존 방법을 계속 사용할 수 있습니다. 알파 프로그램을 통해 제한된 고객 집합에서 테스트한 이 기능은 이제 모든 고객에게 베타 버전으로 제공됩니다.
</p>
</td>
</tr>
</tbody>
</table>

### 기타 개선 사항

여정의 새 버전을 만들 때 제한 사항을 추가했습니다. 이러한 제한 사항은 여정에서 너무 많은 변경 사항을 방지하여 버전 간에 일관성을 유지합니다. [자세히 보기](../about/limitations.md#journey-versions-limitations)

Campaign Standard 메시지 활동을 포함하는 여정에서 더 이상 **세그먼트 자격** 활동을 사용할 수 없습니다. 이러한 제한은 Adobe Campaign Standard 인스턴스의 무결성을 보호합니다. 실제로, 세그먼트 자격 사용은 Campaign Standard 트랜잭션 메시지를 오버로드하게 하는 메시지를 매일 가장 많이 보낼 수 있습니다. [자세히 보기](../about/limitations.md#segment-qualification)

## 2020년 10월 릴리스 {#october-release}

<table>
<thead>
<tr>
<th><strong>이벤트 시간 제한</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 여정이 특정 시간 동안에만 이벤트를 수신하도록 하기 위해 이벤트에 대한 시간 제한을 구성할 수 있습니다. 이를 위해 더 이상 이벤트 여정을 동시에 대기 활동을 추가할 필요가 없습니다.
</p>
<p>자세한 내용은 <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">자세한 설명서</a>를 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

### 기타 개선 사항

* 새 여정 버전을 게시하면 이전 버전이 자동으로 종료되고 닫힌 상태로 전환됩니다. [자세히 보기](../building-journeys/journey-versions.md)

## 2020년 9월 릴리스 {#september-release}

### GA 업데이트{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>조건 활동 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 여정에 조건을 추가할 때 레이블을 정의할 수 있습니다. 여정에서 여러 조건을 사용하는 경우 해당 조건을 보다 쉽게 식별할 수 있습니다.
</p>
<p>자세한 내용은 <a href="../building-journeys/condition-activity.md#about_condition">세부 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

### 알파 업데이트{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>세그먼트 활동 읽기 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>세그먼트 읽기</strong> 활동에는 다음과 같은 사항이 개선되었습니다.
</p>
<ul>
<li><p>이제 세그먼트 기반 여정이 캔버스 위에 표시되어 여정의 예약 유형을 미리 알려줍니다. 이 미리 알림을 클릭하여 예약 구성 메뉴에 액세스할 수 있습니다.</p>
</li>
<li><p>세그먼트 내보내기 진행 상태를 표시하기 위해 테스트 모드 로그의 세부 기간을 개선하였습니다.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## 2020년 8월 릴리스 {#august-release}

### GA 업데이트{#august-ga-update}

이제 세그먼트 자격 이벤트의 페이로드에는 동작(시작, 종료), 자격 타임스탬프 및 세그먼트 ID와 같은 컨텍스트 정보가 포함되어 있으며 조건 및 작업에 사용할 수 있습니다. [자세히 보기](../building-journeys/segment-qualification-events.md)

### 알파 업데이트{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>세그먼트 트리거 활동</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>세그먼트 트리거 활동에는 다음과 같은 사항이 개선되었습니다.
</p>
<ul>
<li><p>활동의 이름이 "세그먼트 읽기"로 변경되었습니다. </p>
</li>
<li><p>여정 스케줄러 구성이 활동의 속성에서 제거되었습니다. 이제 세그먼트 읽기 활동이 캔버스에 드롭된 경우 표시되는 전용 섹션의 여정의 속성에서 직접 액세스할 수 있습니다. </p>
</li>
<li><p>이제 단일 프로필에서 여정을 테스트하고 시각적인 흐름을 사용하여 여정의 진행 상황을 추적할 수 있습니다.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>규칙 기반 이벤트</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>규칙 기반 이벤트에는 다음과 같은 사항이 개선되었습니다.
</p>
<ul>
<li><p>이제 모든 Adobe Analytics 행동 이벤트 데이터를 활용하여 이미 플랫폼에 스트리밍 및 캡처하고 있으므로 고객을 위한 고객 여정을 트리거하고 경험을 자동화할 수 있습니다. <a href="../event/about-analytics.md">자세히 보기</a></p>
</li>
<li><p>이제 테스트 모드에서 규칙 기반 이벤트를 트리거할 때 이벤트 ID 조건을 직접 볼 수 있습니다. 또한 규칙 평가의 일부인 각 필드 옆에 도구 설명이 추가되었습니다. <a href="../building-journeys/testing-the-journey.md#test-rule-based">자세히 보기</a></p>
</li>
<li><p>향상된 경험을 위해 규칙 기반 이벤트 정의 화면이 재구성되었습니다. <a href="../event/about-creating.md">자세히 보기</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## 알파 릴리스 - 2020년 7월 {#alpha-release---july-2020}

알파 프로그램은 제한된 고객 세트에서 현재 테스트하는 기능을 제공합니다. 따라서 수신한 피드백을 바탕으로 제품을 개선할 수 있습니다. 모든 Journey Orchestration 고객이 이러한 기능을 사용할 수는 없습니다.

<table>
<thead>
<tr>
<th><strong>향상된 사용자 인터페이스</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform과 일관된 인터페이스를 제공하기 위해 Journey Orchestration 메뉴 내의 탐색 기능이 다음과 같이 향상되었습니다.
</p>
<ul>
<li><p>메뉴가 인터페이스 맨 위에서 왼쪽으로 이동되었습니다. </p>
</li>
<li><p>관리 기능을 하나의 대시보드로 그룹화하였습니다.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>세그먼트 트리거 활동</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>세그먼트 트리거 활동을 사용하면 Adobe Experience Platform 세그먼트에 속하는 모든 개인이 여정을 시작할 수 있습니다. 여정의 시작은 한 번 또는 정기적으로 실행될 수 있습니다. 
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>규칙 기반 이벤트</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>경험 이벤트를 설정하는 방법을 간소화했습니다. eventID를 사용할 필요가 없는 새 메서드가 도입되었습니다. 이제 Journey Orchestration에서 이벤트를 설정할 때 규칙 기반 이벤트를 정의할 수 있습니다. <a href="../event/about-events.md">자세히 보기</a>
</p>
</td>
</tr>
</tbody>
</table>


## 2분기 릴리스 - 2020년 6월 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform 통합 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>다음과 같은 Adobe Experience Platform 통합 개선이 이루어졌습니다.</p>
<ul>
<li><p>새로운 활동을 통해 Adobe Experience Platform 세그먼트 출입구에서 수신 대기함으로써 사용자가 여정에 들어오거나 앞으로 이동하도록 할 수 있습니다. <a href="../building-journeys/segment-qualification-events.md">자세히 보기</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>이제 새로운 <strong>세그먼트</strong> 탭 덕분에 Journey Orchestration 인터페이스를 벗어나지 않고도 Adobe Experience Platform 세그먼트를 만들고 편집할 수 있습니다. <a href="../segment/about-segments.md">자세히 보기</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>단순 표현식 편집기에서 이제 Adobe Experience Platform 세그먼트가 탐색 트리에 직접 나열되므로 "이 사람이 세그먼트 A에 속합니까?"와 같은 조건을 쉽게 설정할 수 있습니다. <a href="../segment/using-a-segment.md">자세히 보기</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>이제 Journey Orchestration이 여정 중에 실행된 단계를 Adobe Data Platform에 자동으로 전달합니다. 여기에는 발생한 잠재적 오류도 포함됩니다. 이 정보는 특정 여정 또는 모든 여정에 대해 여정 단계 이벤트에서 쿼리를 실행함으로써 보고 및 문제 해결을 수행하는 데 사용될 수 있습니다. <a href="../building-journeys/sharing-overview.md">자세히 보기</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>이제 Journey Orchestration을 프로덕션 및 프로덕션이 아닌 Adobe Experience Platform 샌드박스에 연결할 수 있습니다. 샌드박스는 베타 기능입니다. <a href="../about/access-management.md#sandboxes">자세히 보기</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>여정 디자이너 및 테스트 모드 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>여정 디자이너 및 테스트 모드가 다음과 같이 개선되었습니다.</p>
<ul>
<li><p>이제 1 또는 N 여정 활동을 선택하면서 붙여넣기 활동을 한 여정에서 다른 여정로 복사할 수 있습니다. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">자세히 보기</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>이제는 테스트 프로필이 여정에 들어가도록 만드는 이벤트를 시작한 후에 색상으로 표시되는 시각적 플로우를 통해 여정 내 진행 상황을 확인할 수 있습니다. 여정에서 오류가 발생하는 경우 오류의 세부 정보도 표시됩니다. <a href="../building-journeys/testing-the-journey.md#firing_events">자세히 보기</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li><strong>Finished</strong> 여정 상태가 해당 상태의 의미를 더 잘 반영하도록 <strong>Closed (no entrance)</strong>로 이름이 바뀌었습니다.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**기타 개선 사항**

서드파티 시스템에 너무 많은 API 호출을 보내지 않도록 &quot;최대 가용량&quot; 규칙을 설정하는 새로운 공개 API를 채택하고 있습니다. 최대 가용량 규칙을 사용하면 API 엔드포인트에 대한 밀리초당 최대 호출 수를 정의할 수 있습니다. [자세히 보기](../api/capping.md)

이제 액세스 제어를 통해 사용자 액세스를 더 세부적으로 관리할 수 있습니다. 발효 날짜: 2020년 6월 30일. [자세히 보기](../about/access-management.md#create-product-profile)

이제 APAC(호주 데이터 센터)에서 Journey Orchestration을 사용할 수 있습니다. 발효 날짜: 2020년 6월 30일

Journey Orchestration 인터페이스를 일본어로 사용할 수 있습니다.

## 1분기 릴리스 - 2020년 3월 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>향상된 테스트 모드</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>테스트 모드가 다음과 같이 향상되었습니다.</p>
<ul>
<li>이제는 여정 하나에서 여러 이벤트를 사용할 때 테스트 모드의 <strong>이벤트 구성</strong> 화면 내 드롭다운 목록에서 각 이벤트를 개별적으로 트리거할 수 있습니다. <a href="../building-journeys/testing-the-journey.md#firing_events">자세히 보기</a></p></li>
<li><p>이제는 여정에서 <strong>대기</strong> 활동을 하나 이상 사용할 때 테스트 모드에서 이러한 각 활동을 진행할 시간을 정의할 수 있습니다. 기본 시간은 10초입니다. 왼쪽 아래에서 <strong>테스트의 대기 시간</strong> 매개 변수를 사용하여 이 시간을 변경할 수 있습니다. <a href="../building-journeys/testing-the-journey.md">자세히 보기</a></p><img src="../assets/rn-test.png"/>
</li>
<li>이제는 서드파티 시스템(데이터 소스 또는 작업)을 호출할 때 오류가 발생하면 <strong>테스트 로그</strong>에 오류 코드와 오류 응답이 표시됩니다. <a href="../building-journeys/testing-the-journey.md#viewing_logs">자세히 보기</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>중앙 집중식 시간대 관리</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>이제는 여정 속성 패널에서 중앙 집중식으로 시간대를 관리할 수 있습니다. 중앙 집중식 관리를 위해 여정 속성에 매개 변수 두 개가 추가되었습니다.</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li><strong>시간대</strong> 드롭다운 목록에서 특정 시간대를 선택할 수 있습니다. 기본적으로는 브라우저의 시간대가 사용됩니다. </li>
<li><strong>프로필 시간대</strong> 확인란을 선택하면 여정을 입력하는 사용자의 Adobe Experience Platform 프로필 시간대(사용 가능한 경우)를 사용할 수 있습니다. 이 확인란을 선택하지 않으면 드롭다운 목록에서 정의한 시간대가 사용됩니다. 이 기능은 네임스페이스가 없는 이벤트를 사용하는 여정은 호환되지 않습니다.</li>
</ul>
<p>자세한 내용은 <a href="../building-journeys/changing-properties.md#timezone">속성 변경</a> 및 <a href="../building-journeys/timezone-management.md">시간대 관리</a> 섹션을 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>향상된 여정 디자이너</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>여정 디자이너 왼쪽의 여정 <strong>팔레트</strong>가 다음과 같이 향상되었습니다.</p>
<ul>
<li><strong>검색</strong> 창 옆의 새 아이콘을 클릭하면 팔레트에서 사용할 수 없는 요소(예: 여정에 사용되는 것과 다른 네임스페이스를 사용하는 이벤트)를 숨기거나 표시할 수 있습니다. 기본적으로 사용할 수 없는 항목은 숨겨집니다.</li>
<li>이제는 <strong>검색</strong> 필드를 사용할 때 각 캔버스 활동 범주의 결과 수가 표시됩니다.</li>
<li>활동 범주 간의 탐색 방식이 개선되었습니다.</li>
</ul>
<p>이제는 여정 디자이너에서 여정의 최신 버전에 액세스하고 있는지를 확인할 수 있습니다. 이 정보는 버전 번호 옆에 표시됩니다.</p>
<p>이제는 여정 <strong>캔버스</strong>에서 두 활동의 연결이 끊기면 경고 메시지가 표시됩니다.</p>
<img src="../assets/rn-canvas.png"/>
<p>자세한 내용은 <a href="../building-journeys/using-the-journey-designer.md">세부 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>상황별 도움말</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 여정, 이벤트, 작업, 데이터 소스 등의 다양한 Journey Orchestration 목록 화면에서 상황별 도움말이 제공됩니다. 따라서 현재 사용 중인 기능의 간략한 설명을 확인하고 관련 문서와 비디오에 액세스할 수 있습니다.</p>
<p>상황별 도움말을 표시하려면 화면의 오른쪽 위의 <img src="../assets/icon-context.png"/> 아이콘을 클릭합니다. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**기타 개선 사항**

* 이제는 미국뿐 아니라 **EMEA**&#x200B;에서도 Journey Orchestration을 사용할 수 있습니다. 애플리케이션과 설명서는 프랑스어 및 독일어로 제공됩니다.

* 이제 Experience League가 제품에 통합되어 제공됩니다. 따라서 관련 콘텐츠에 간편하게 액세스할 수 있으며 Experience Cloud를 최대한 활용할 수 있습니다. [도움말] 탭 아래쪽에서 Journey Orchestration 설명서에 바로 액세스할 수 있습니다. 또한 도움말 > 피드백을 클릭하여 문제를 보고하거나 Adobe와 아이디어를 공유할 수 있습니다.

* 이제는 여정, 데이터 소스, 작업, 이벤트 등의 모든 목록 화면에서 새 항목 만들기용 바로 가기(**c**)를 사용할 수 있습니다. [자세히 보기](../about/user-interface.md#section_ksq_zr1_ffb)

* 이제는 정지된 여정을 **삭제**&#x200B;할 수 있습니다. 그러면 삭제한 여정을 연관된 보고서를 사용할 수 없게 됩니다.

* 이제 **Adobe Experience Platform 필드**(XDM 형식)를 통해 검색할 때 필드 이름과 함께 표시 이름도 표시됩니다. 이 정보는 Experience Data Model의 스키마 정의에서 검색됩니다. 사용 가능한 경우 대체 표시 이름이 나타납니다. 사용자에게 친숙한 이 설명을 통해 필드를 더 쉽게 확인할 수 있으므로 eVar 필드 사용 시에 특히 유용합니다. [자세히 보기](../about/user-interface.md#friendly-names-display)

## GA 릴리스 - 2019년 12월 {#ga-release---december-2019}

이제 Journey Orchestration이 GA(일반 공급)됩니다.

이벤트 또는 데이터 소스에 저장된 컨텍스트 데이터를 활용하여 실시간 오케스트레이션 사용 사례를 구축합니다.

Journey Orchestration에서는 이벤트, Adobe Experience Platform의 정보 또는 서드파티 API 서비스의 데이터를 활용한 실시간 오케스트레이션이 가능합니다. 이 애플리케이션은 여러 단계로 진행되는 &#39;여정&#39;를 통해 소비자의 프로필과 행동을 토대로 하여 해당 사용자에 맞는 최적의 다음 작업을 결정합니다. 즉, 다음 작업을 수행하기에 가장 적절한 시점과 해당 작업의 유형이 모두 결정됩니다. Adobe Campaign Standard 트랜잭션 메시지 기능을 통해 소비자에게 푸시 알림을 보내거나(Adobe Campaign Standard 필요), 서드파티 시스템의 알림을 보내는 등의 작업을 예로 들 수 있습니다. 규칙과 Sensei 점수를 기반으로 이러한 사항을 결정합니다.

[](../action/working-with-adobe-campaign.md)Journey Orchestration에 대해 자세히 알아보십시오.

추가 리소스:

* [튜토리얼](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/introduction.html?lang=ko-KR)
* [커뮤니티](https://www.adobe.com/go/journeyorchestrationcommunity)
