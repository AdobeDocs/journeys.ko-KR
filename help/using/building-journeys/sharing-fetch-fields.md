---
title: journeyStep 이벤트 데이터 가져오기 필드
description: journeyStep 이벤트 데이터 가져오기 필드
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# journeyStep 이벤트 데이터 가져오기 필드 {#sharing-fetch-fields}

이 혼합은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

단계 처리 중에 필드 그룹에 대해 N 데이터를 가져올 수 있습니다.

## fetchTotalTime

단계 처리 중 데이터 가져오기에 소요된 총 시간입니다.

유형: long

## fetchTypeInError

가져오기 시작 오류가 Adobe Experience Platform 또는 사용자 지정 데이터 소스에 있는지 정의합니다.

유형: 문자열

값:
* aep
* 사용자 지정

## fetchError

데이터 가져오기가 처리될 때 발생하는 오류 유형입니다.

유형: 문자열

값:
* http
* 랩
* 시간 제한
* error

## fetchErrorCode

가져오기 오류 코드. 오류에 HTTP 코드 등의 코드가 있을 경우 표시됩니다. 예를 들어 actionExecError가 http인 경우 코드 404는 HTTP 404 오류를 나타냅니다.

유형: 문자열

## fetchOriginError

시간 초과는 다음 두 경우에 발생할 수 있습니다.

* 처음 시도하면 작업이 실행됩니다. 이 경우 실행이 완료되지 않았으므로 기본 오류가 없습니다.
* 재시도에서: 이 경우 actionExecOrigError/actionExecOrigErrorCode는 재시도 전에 발생한 오류에 대해 설명합니다.

예를 들어 통합 프로필 서비스에서 데이터를 가져오는 경우 첫 번째 시도에서 HTTP 500 오류가 반환됩니다. 가져오기가 다시 시도되지만 2회 시도 기간이 시간 초과를 초과합니다. 그러면 작업 실행에 타임아웃으로 태그가 지정됩니다. 작업 부분은 다음과 같습니다.

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

유형: 문자열

## fetchOriginErrorCode

시스템에서 제공하는 오류 코드를 쿼리하고 [!DNL Journey Orchestration] 있습니다. 예를 들어 404, 500 등이 될 수 있습니다.

유형: 문자열

## fetchCount

소스 유형에 상관없이 데이터를 가져오는 횟수.

유형: long

## fetchPlatformTotalTime

Adobe Experience Platform에서 데이터를 가져오는 데 걸린 총 시간입니다. 참고: 이 시간은 엔진이 농축 이벤트를 우라늄 서비스에 보내고 응답을 받는 시점부터 계산됩니다.

유형: long

## fetchPlatformCount

Adobe Experience Platform에서 데이터를 가져오는 횟수입니다.

유형: long

## fetchCustomTotalTime

사용자 지정 데이터를 밀리 단위로 가져오는 시간입니다. 참고: 이 시간은 엔진이 농축 이벤트를 우라늄 서비스에 보내고 응답을 받은 시점부터 계산됩니다

유형: long

## fetchCustomCount

외부 시스템에서 사용자 지정 데이터를 가져오는 횟수입니다.

유형: long
