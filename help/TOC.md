---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# 여정 운영 도움말 {#using}

+ [제품 설명서](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [릴리스 정보](using/release-notes/release-notes.md)
   + [설명서 업데이트 정보](using/release-notes/documentation-updates.md)
+ 고객 여정 통합 운영 {#starting-with-journeys}
   + [여정 통합 운영 정보](using/about/about-journey-orchestration.md)
   + [시작하기](using/about/get-started.md)
   + [유저 인터페이스](using/about/user-interface.md)
   + [액세스 관리](using/about/access-management.md)
   + [문제 해결](using/about/troubleshooting.md)
+ 이벤트 구성 {#events-journeys}
   + [이벤트 정보](using/event/about-events.md)
   + [페이로드 필드 정의](using/event/defining-the-payload-fields.md)
   + [네임스페이스 선택](using/event/selecting-the-namespace.md)
   + [이벤트 키 정의](using/event/defining-the-event-key.md)
   + [조건 추가](using/event/adding-a-condition.md)
   + [페이로드 미리 보기](using/event/previewing-the-payload.md)
   + [이벤트를 전송하는 추가 단계](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ 데이터 소스 구성 {#data-source-journeys}
   + [데이터 소스 정보](using/datasource/about-data-sources.md)
   + [필드 그룹](using/datasource/field-groups.md)
   + [Adobe Experience Platform 데이터 소스](using/datasource/adobe-experience-platform-data-source.md)
   + [외부 데이터 소스](using/datasource/external-data-sources.md)
+ 작업 구성 {#action-journeys}
   + [작업 정보](using/action/action.md)
   + [Adobe Campaign 작업](using/action/working-with-adobe-campaign.md)
   + 타사 시스템 사용 {#action-third-party}
      + [사용자 지정 작업 구성 정보](using/action/about-custom-action-configuration.md)
      + [사용자 지정 작업 제한](using/action/custom-action-limitations.md)
      + [URL 구성](using/action/url-configuration.md)
      + [메시지 매개 변수 정의](using/action/defining-the-message-parameters.md)
+ 고객 여정 구축 {#building-journeys}
   + 고객 여정 구축 정보 {#about-journey-building}
      + [고객 여정 만들기](using/building-journeys/journey.md)
      + [고객 여정 디자이너 사용](using/building-journeys/using-the-journey-designer.md)
      + [속성 변경](using/building-journeys/changing-properties.md)
      + [고객 여정 버전](using/building-journeys/journey-versions.md)
      + [경로 종료](using/building-journeys/terminating-a-journey.md)
      + [시간대 관리](using/building-journeys/timezone-management.md)
   + 활동 {#about-journey-building}
      + [이벤트 활동](using/building-journeys/event-activities.md)
      + 통합 운영 활동 {#orchestration-activities}
         + [오케스트레이션 활동 정보](using/building-journeys/about-orchestration-activities.md)
         + [조건 활동](using/building-journeys/condition-activity.md)
         + [종료 활동](using/building-journeys/end-activity.md)
         + [대기 활동](using/building-journeys/wait-activity.md)
      + 작업 활동 {#action-activities}
         + [작업 활동 정보](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign 동작 사용](using/building-journeys/using-adobe-campaign-actions.md)
         + [사용자 정의 작업 사용](using/building-journeys/using-custom-actions.md)
   + [고객 여정 테스트](using/building-journeys/testing-the-journey.md)
   + [고객 여정 게시](using/building-journeys/publishing-the-journey.md)
+ 고급 표현식 편집기 사용 {#building-advanced-conditions-journeys}
   + [고급 표현식 편집기 정보](using/expression/expressionadvanced.md)
   + 구문 {#syntax}
      + [일반성](using/expression/generalities.md)
      + [조건부 지침](using/expression/conditional-instruction.md)
      + [데이터 유형](using/expression/data-types.md)
      + [필드 참조](using/expression/field-references.md)
      + [컬렉션 관리 기능](using/expression/collection-management-functions.md)
      + [연산자](using/expression/operators.md)
   + 함수 {#main-functions-journey}
      + [기본 함수](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + 집계 {#aggregation}
         + [avl](using/functions/functionavg.md)
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
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 날짜 {#date}
         + [현재 &#x200B; 시간 InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [지난 달](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [다음 날](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [다음 달](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + 목록 {#list}
         + [뚜렷하](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [정렬](using/functions/functionsort.md)
      + 수학 {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 문자열 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorease](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [길이](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [트리밍](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ 보고서 작성{#journey-reports}
   + [경로 보고서 정보](using/reporting/about-journey-reports.md)
   + [여정 보고서 만들기](using/reporting/creating-your-journey-reports.md)
   + [지표 및 차원](using/reporting/metrics-and-dimensions.md)
+ 활용 사례{#use-cases-journeys}
   + 간단한 사용 사례{#use-case-simple}
      + [간단한 사용 사례 정보](using/usecase/about-the-simple-use-case.md)
      + [이벤트 구성](using/usecase/configuring-the-event.md)
      + [데이터 소스 구성](using/usecase/configuring-the-data-source.md)
      + [고객 여정 구축](using/usecase/simple-uc-building-the-journey.md)
   + 고급 사용 사례{#use-case-advanced}
      + [고급 사용 사례 정보](using/usecase/about-the-advanced-use-case.md)
      + [이벤트 구성](using/usecase/configuring-the-events.md)
      + [데이터 소스 구성](using/usecase/configuring-the-data-sources.md)
      + [고객 여정 구축](using/usecase/building-the-journey.md)
   + [피로 점수 활용](using/usecase/leveraging-fatigue-scores.md)

