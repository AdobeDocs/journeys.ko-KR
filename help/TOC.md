---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Journey Orchestration 안내서
user-guide-description: 여정 구현 및 구축 방법에 대한 지침을 확인할 수 있습니다.
index: true
feature: Journeys
source-git-commit: 235992282b0a05873dc17984e044400dc8de1dd8
workflow-type: ht
source-wordcount: '440'
ht-degree: 100%

---


# [!DNL Journey Orchestration] 안내서 {#using}

+ [제품 설명서](journey-orchestration-home.md)
+ 새로운 기능 {#release-notes}
   + [릴리스 정보](using/release-notes/release-notes.md)
   + [설명서 업데이트](using/release-notes/documentation-updates.md)
   + [Journey Optimizer로 업그레이드](using/release-notes/upgrade-to-ajo.md)
+ [!DNL Journey Orchestration] 시작 {#starting-with-journeys}
   + [ [!DNL Journey Orchestration] 정보](using/about/about-journey-orchestration.md)
   + [제한 사항](using/about/limitations.md)
   + [시작](using/about/get-started.md)
   + [사용자 인터페이스](using/about/user-interface.md)
   + [액세스 관리](using/about/access-management.md)
   + [문제 해결](using/about/troubleshooting.md)
   + [외부 시스템과 통합](using/about/external-systems.md)
+ 이벤트 구성 {#events-journeys}
   + 이벤트 정보 {#about-events}
      + [일반 원칙](using/event/about-events.md)
      + [데이터 주기](using/event/about-data-cycle.md)
      + [이벤트 만들기](using/event/about-creating.md)
      + [Adobe Analytics 활용](using/event/about-analytics.md)
      + [ExperienceEvent 스키마 정보](using/event/experience-event-schema.md)
      + [이벤트를 보내는 추가적인 단계](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [페이로드 필드 정의](using/event/defining-the-payload-fields.md)
   + [네임스페이스 선택](using/event/selecting-the-namespace.md)
   + [이벤트 키 정의](using/event/defining-the-event-key.md)
   + [페이로드 미리 보기](using/event/previewing-the-payload.md)
+ 데이터 소스 구성 {#data-source-journeys}
   + [데이터 소스 정보](using/datasource/about-data-sources.md)
   + [필드 그룹](using/datasource/field-groups.md)
   + [Adobe Experience Platform 데이터 소스](using/datasource/adobe-experience-platform-data-source.md)
   + [외부 데이터 소스](using/datasource/external-data-sources.md)
+ 작업 구성 {#action-journeys}
   + [작업 정보](using/action/action.md)
   + [Adobe Campaign Standard 작업](using/action/working-with-adobe-campaign.md)
   + [Adobe Campaign v7/v8 작업](using/action/acc-action.md)
   + 서드파티 시스템 사용 {#action-third-party}
      + [사용자 지정 작업 구성 정보](using/action/about-custom-action-configuration.md)
      + [URL 구성](using/action/url-configuration.md)
      + [작업 매개 변수 정의](using/action/defining-the-message-parameters.md)
+ 세그먼트 사용 {#configuring-segment}
   + [세그먼트 정보](using/segment/about-segments.md)
   + [세그먼트 작성](using/segment/creating-a-segment.md)
   + [조건에서 세그먼트 사용](using/segment/using-a-segment.md)
+ 여정 구축 {#building-journeys}
   + 여정 구축 {#about-journey-building}
      + [여정 만들기](using/building-journeys/journey.md)
      + [여정 디자이너 사용](using/building-journeys/using-the-journey-designer.md)
      + [속성 변경](using/building-journeys/changing-properties.md)
      + [여정 버전](using/building-journeys/journey-versions.md)
      + [여정 종료](using/building-journeys/terminating-a-journey.md)
      + [시간대 관리](using/building-journeys/timezone-management.md)
      + [테스트 프로필](using/building-journeys/creating-test-profiles.md)
   + 활동 {#about-journey-building}
      + 이벤트 활동 {#events-activities}
         + [이벤트 활동 정보](using/building-journeys/event-activities.md)
         + [일반 이벤트](using/building-journeys/general-events.md)
         + [반응 이벤트](using/building-journeys/reaction-events.md)
         + [세그먼트 자격 이벤트](using/building-journeys/segment-qualification-events.md)
      + 오케스트레이션 활동 {#orchestration-activities}
         + [오케스트레이션 활동 정보](using/building-journeys/about-orchestration-activities.md)
         + [조건 활동](using/building-journeys/condition-activity.md)
         + [종료 활동](using/building-journeys/end-activity.md)
         + [대기 활동](using/building-journeys/wait-activity.md)
      + 작업 활동 {#action-activities}
         + [작업 활동 정보](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign Standard 사용](using/building-journeys/using-adobe-campaign-actions.md)
         + [Adobe Campaign v7/v8 사용](using/building-journeys/using-adobe-campaign-classic.md)
         + [사용자 지정 작업 사용](using/building-journeys/using-custom-actions.md)
         + [여정 간 이동](using/building-journeys/jump.md)
         + [프로필 업데이트](using/building-journeys/update-profiles.md)
   + [여정 테스트](using/building-journeys/testing-the-journey.md)
   + [여정 게시](using/building-journeys/publishing-the-journey.md)
   + Adobe Experience Platform과 여정 단계 공유 {#sharing-journey-steps}
      + [여정 단계 공유 개요](using/building-journeys/sharing-overview.md)
      + [단계 이벤트 필드 목록](using/building-journeys/sharing-field-list.md)
      + 레거시 단계 이벤트 필드 {#legacy-step-event-fields}
         + [레거시 필드 정보](using/building-journeys/sharing-legacy-fields.md)
         + [journeySteps 이벤트 공통 필드](using/building-journeys/sharing-common-fields.md)
         + [journeyStep 이벤트 작업 실행 필드](using/building-journeys/sharing-execution-fields.md)
         + [journeyStep 이벤트 데이터 가져오기 필드](using/building-journeys/sharing-fetch-fields.md)
         + [journeyStep 이벤트 ID 필드](using/building-journeys/sharing-identity-fields.md)
         + [여정 필드](using/building-journeys/sharing-journey-fields.md)
      + [쿼리 예제](using/building-journeys/query-examples.md)
+ 표현식 작성 {#building-advanced-conditions-journeys}
   + [개요](using/expression/expressionadvanced.md)
   + 구문 {#syntax}
      + [일반성](using/expression/generalities.md)
      + [조건부 지침](using/expression/conditional-instruction.md)
      + [데이터 유형](using/expression/data-types.md)
      + [필드 참조](using/expression/field-references.md)
      + [컬렉션 관리 기능](using/expression/collection-management-functions.md)
      + [연산자](using/expression/operators.md)
      + [여정 속성](using/expression/journey-properties.md)
      + [예시](using/expression/advanced-editor-use-cases.md)
   + 함수 {#main-functions-journey}
      + [기본 함수](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + 집계 {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + 전환 {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 날짜 {#date}
         + [currentTimeInMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + 목록 {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [limit](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + 수학 {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 문자열 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ 보고서 작성{#journey-reports}
   + [여정 보고서 정보](using/reporting/about-journey-reports.md)
   + [여정 보고서 만들기](using/reporting/creating-your-journey-reports.md)
   + [지표 및 차원](using/reporting/metrics-and-dimensions.md)
+ 인텔리전스 서비스와 통합{#use-case-advanced}
   + [AI 통합 정보](using/ai-services/ai-services-overview.md)
   + [고객 AI 활용](using/ai-services/leveraging-customer-ai.md)
+ 사용 사례{#use-cases-journeys}
   + 개인화된 이메일 전송{#use-case-simple}
      + [단순 사용 사례 정보](using/usecase/about-the-simple-use-case.md)
      + [이벤트 구성](using/usecase/configuring-the-event.md)
      + [데이터 소스 구성](using/usecase/configuring-the-data-source.md)
      + [여정 구축](using/usecase/simple-uc-building-the-journey.md)
   + 크로스 채널 여정 구축{#use-case-advanced}
      + [고급 사용 사례 정보](using/usecase/about-the-advanced-use-case.md)
      + [이벤트 구성](using/usecase/configuring-the-events.md)
      + [데이터 소스 구성](using/usecase/configuring-the-data-sources.md)
      + [여정 구축](using/usecase/building-the-journey.md)
   + [Campaign v7/v8을 사용하여 메시지 보내기](using/usecase/campaign-classic-use-case.md)
   + [사용자 지정 작업으로 컬렉션을 동적으로 보내기](using/usecase/collections.md)
+ API 작업{#working-with-apis}
   + [API 한도 설정](using/api/capping.md)
