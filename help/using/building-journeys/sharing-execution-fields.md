---
product: adobe campaign
title: journeyStep 이벤트 작업 실행 필드
description: journeyStep 이벤트 작업 실행 필드
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 12%

---

# journeyStep 이벤트 작업 실행 필드 {#sharing-execution-fields}

이 mixin은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

단계에 처리할 작업이 있으면 해당 필드가 이벤트 페이로드에 추가됩니다.

## actionID

실행 중인 작업의 ID입니다.

유형: 문자열

## actionName

작업의 이름입니다. 설정된 이름이 없으면 stepName이 사용됩니다.

유형: 문자열

## actionType

작업의 유형입니다.

유형: 문자열

## actionParameterized

작업이 매개 변수화되는지 여부를 나타냅니다.

유형: 부울

## actionExecutionTime

현재 작업을 실행하는 데 걸린 시간(밀리초)입니다.

유형: 장기간

## actionExecutionError

작업이 호출될 때 발생하는 오류 유형입니다.

유형: 문자열

값:
* http
* 최대 가용량
* timeout
* 라는 오류가 표시됩니다

## actionExecutionErrorCode

작업 실행 오류에 대한 코드입니다. 오류에 HTTP 코드와 같은 코드가 있을 경우 표시됩니다.

유형: 문자열

## actionExecutionOriginError

시간 초과는 다음 두 가지 경우에 발생할 수 있습니다.

* 첫 번째 시도에서는 작업이 실행됩니다. 이 경우 실행이 완료되지 않았으므로 기본 오류가 없습니다
* 다시 시도 시: 이 경우 actionExecOrigError/actionExecOrigErrorCode는 재시도 전에 발생한 오류에 대해 설명합니다.

예를 들어 이메일이 전송되고 첫 번째 시도에서 HTTP 500 오류가 반환됩니다. 가져오기가 다시 시도되지만, 두 번의 시도 기간이 시간 제한을 초과합니다. 그런 다음 작업 실행에 시간 제한으로 태그가 지정됩니다. 작업 부분은 다음과 같습니다.

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

유형: 문자열

## actionExecutionOriginCode

actionExecOrigError의 오류 코드입니다.

유형: 문자열

## actionBusinessType

작업 유형을 나타냅니다.

값:

* 빌딩
* ACS 이메일
* ACS SMS
* ACS 푸시
* 고객
* Epsilon
* ...

유형: 문자열

## deliveryJobID

이 섹션에서는 배치 여정에 대한 게재 작업 ID에 대해 설명합니다.

유형: 문자열

## batchDeliveryID

이 섹션에서는 배치 여정에 대한 게재 ID에 대해 설명합니다.

유형: 문자열

## fromSegmentTrigger

대상 세그먼트에서 배치 여정이 트리거되는지 여부를 설명합니다.

유형: 부울

## actionSchedulerCount

단계 처리 중 스케줄러 서비스로 전송된 스케줄러 알림 요청 개수입니다.

유형: 장기간
