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
translation-type: ht
source-git-commit: 0bf8ce5974b7be684a156d5c5445dca122213237
workflow-type: ht
source-wordcount: '383'
ht-degree: 100%

---


# 설명서 업데이트 정보

이 페이지에는 Journey Orchestration의 설명서 업데이트 내용이 모두 포함되어 있습니다.
Journey Orchestration [릴리스 정보](../release-notes/release-notes.md)도 확인할 수 있습니다.

## 2020년 3월 {#march-2020}

* 테스트 로그 섹션에 _actionExecutionErrors_ 및 _fetchErrors_&#x200B;의 매개 변수 설명이 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#viewing_logs)
* 경로에 사용되는 사용자 지정 작업 관련 제한이 업데이트되었습니다. **URL** 필드 및 **Authentication** 매개 변수도 수정할 수 있습니다. [자세한 내용](../action/about-custom-action-configuration.md)
* 새 상황별 도움말 항목이 추가되었습니다. 이제 작업 및 데이터 소스의 사용자 지정 인증 페이로드 창에 도움말 아이콘이 포함되어 있습니다. 해당 아이콘을 클릭하면 이 [섹션](../datasource/external-data-sources.md#section_wjp_nl5_nhb)으로 이동하게 됩니다.
* 이제는 완료된 여정도 정지할 수 있습니다. [자세한 내용](../building-journeys/using-the-journey-designer.md)
* 인터페이스 설명 섹션의 구성이 변경되었습니다. [자세한 내용](../about/user-interface.md)
* 여러 이벤트를 트리거하는 방법이 테스트 모드 섹션에 추가되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#firing_events)
* 새 **테스트의 대기 시간** 매개 변수 관련 내용이 추가되어 테스트 모드 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md)
* 외부 호출 오류 코드 및 응답이 추가되어 테스트 로그 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md#viewing_logs)
* 이제는 경로 속성 패널에서 중앙 집중식으로 시간대를 관리할 수 있습니다. [여기](../building-journeys/changing-properties.md#timezone)와 [여기](../building-journeys/timezone-management.md)에서 자세한 내용을 확인할 수 있습니다.
* 최근 향상된 기능을 반영하여 경로 디자이너 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/using-the-journey-designer.md)
* 상황별 도움말 관련 정보가 추가되어 인터페이스 설명이 업데이트되었습니다. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)
* 이제 **XDM 필드**&#x200B;를 탐색할 때 친숙한 이름이 표시됩니다. 해당 내용을 반영하여 관련 섹션이 업데이트되었습니다. [자세한 내용](../about/user-interface.md#friendly-names-display)


## 2020년 2월 {#february-2020}

* 바로 가기 섹션이 업데이트되었습니다. **C** 바로 가기를 사용하면 모든 목록 화면에서 새 항목을 만들 수 있습니다. [자세한 내용](../about/user-interface.md#section_ksq_zr1_ffb)

## 2020년 1월 {#january-2020}

* [경험 이벤트](../datasource/adobe-experience-platform-data-source.md) 및 [세그먼트](../functions/functioninsegment.md)의 가져오기 제한 관련 내용이 추가되었습니다.
* [getBestSendTime 설명서](../functions/functiongetbestsendtime.md)가 업데이트되었습니다.

## 2019년 12월 {#december-2019}

* 인터페이스 변경 사항을 반영하여 모든 스크린샷이 업데이트되었습니다.
* 테스트 모드 섹션이 업데이트되었습니다. [자세한 내용](../building-journeys/testing-the-journey.md)
* [이메일 전송 시간 최적화](../building-journeys/wait-activity.md) 및 [예측 피로도 점수](../usecase/leveraging-fatigue-scores.md) 섹션에 경고가 추가되었습니다. 이러한 기능은 Adobe Campaign Standard 데이터 서비스 기능을 사용하는 고객에게만 제공됩니다.
* 이제는 정지된 경로를 삭제할 수 있습니다. 관련 설명서 페이지가 업데이트되었습니다.
* 이제는 경로에서 문제가 탐지되면 두 가지 색상이 표시됩니다. 오류의 경우 빨간색, 경고의 경우에는 주황색이 표시됩니다. [자세한 내용](../about/troubleshooting.md)
* 고급 표현식 편집기 섹션이 업데이트되었습니다. [자세한 내용](../expression/expressionadvanced.md)
* [조건부 지침](../expression/conditional-instruction.md) 및 [컬렉션 관리](../expression/collection-management-functions.md) 섹션이 이동/업데이트되었습니다.
* [함수](../expression/functions.md) 섹션이 업데이트되었으며 새 예제가 추가되었습니다.
* 시간대 구문 변경 사항을 반영하여 [toDateTime function](../functions/functiontodatetime.md) 설명서가 업데이트되었습니다.
