---
title: 릴리스 정보
description: 릴리스 노트에 대한 자세한 내용
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
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d

---


# 릴리스 정보 {#release-notes}

이 페이지에는 고객 여정 오케스트레이션에 대한 모든 새로운 기능과 향상된 기능이 나열됩니다.
설명서 업데이트를 참조할 수도 [있습니다](../release-notes/documentation-updates.md).

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
<p>테스트 모드는 다음과 같이 개선되었습니다.</p>
<ul>
<li>이제 여정에서 여러 이벤트를 사용하는 경우 테스트 모드의 이벤트 구성 <strong>화면에서 각 이벤트를 드롭다운 목록에서 개별적으로 트리거할</strong> 수 있습니다. <a href="../building-journeys/testing-the-journey.md#firing_events">자세한 내용</a></p></li>
<li><p>이제 하나 이상의 <strong>대기</strong> 활동이 여정에서 사용될 때 이러한 각 활동이 테스트 모드에서 지속될 시간을 정의할 수 있습니다. 기본 시간은 10초입니다. 왼쪽 아래 모서리에서 테스트 <strong></strong> 매개 변수의 대기 시간을 사용하여 변경할 수 있습니다. <a href="../building-journeys/testing-the-journey.md">자세한 내용</a></p><img src="../assets/rn-test.png"/>
</li>
<li>이제 <strong>테스트 로그에서</strong>타사 시스템(데이터 소스 또는 작업)을 호출할 때 오류가 발생하는 경우 오류 코드와 오류 응답이 표시됩니다. <a href="../building-journeys/testing-the-journey.md#viewing_logs">자세한 내용</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>중앙 시간대 관리</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>이제 시간대 관리는 여정 속성 패널에서 중앙에서 이루어집니다. 경로 속성에 두 개의 매개 변수가 추가되었습니다.</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>시간대 <strong>드롭다운</strong> 목록을 사용하면 특정 시간대를 선택할 수 있습니다. 기본적으로 브라우저의 표준 시간대가 사용됩니다. </li>
<li>프로필 <strong>표준 시간대</strong> 확인란을 사용하여 여정에 들어오는 사람의 경험 플랫폼 프로필 표준 시간대를 사용할 수 있습니다(가능한 경우). 그렇지 않은 경우 드롭다운 목록에 정의된 시간대가 사용됩니다. 이 기능은 네임스페이스가 없는 이벤트를 사용하는 여정과 호환되지 않습니다.</li>
</ul>
<p>자세한 내용은 속성 <a href="../building-journeys/changing-properties.md#timezone">및</a> 시간대 관리 <a href="../building-journeys/timezone-management.md">섹션을</a> 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>고객 여정 디자이너 개선 사항</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>경로 디자이너의 왼쪽에 있는 경로 <strong>팔레트가</strong>향상되었습니다.</p>
<ul>
<li>검색 막대 옆에 있는 새 <strong>아이콘을 사용하면</strong> 팔레트에서 사용할 수 없는 요소(예: 여정에 사용된 요소와 다른 네임스페이스를 사용하는 이벤트)를 숨기거나 표시할 수 있습니다. 기본적으로 사용할 수 없는 항목은 숨겨집니다.</li>
<li>검색 <strong>필드를 사용할</strong> 때 이제 각 캔버스 활동 카테고리에 대한 결과 수가 표시됩니다.</li>
<li>다른 활동 카테고리 간의 탐색이 개선되었습니다.</li>
</ul>
<p>이제 고객 여정 디자이너에서는 최신 버전의 여정에 액세스하고 있는지 확인할 수 있습니다. 이 정보는 버전 번호 옆에 표시됩니다.</p>
<p>이제 경로 <strong>캔버스에서</strong>두 활동의 연결이 끊기면 경고 메시지가 표시됩니다.</p>
<img src="../assets/rn-canvas.png"/>
<p>자세한 내용은 <a href="../building-journeys/using-the-journey-designer.md">자세한 설명서를</a>참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>상황에 맞는 도움말</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 여정 운영 목록 화면(여정, 이벤트, 작업 및 데이터 소스)에서 상황에 맞는 도움말을 사용할 수 있습니다. 이를 통해 현재 기능에 대한 빠른 설명을 보고 관련 문서 및 비디오에 액세스할 수 있습니다.</p>
<p>상황에 맞는 도움말을 표시하려면 화면의 오른쪽 위 모서리에 있는 <img src="../assets/icon-context.png"/> 아이콘을 클릭합니다. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**기타 개선 사항**

* 미국 외에도 EMEA에서 Journeys Orchestration을 사용할 수 **있습니다**. 애플리케이션과 설명서는 프랑스어와 독일어로 제공됩니다.

* Experience League는 이제 제품에 통합되었습니다. 이렇게 하면 관련 콘텐츠에 대한 액세스가 간소화되고 Experience Cloud를 최대한 활용할 수 있습니다. 경로 관리 설명서에 대한 직접 액세스는 도움말 탭 하단에 있습니다. 또한 도움말 > 피드백을 클릭하여 문제를 보고하거나 Adobe와 아이디어를 공유할 수 있습니다.

* 이제 **새** 항목을 만들 수 있는 C 키보드 단축키를 모든 목록 화면에서 사용할 수 있습니다.여행, 데이터 소스, 작업 및 이벤트. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)

* 이제 중단된 여행을 **삭제할** 수 있습니다. 이러한 삭제된 여정과 관련된 보고서는 사용할 수 없습니다.

* 데이터 플랫폼 **필드** (XDM 형식)를 검색할 때 필드 이름 외에 표시 이름이 표시됩니다. 이 정보는 경험 데이터 모델의 스키마 정의에서 검색됩니다. 사용 가능한 경우 대체 표시 이름이 나타납니다. eVar 필드의 경우 특히 유용한 이 사용자 친화적인 설명을 사용하면 필드를 보다 쉽게 식별할 수 있습니다. [자세한 내용](../about/user-interface.md#friendly-names-display)

## GA 릴리스 - 2019년 12월 {#ga-release---december-2019}

고객 여정 통합 운영

이벤트 또는 데이터 소스에 저장된 컨텍스트 데이터를 활용하여 실시간 통합 활용 사례를 구축할 수 있습니다.

고객 여정 통합 운영을 통해 이벤트, Adobe Experience Platform의 정보 또는 타사 API 서비스의 데이터를 기반으로 한 컨텍스트 기반의 실시간 통합 기능을 사용할 수 있습니다. 이 애플리케이션은 여러 단계로 구성된 흐름에서 소비자의 프로필과 행동을 기반으로 고객에게 적합한 다음 최고의 행동이라고 합니다. 이는 최적의 타이밍뿐만 아니라 Adobe Campaign Standard 트랜잭션 메시징 기능(Adobe Campaign Standard 필요) 또는 타사 시스템의 알림을 통해 고객에게 푸시 알림을 전송하는 등의 작업 유형으로 구성됩니다. 이러한 결정은 규칙과 Sensei 점수를 기반으로 합니다.

[](../action/working-with-adobe-campaign.md)Journey Orchestration에 대해 자세히 알아보십시오.

추가 리소스:

* [튜토리얼](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [커뮤니티](https://www.adobe.com/go/journeyorchestrationcommunity)
