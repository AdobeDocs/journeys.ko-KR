---
product: adobe campaign
title: journeysteps 이벤트 공통 필드
description: journeysteps 이벤트 공통 필드
feature: 여정
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 9%

---

# journeysteps 이벤트 공통 필드 {#sharing-common-fields}

이 mixin은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

이러한 필드는 [!DNL Journey Orchestration]이 Adobe Experience Platform에 보내는 일반적인 XDM 필드입니다. 여정에서 처리되는 모든 단계에 대해 공통 필드가 전송됩니다. 더 구체적인 필드가 사용자 지정 작업 및 데이터 보강 용도로 사용됩니다.

이러한 필드 중 일부는 특정 처리 패턴(작업 실행, 데이터 가져오기 등)에서만 사용할 수 있습니다. 를 사용하여 이벤트 크기를 제한할 수 있습니다.

## 입구

사용자가 여정을 입력했는지 여부를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형: 부울

값: true/false

## 재입구

사용자가 동일한 인스턴스가 있는 여정을 다시 입력했는지 여부를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형: 부울

값: true/false

## instanceEnd

인스턴스가 종료되었는지(성공했는지 여부)를 나타냅니다.

유형: 부울

## eventID

처리 중인 이벤트 ID로서, 단계 처리를 위한 것입니다. 이벤트가 외부 이벤트인 경우 값은 해당 eventId입니다. 이벤트가 내부 이벤트인 경우 값은 내부 eventId(예: scheduledNotificationReceived, executedAction 등)입니다.

유형: 문자열

## nodeID

클라이언트 노드 ID(캔버스에서).

유형: 문자열

## stepID

현재 처리 중인 단계의 고유 ID입니다.

유형: 문자열

## stepName

현재 처리 중인 단계의 이름입니다.

유형: 문자열

## stepType

단계의 유형입니다.

유형: 문자열

가능한 값:

* 조건
* 작업
* 예약
* 타이머

## stepStatus

단계의 처리가 수행된(및 단계 이벤트가 실행된) 단계 상태를 나타내는 단계 상태입니다.

유형: 문자열

상태는 다음과 같습니다.

* 종료: 단계에 전환이 없으며 해당 처리가 성공적으로 종료되었습니다.
* 오류: 단계 처리에서 오류가 발생했습니다.
* 전환: 이 단계는 이벤트가 다른 단계로 전환되기를 기다리는 중입니다.
* 제한: 동작 또는 데이터 보강 중에 발생한 최대 가용량 오류 발생 시 단계가 실패했습니다.
* 시간 제한: 작업이 수행되거나 데이터 보강 중에 발생한 시간 초과 오류로 인해 단계가 실패했습니다.
* instanceTimedout: 인스턴스가 시간 초과에 도달하여 단계가 처리를 중지합니다.

## journeyID

여정 ID입니다.

유형: 문자열

## journeyVersionID

여정 버전의 ID입니다. 이 id는 journeyStepEvent의 경우 여정에 대한 ID 참조를 나타냅니다.

유형: 문자열

## journeyVersionName

여정 버전 이름입니다.

유형: 문자열

## journeyVersion

여정 버전.

유형: 문자열

## instanceID

여정 인스턴스의 내부 ID입니다.

유형: 문자열

## externalKey

이벤트에서 추출된 외부 키로 처리합니다.

유형: 문자열

## parentStepID

인스턴스에서 현재 처리된 단계의 상위 단계 ID입니다.

유형: 문자열

## parentStepName

현재 단계의 상위 단계의 단계 이름입니다.

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

인스턴스 단계 시작에서 처리 종료까지의 총 시간(밀리초)입니다.

유형: 장기간

## instanceType

인스턴스 유형이 일괄 처리이거나 단일 인스턴스인 경우 해당 유형을 나타냅니다.

유형: 문자열

값: 배치/단일

## recursionIndex

여정이 일괄 처리이고 반복(첫 번째 실행에서 recurenceIndex = 1)인 경우 되풀이 인덱스.

유형: 장기간

## isBatchToUnior

일괄 처리 인스턴스에서 이 단일 인스턴스가 트리거되었는지 여부를 나타냅니다.

유형: 부울

## batchExternalKey

일괄 처리 이벤트에 대한 외부 키.

유형: 문자열

## batchInstanceID

배치 인스턴스 ID입니다.

유형: 문자열

## batchUniorBranchID

인스턴스가 배치 인스턴스에서 트리거된 경우 단일 분기 ID입니다.

유형: 문자열
