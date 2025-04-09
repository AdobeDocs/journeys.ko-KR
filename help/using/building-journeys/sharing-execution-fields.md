---
product: adobe campaign
title: journeyStep 이벤트 작업 실행 필드
description: journeyStep 이벤트 작업 실행 필드
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# journeyStep 이벤트 작업 실행 필드 {#sharing-execution-fields}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


이 mixin은 journeyStepEvent 및 journeyStepProfileEvent에서 공유됩니다.

단계에 처리할 작업이 있으면 해당 필드가 이벤트 페이로드에 추가됩니다.

## actionID

실행 중인 작업의 ID입니다.

유형: 문자열

## actionName

작업 이름. 설정된 이름이 없으면 stepName이 사용됩니다.

유형: 문자열

## actionType

작업 유형.

유형: 문자열

## actionParameterized

작업이 매개 변수화되는지 여부를 나타냅니다.

유형: 부울

## actionExecutionTime

현재 작업을 실행하는 데 걸린 시간(밀리초)입니다.

유형: long

## actionExecutionError

작업을 호출할 때 발생하는 오류 유형입니다.

유형: 문자열

값:
* http
* 캡핑
* timeout
* 오류

## actionExecutionErrorCode

액션 실행 오류용 코드. 오류에 HTTP 코드와 같은 코드가 있을 경우 표시됩니다.

유형: 문자열

## actionExecutionOriginError

두 가지 경우 시간 초과가 발생할 수 있습니다.

* 첫 번째 시도에서 작업이 실행됩니다. 이 경우 실행이 완료되지 않으므로 기본 오류가 없습니다
* 재시도 시: 이 경우 actionExecOrigError/actionExecOrigErrorCode는 재시도 전에 시도에 발생한 오류를 설명합니다.

예를 들어 이메일이 전송되고 HTTP 500 오류가 첫 번째 시도에서 반환됩니다. 가져오기를 다시 시도하지만 2회 시도 기간이 시간 제한을 초과합니다. 그러면 작업 실행이 시간 초과로 태그가 지정됩니다. 작업 파트는 다음과 같이 표시됩니다.

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

* 기본
* ACS 이메일
* ACS SMS
* ACS 푸시
* 고객
* 엡실론
* ...

유형: 문자열

## 배달 작업 ID

배치 여정의 게재 작업 ID에 대해 설명합니다.

유형: 문자열

## 일괄 게재 ID

배치 여정의 게재 ID에 대해 설명합니다.

유형: 문자열

## fromSegmentTrigger

이는 배치 세그먼트가 대상 여정에서 트리거되는지 여부를 설명합니다.

유형: 부울

## actionSchedulerCount

단계 처리 중 스케줄러 서비스로 전송된 스케줄러 알림 요청 개수입니다.

유형: long
