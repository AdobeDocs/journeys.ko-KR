---
title: 릴리스 정보
description: 릴리스 정보에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8641b577e91492c86e6fc8e201acd6a208e5e38b
workflow-type: tm+mt
source-wordcount: '1107'
ht-degree: 84%

---


# 릴리스 정보 {#release-notes}

이 페이지에는 Journey Orchestration의 새로운 기능과 개선 사항이 모두 포함되어 있습니다.
[설명서 업데이트](../release-notes/documentation-updates.md)도 확인할 수 있습니다.

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
<p>다음과 같은 Adobe Experience Platform 통합 기능이 개선되었습니다.</p>
<ul>
<li><p>새로운 활동을 통해 Adobe Experience Platform 세그먼트 입장/출구의 의견 수렴을 통해 사람들이 여행 중에 들어오거나 앞으로 이동할 수 있습니다. <a href="../building-journeys/segment-qualification-events.md">자세한 내용</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Adobe Experience Platform segments can now be created and edited without leaving the Journey Orchestration interface, thanks to a new <strong>Segments</strong> tab.<a href="../segment/about-segments.md">자세한 내용</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>단순 표현식 편집기에서 이제 Adobe Experience Platform 세그먼트가 내비게이션 트리에 바로 나열되므로 "이 사람이 세그먼트 A에 속합니까?"와 같은 조건을 쉽게 설정할 수 있습니다.<a href="../segment/using-a-segment.md">자세한 내용</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration은 이제 여행 중 행해지는 단계인 Adobe Experience Platform으로 자동 전달됩니다. 여기에는 발생한 잠재적 오류도 포함됩니다. 이 정보는 특정 경로 또는 모든 경로에 대해 경로 단계 이벤트에서 쿼리를 실행함으로써 보고 및 문제 해결을 수행하는 데 사용될 수 있습니다. <a href="../building-journeys/sharing-overview.md">자세한 내용</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>이제 Journey Orchestration을 프로덕션 및 비프로덕션 Adobe Experience Platform 샌드박스와 연결할 수 있습니다. 샌드박스는 베타 기능입니다. <a href="../about/access-management.md#sandboxes">자세한 내용</a></p>
</li>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>경로 디자이너 및 테스트 모드 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>경로 디자이너 및 테스트 모드가 다음과 같이 개선되었습니다.</p>
<ul>
<li><p>이제 1 또는 N 경로 활동을 선택하면서 붙여넣기 활동을 한 경로에서 다른 경로로 복사할 수 있습니다. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">자세한 내용</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>이제는 테스트 프로필이 경로에 들어가도록 만드는 이벤트를 시작한 후에 색상으로 표시되는 시각적 플로우를 통해 경로 내 진행 상황을 확인할 수 있습니다. 경로에서 오류가 발생하는 경우 오류의 세부 정보도 표시됩니다. <a href="../building-journeys/testing-the-journey.md#firing_events">자세한 내용</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li><strong>Finished</strong> 경로 상태가 해당 상태의 의미를 더 잘 반영하도록 <strong>Closed (no entrance)</strong>로 이름이 바뀌었습니다.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**기타 개선 사항**

서드파티 시스템에 너무 많은 API 호출을 보내지 않도록 &quot;최대 가용량&quot; 규칙을 설정하는 새로운 공개 API를 채택하고 있습니다. 최대 가용량 규칙을 사용하면 API 엔드포인트에 대한 밀리초당 최대 호출 수를 정의할 수 있습니다. [자세한 내용](../api/capping.md)

