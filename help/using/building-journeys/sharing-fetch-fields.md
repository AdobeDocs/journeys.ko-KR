---
product: adobe campaign
title: journeyStep 이벤트 데이터 가져오기 필드
description: journeyStep 이벤트 데이터 가져오기 필드
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# journeyStep 이벤트 데이터 가져오기 필드 {#sharing-fetch-fields}

이 mixin은 journeyStepEvent 및 journeyStepProfileEvent에서 공유됩니다.

단계 처리 중에 필드 그룹에서 N개의 데이터를 가져올 수 있습니다.

## fetchTotalTime

단계 처리 중 데이터 가져오기에 소요된 총 시간(밀리초)입니다.

유형: long

## fetchTypeInError

가져오기 오류 발생 여부가 Adobe Experience Platform 또는 사용자 지정 데이터 소스인지 정의합니다.

유형: 문자열

값:
* aep
* 사용자 정의

## fetchError

데이터 가져오기를 처리할 때 발생하는 오류 유형.

유형: 문자열

값:
* http
* 캡핑
* 시간 초과
* 오류

## fetchErrorCode

가져오기 오류 코드. 오류에 HTTP 코드와 같은 코드가 있을 경우 표시됩니다. 예를 들어 actionExecError 가 http 이면 코드 404 는 HTTP 404 오류를 나타냅니다.

유형: 문자열

## fetchOriginError

두 가지 경우 시간 초과가 발생할 수 있습니다.

* 첫 번째 시도에서 작업이 실행됩니다. 이 경우 실행이 완료되지 않으므로 기본 오류가 없습니다
* 재시도 시: 이 경우 actionExecOrigError/actionExecOrigErrorCode는 재시도 전에 시도에 발생한 오류를 설명합니다.

예를 들어 통합 프로필 서비스에서 데이터를 가져오고 첫 번째 시도에서 HTTP 500 오류가 반환됩니다. 가져오기를 다시 시도하지만 2회 시도 기간이 시간 제한을 초과합니다. 그러면 작업 실행이 시간 초과로 태그가 지정됩니다. 작업 파트는 다음과 같이 표시됩니다.

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

시스템 [!DNL Journey Orchestration]에서 제공한 오류 코드를 쿼리하는 중입니다. 예를 들어 404, 500 등이 될 수 있습니다.

유형: 문자열

## fetchCount

소스 유형에 관계없이 데이터를 가져오는 횟수.

유형: long

## fetchPlatformTotalTime

Adobe Experience Platform에서 데이터를 가져오는 데 걸린 총 시간(밀리초)입니다. 비고: 이 시간은 엔진이 데이터 보강 서비스로 데이터 보강 이벤트를 보내고 응답을 받은 시간부터 계산됩니다.

유형: long

## fetchPlatformCount

Adobe Experience Platform에서 데이터를 가져오는 횟수.

유형: long

## fetchCustomTotalTime

사용자 정의 데이터를 가져오는 데 걸리는 시간(밀리초)입니다. 비고: 이 시간은 엔진이 데이터 보강 서비스로 데이터 보강 이벤트를 보내고 응답을 받은 시간부터 계산됩니다

유형: long

## fetchCustomCount

외부 시스템에서 사용자 정의 데이터를 가져오는 횟수.

유형: long
