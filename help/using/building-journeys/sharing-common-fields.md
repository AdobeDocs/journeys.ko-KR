---
product: adobe campaign
title: journeysteps 이벤트 공통 필드
description: journeysteps 이벤트 공통 필드
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# journeysteps 이벤트 공통 필드 {#sharing-common-fields}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


이 mixin은 journeyStepEvent 및 journeyStepProfileEvent에서 공유됩니다.

[!DNL Journey Orchestration]이(가) Adobe Experience Platform으로 보내는 일반적인 XDM 필드입니다. 여정에서 처리되는 모든 단계에 대해 공통 필드가 전송됩니다. 사용자 지정 작업 및 보강에는 더 구체적인 필드가 사용됩니다.

이러한 필드 중 일부는 이벤트 크기를 제한하기 위해 특정 처리 패턴(작업 실행, 데이터 가져오기 등)에서만 사용할 수 있습니다.

## 입구

사용자가 여정을 입력했는지 여부를 나타냅니다. 만약 존재하지 않는다면, 우리는 값이 false라고 가정한다.

유형: 부울

값: true/false

## 재진입

사용자가 동일한 인스턴스로 여정을 다시 입력했는지 여부를 나타냅니다. 만약 존재하지 않는다면, 우리는 값이 false라고 가정한다.

유형: 부울

값: true/false

## instanceEnd

인스턴스가 종료되었는지 여부를 나타냅니다.

유형: 부울

## eventID

처리 중인 이벤트 ID입니다(단계 처리 중). 이벤트가 외부 이벤트인 경우 값은 해당 eventId입니다. 이벤트가 내부 이벤트인 경우 값은 내부 eventId(예: scheduledNotificationReceived, executedAction 등)입니다.

유형: 문자열

## nodeID

클라이언트 노드 ID(캔버스에서).

유형: 문자열

## stepID

현재 처리 중인 단계에 대한 고유 ID.

유형: 문자열

## stepName

현재 처리 중인 단계의 이름입니다.

유형: 문자열

## stepType

단계 유형.

유형: 문자열

가능한 값:

* 조건
* 작업
* 스케줄러
* 타이머

## stepStatus

단계가 처리되었으며(및 단계 이벤트가 실행됨) 단계 상태를 나타내는 단계 상태.

유형: 문자열

상태는 다음과 같을 수 있습니다.

* 종료: 단계에 전환이 없으며 처리가 정상적으로 종료되었습니다.
* error: 단계 처리에서 오류가 발생했습니다.
* 전환: 단계가 이벤트가 다른 단계로 전환되기를 기다리고 있습니다.
* 제한됨: 작업 또는 데이터 보강 중에 발생한 최대 가용량 오류에서 단계가 실패했습니다.
* 시간 초과: 작업 또는 데이터 보강 중에 발생한 시간 초과 오류로 인해 단계가 실패했습니다.
* instanceTimedout: 인스턴스가 시간 제한에 도달했기 때문에 단계가 처리를 중지했습니다.

## journeyID

여정 ID.

유형: 문자열

## 여정 버전 ID

여정 버전 ID. 이 ID는 journeyStepEvent의 경우 여정에 대한 ID 참조를 나타냅니다.

유형: 문자열

## 여정 버전 이름

여정 버전 이름.

유형: 문자열

## journeyVersion

여정 버전.

유형: 문자열

## instanceID

여정 인스턴스의 내부 ID.

유형: 문자열

## externalKey

처리할 이벤트에서 외부 키가 추출되었습니다.

유형: 문자열

## 상위 단계 ID

인스턴스에서 현재 처리된 단계의 상위 단계 ID.

유형: 문자열

## parentStepName

현재 단계 상위의 단계 이름입니다.

유형: 문자열

## parentTransitionID

인스턴스를 처리된 단계로 가져온 전환의 ID입니다.

유형: 문자열

## parentTransitionName

인스턴스를 처리된 단계로 가져온 전환의 이름입니다.

유형: 문자열

## inTest

이 여정이 테스트 모드인지 여부를 나타냅니다.

유형: 부울

## processingTime

인스턴스 단계 시작부터 처리 종료까지의 총 시간(밀리초).

유형: long

## instanceType

인스턴스 유형이 일괄 처리이거나 단일 인스턴스인 경우 이를 나타냅니다.

유형: 문자열

값: 배치/단일

## recurrenceIndex

여정이 일괄 처리이고 반복인 경우 반복의 색인입니다(첫 번째 실행에는 recurrenceIndex = 1).

유형: long

## isBatchToUnitary

이 단일 인스턴스가 일괄 처리 인스턴스에서 트리거되었는지 여부를 나타냅니다.

유형: 부울

## batchExternalKey

일괄 처리 이벤트에 대한 외부 키.

유형: 문자열

## 일괄 처리 인스턴스 ID

배치 인스턴스 ID입니다.

유형: 문자열

## batchUnitaryBranchID

인스턴스가 배치 인스턴스에서 트리거된 경우 단일 분기 ID입니다.

유형: 문자열
