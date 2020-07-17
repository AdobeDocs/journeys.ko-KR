---
title: 설명서 업데이트 정보
description: 설명서 업데이트에 대해 알아보기
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 51%

---


# 설명서 업데이트 정보

This page lists all the documentation updates for [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## 2020년 7월 {#july-2020}

* Adobe Experience Platform에 대한 단계 이벤트 보고 시 새로운 자습서 비디오에 대한 링크를 추가했습니다. [자세한 내용](../building-journeys/sharing-overview.md)
* 이벤트 활동 섹션은 각 이벤트 유형에 대한 전용 하위 섹션으로 재구성되었습니다. [자세한 내용](../building-journeys/event-activities.md)
* 세그먼트 품질에 대한 오버로드를 방지하기 위한 우수 사례를 추가했습니다. [자세한 내용](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 작업 또는 조건에 오류가 발생한 후 여행을 계속하는 방법을 설명하는 참고가 추가되었습니다. [자세한 내용](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 제한된 고객 세트에서 테스트되는 알파 기능에 새로운 섹션이 추가되었습니다. [자세한 내용](../alpha/alpha-overview.md)
* Intelligent Services 통합에 새 섹션이 추가되었습니다. [자세한 내용](../ai-services/ai-services-overview.md)
* 테스트 프로필 만들기에 새 섹션이 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#create-test-profile)
* 경로 조건 또는 작업에서 노드를 사용하는 방법에 대한 **[!UICONTROL SegmentQualification]** 정보가 추가되었습니다. [자세한 내용](../building-journeys/segment-qualification-events.md)
* 캠페인 트랜잭션 메시지 및 이벤트 게시에 메모가 추가되었습니다. Adobe Campaign [작업](../action/working-with-adobe-campaign.md) 및 Adobe Campaign 작업 [사용을 참조하십시오](../building-journeys/using-adobe-campaign-actions.md).
* Campaign Standard 인스턴스 URL을 테스트할 때 수행되는 검사에 정보가 추가되었습니다. [자세한 내용](../action/working-with-adobe-campaign.md)
* AWS 또는 Azure 서버에서 호스팅되는 Campaign Standard 인스턴스와의 반응 이벤트 호환성에 대한 정보가 추가되었습니다. [자세한 내용](../building-journeys/reaction-events.md)
* Campaign Standard 트랜잭션 메시징을 사용하여 작업할 때 매핑 규칙을 설정해야 하는 데 대한 메모가 추가되었습니다. [자세한 내용](../action/working-with-adobe-campaign.md)
* 테스트 모드를 사용하여 이벤트를 트리거할 때 실제 이벤트 생성에 대한 메모가 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#firing_events)

## 2020년 6월 {#june-2020}

* 사용자 지정 인증 데이터 소스에 대한 토큰의 캐시 지속 시간을 변경하는 방법에 대한 정보가 추가되었습니다. [자세한 내용](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* 변경된 경로 상태 이름을 반영하도록 업데이트된 스크린샷 및 텍스트 **[!UICONTROL Finished]** **[!UICONTROL Closed (no entrance)]**.
* 인터페이스에 대한 언어가 정의된 방식에 대한 정보가 추가되었습니다. [자세한 내용](../about/user-interface.md)
* 개별 경로의 상태 목록이 [테스트 모드 로그 섹션으로](../building-journeys/testing-the-journey.md#viewing_logs) 이동되었습니다.

## 2020년 4월 {#april-2020}

* 사용자가 첫 번째 이벤트를 구성하는 데 도움이 되도록 경험 이벤트 스키마 정의에 새 섹션이 추가되었습니다. [자세한 내용](../event/experience-event-schema.md)
* 설명서의 홈 페이지가 [!DNL Journey Orchestration] 유용한 추가 링크로 업데이트되었습니다. [자세한 내용](../../journey-orchestration-home.md)

## 2020년 3월 {#march-2020}

* 테스트 로그 섹션에 _actionExecutionErrors_ 및 _fetchErrors_&#x200B;의 매개 변수 설명이 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#viewing_logs)
* 경로에 사용되는 사용자 지정 작업 관련 제한이 업데이트되었습니다. You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [자세한 내용](../action/about-custom-action-configuration.md)
* 새 상황별 도움말 항목이 추가되었습니다. 이제 작업 및 데이터 소스의 사용자 지정 인증 페이로드 창에 도움말 아이콘이 포함되어 있습니다. 해당 아이콘을 클릭하면 이 [섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)으로 이동하게 됩니다.
* 폐쇄적인 여정은 이제 멈출 수 있다. [자세한 내용](../building-journeys/using-the-journey-designer.md)
* 인터페이스 설명 섹션의 구성이 변경되었습니다. [자세한 내용](../about/user-interface.md)
* 여러 이벤트를 트리거하는 방법이 테스트 모드 섹션에 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#firing_events)
* 테스트 모드 섹션이 새 매개 변수에 대해 **[!UICONTROL Wait time in test]** 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md)
* 외부 호출 오류 코드 및 응답이 추가되어 테스트 로그 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#viewing_logs)
* 이제는 경로 속성 패널에서 중앙 집중식으로 시간대를 관리할 수 있습니다. [여기](../building-journeys/changing-properties.md#timezone)와 [여기](../building-journeys/timezone-management.md)에서 자세한 내용을 확인할 수 있습니다.
* 최근 향상된 기능을 반영하여 경로 디자이너 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/using-the-journey-designer.md)
* 상황별 도움말 관련 정보가 추가되어 인터페이스 설명이 업데이트되었습니다. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)
* 이제 **XDM 필드**&#x200B;를 탐색할 때 친숙한 이름이 표시됩니다. 해당 내용을 반영하여 관련 섹션이 업데이트되었습니다. [자세한 내용](../about/user-interface.md#friendly-names-display)

## 2020년 2월 {#february-2020}

* 바로 가기 섹션이 업데이트되었습니다. **C** 바로 가기를 사용하면 모든 목록 화면에서 새 항목을 만들 수 있습니다. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)
* 데이터 소스 [및](../datasource/about-data-sources.md) 작업 [](../action/action.md) 개요 페이지가 개선되었습니다.

## 2020년 1월 {#january-2020}

* [경험 이벤트](../datasource/adobe-experience-platform-data-source.md) 및 [세그먼트](../functions/functioninsegment.md)의 가져오기 제한 관련 내용이 추가되었습니다.
* [getBestSendTime 설명서](../functions/functiongetbestsendtime.md)가 업데이트되었습니다.

## 2019년 12월 {#december-2019}

* 인터페이스 변경 사항을 반영하여 모든 스크린샷이 업데이트되었습니다.
* 테스트 모드 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md)
* [이메일 전송 시간 최적화](../building-journeys/wait-activity.md) 및 [예측 피로도 점수](../ai-services/leveraging-fatigue-scores.md) 섹션에 경고가 추가되었습니다. 이러한 기능은 Adobe Campaign Standard 데이터 서비스 기능을 사용하는 고객에게만 제공됩니다.
* 이제는 정지된 경로를 삭제할 수 있습니다. 관련 설명서 페이지가 업데이트되었습니다.
* 이제는 경로에서 문제가 탐지되면 두 가지 색상이 표시됩니다. 오류의 경우 빨간색, 경고의 경우에는 주황색이 표시됩니다. [자세한 내용](../about/troubleshooting.md)
* 고급 표현식 편집기 섹션이 업데이트되었습니다. [자세한 내용](../expression/expressionadvanced.md)
* [조건부 지침](../expression/conditional-instruction.md) 및 [컬렉션 관리](../expression/collection-management-functions.md) 섹션이 이동/업데이트되었습니다.
* [함수](../expression/functions.md) 섹션이 업데이트되었으며 새 예제가 추가되었습니다.
* 시간대 구문 변경 사항을 반영하여 [toDateTime function](../functions/functiontodatetime.md) 설명서가 업데이트되었습니다.