이제 액세스 제어를 통해 사용자 액세스를 더 세부적으로 관리할 수 있습니다. 발효 날짜: 2020년 6월 30일. [자세한 내용](../about/access-management.md#create-product-profile)

이제 APAC(호주 데이터 센터)에서 Journey Orchestration을 사용할 수 있습니다. 발효 날짜: 2020년 6월 30일

Journey Orchestration 인터페이스를 일본어로 사용할 수 있습니다.

## 1분기 릴리스 - 2020년 3월 {#q1-release---march-2020}

**새로운 기능?**

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
<li>이제는 경로 하나에서 여러 이벤트를 사용할 때 테스트 모드의 <strong>이벤트 구성</strong> 화면 내 드롭다운 목록에서 각 이벤트를 개별적으로 트리거할 수 있습니다. <a href="../building-journeys/testing-the-journey.md#firing_events">자세한 내용</a></p></li>
<li><p>이제는 여정에서 <strong>대기</strong> 활동을 하나 이상 사용할 때 테스트 모드에서 이러한 각 활동을 진행할 시간을 정의할 수 있습니다. 기본 시간은 10초입니다. 왼쪽 아래에서 <strong>테스트의 대기 시간</strong> 매개 변수를 사용하여 이 시간을 변경할 수 있습니다. <a href="../building-journeys/testing-the-journey.md">자세한 내용</a></p><img src="../assets/rn-test.png"/>
</li>
<li>이제는 서드파티 시스템(데이터 소스 또는 작업)을 호출할 때 오류가 발생하면 <strong>테스트 로그</strong>에 오류 코드와 오류 응답이 표시됩니다. <a href="../building-journeys/testing-the-journey.md#viewing_logs">자세한 내용</a>
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
<p>이제는 경로 속성 패널에서 중앙 집중식으로 시간대를 관리할 수 있습니다. 중앙 집중식 관리를 위해 경로 속성에 매개 변수 두 개가 추가되었습니다.</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li><strong>시간대</strong> 드롭다운 목록에서 특정 시간대를 선택할 수 있습니다. 기본적으로는 브라우저의 시간대가 사용됩니다. </li>
<li>The <strong>Profile Timezone</strong> checkbox allows you to use the Adobe Experience Platform Profile timezone of the person entering the journey, if available. 이 확인란을 선택하지 않으면 드롭다운 목록에서 정의한 시간대가 사용됩니다. 이 기능은 네임스페이스가 없는 이벤트를 사용하는 경로와는 호환되지 않습니다.</li>
</ul>
<p>자세한 내용은 <a href="../building-journeys/changing-properties.md#timezone">속성 변경</a> 및 <a href="../building-journeys/timezone-management.md">시간대 관리</a> 섹션을 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>향상된 경로 디자이너</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>경로 디자이너 왼쪽의 경로 <strong>팔레트</strong>가 다음과 같이 향상되었습니다.</p>
<ul>
<li><strong>검색</strong> 창 옆의 새 아이콘을 클릭하면 팔레트에서 사용할 수 없는 요소(예: 경로에 사용되는 것과 다른 네임스페이스를 사용하는 이벤트)를 숨기거나 표시할 수 있습니다. 기본적으로 사용할 수 없는 항목은 숨겨집니다.</li>
<li>이제는 <strong>검색</strong> 필드를 사용할 때 각 캔버스 활동 범주의 결과 수가 표시됩니다.</li>
<li>활동 범주 간의 탐색 방식이 개선되었습니다.</li>
</ul>
<p>이제는 경로 디자이너에서 경로의 최신 버전에 액세스하고 있는지를 확인할 수 있습니다. 이 정보는 버전 번호 옆에 표시됩니다.</p>
<p>이제는 경로 <strong>캔버스</strong>에서 두 활동의 연결이 끊기면 경고 메시지가 표시됩니다.</p>
<img src="../assets/rn-canvas.png"/>
<p>자세한 내용은 <a href="../building-journeys/using-the-journey-designer.md">세부 설명서</a>를 참조하십시오.</p>
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
<p>이제 경로, 이벤트, 작업, 데이터 소스 등의 다양한 Journey Orchestration 목록 화면에서 상황별 도움말이 제공됩니다. 따라서 현재 사용 중인 기능의 간략한 설명을 확인하고 관련 문서와 비디오에 액세스할 수 있습니다.</p>
<p>상황별 도움말을 표시하려면 화면의 오른쪽 위의 <img src="../assets/icon-context.png"/> 아이콘을 클릭합니다. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**기타 개선 사항**

* In addition to US, Journey Orchestration is now available in **EMEA**. 애플리케이션과 설명서는 프랑스어 및 독일어로 제공됩니다.

* 이제 Experience League가 제품에 통합되어 제공됩니다. 따라서 관련 콘텐츠에 간편하게 액세스할 수 있으며 Experience Cloud를 최대한 활용할 수 있습니다. [도움말] 탭 아래쪽에서 Journey Orchestration 설명서에 바로 액세스할 수 있습니다. 또한 [도움말] > [의견]을 클릭하여 문제를 보고하거나 Adobe와 아이디어를 공유할 수 있습니다.

* 이제는 경로, 데이터 소스, 작업, 이벤트 등의 모든 목록 화면에서 새 항목 만들기용 바로 가기(**c**)를 사용할 수 있습니다. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)

* 이제는 정지된 경로를 **삭제**&#x200B;할 수 있습니다. 그러면 삭제한 경로와 연관된 보고서를 사용할 수 없게 됩니다.

* When browsing through **Adobe Experience Platform fields** (XDM format), you will now see the display name in addition to the field name. 이 정보는 Experience Data Model의 스키마 정의에서 검색됩니다. 사용 가능한 경우 대체 표시 이름이 나타납니다. 사용자에게 친숙한 이 설명을 통해 필드를 더 쉽게 확인할 수 있으므로 eVar 필드 사용 시에 특히 유용합니다. [자세한 내용](../about/user-interface.md#friendly-names-display)

## GA 릴리스 - 2019년 12월 {#ga-release---december-2019}

이제 Journey Orchestration이 GA(일반 공급)됩니다.

이벤트나 데이터 소스에 저장된 상황별 데이터를 활용하여 실시간 오케스트레이션 사용 사례를 작성할 수 있습니다.

Journey Orchestration에서는 이벤트, Adobe Experience Platform의 정보 또는 서드파티 API 서비스의 데이터를 활용한 실시간 오케스트레이션이 가능합니다. 이 애플리케이션은 여러 단계로 진행되는 &#39;경로&#39;를 통해 소비자의 프로필과 행동을 토대로 하여 해당 사용자에 맞는 최적의 다음 작업을 결정합니다. 즉, 다음 작업을 수행하기에 가장 적절한 시점과 해당 작업의 유형이 모두 결정됩니다. Adobe Campaign Standard 트랜잭션 메시지 기능을 통해 소비자에게 푸시 알림을 보내거나(Adobe Campaign Standard 필요), 서드파티 시스템의 알림을 보내는 등의 작업을 예로 들 수 있습니다. 규칙과 Sensei 점수를 기반으로 이러한 사항을 결정합니다.

[](../action/working-with-adobe-campaign.md)Journey Orchestration에 대해 자세히 알아보십시오.

추가 자료:

* [튜토리얼](https://docs.adobe.com/content/help/ko-KR/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [커뮤니티](https://www.adobe.com/go/journeyorchestrationcommunity)
