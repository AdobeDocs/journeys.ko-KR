---
title: journeyStep events 작업 실행 필드
description: journeyStep events 작업 실행 필드
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# journeyStep events 작업 실행 필드 {#sharing-execution-fields}

이 혼합은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

단계에 처리할 작업이 있으면 해당 필드가 이벤트 페이로드에 추가됩니다.

## actionID

실행 중인 작업의 ID입니다.

유형: 문자열

## actionName

작업의 이름입니다. 이름이 설정되지 않은 경우 stepName이 수행됩니다.

유형: 문자열

## actionType

작업의 유형입니다.

유형: 문자열

## actionParameterized

작업이 매개 변수화되었는지 여부를 나타냅니다.

유형: boolean

## actionExecutionTime

현재 작업을 실행하는 데 걸린 시간(밀리초)입니다.

유형: long

## actionExecutionError

작업이 호출될 때 발생하는 오류 유형입니다.

유형: 문자열

값:
* http
* 랩
* 시간 초과
* error

## actionExecutionErrorCode

작업 실행 오류 코드. 오류에 HTTP 코드 등의 코드가 있을 경우 표시됩니다.

유형: 문자열

## actionExecutionOriginError

시간 초과는 다음 두 경우에 발생할 수 있습니다.

* 처음 시도하면 작업이 실행됩니다. 이 경우 실행이 완료되지 않았으므로 기본 오류가 없습니다.
* 재시도에서: 이 경우 actionExecOrigError/actionExecOrigErrorCode는 재시도 전에 발생한 오류에 대해 설명합니다.

예를 들어, 이메일이 전송되고 첫 번째 시도에서 HTTP 500 오류가 반환됩니다. 가져오기가 다시 시도되지만 2회 시도 기간이 시간 초과를 초과합니다. 그러면 작업 실행에 타임아웃으로 태그가 지정됩니다. 작업 부분은 다음과 같습니다.

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

* 건물
* ACS 이메일
* ACS SMS
* ACS 푸시
* 고객
* Epsilon
* ...

유형: 문자열

## deliveryJobID

배치 경로의 배달 작업 ID에 대해 설명합니다.

유형: 문자열

## batchDeliveryID

배치 경로의 배달 ID에 대해 설명합니다.

유형: 문자열

## fromSegmentTrigger

대상 세그먼트에서 배치 여정이 트리거되었는지 설명합니다.

유형: boolean

## actionSchedulerCount

단계 처리 중 스케줄러 서비스로 전송된 스케줄러 알림 요청 수입니다.

유형: long
