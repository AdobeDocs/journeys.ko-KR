---
product: adobe campaign
solution: Journey Orchestration
title: 진행 단계 이벤트 공통 필드
description: 진행 단계 이벤트 공통 필드
feature: 여정
role: 비즈니스 전문가
level: 중간
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# 여러 단계 이벤트 공통 필드 {#sharing-common-fields}

이 혼합은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

이러한 필드는 [!DNL Journey Orchestration]이(가) Adobe Experience Platform으로 보내는 일반적인 XDM 필드입니다. 여정에서 처리되는 모든 단계에 대해 공통 필드가 전송됩니다. 사용자 정의 작업 및 추가 기능에 더 구체적인 필드가 사용됩니다.

이러한 필드 중 일부는 특정 처리 패턴(작업 실행, 데이터 가져오기 등)에서만 사용할 수 있습니다. 이벤트 크기를 제한하기 위해.

## 입구

사용자가 여정을 입력했는지 여부를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형:boolean

값:참/거짓

## 재입구

사용자가 동일한 인스턴스를 사용하여 여정을 다시 입력했는지 여부를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형:boolean

값:참/거짓

## instanceEnded

인스턴스가 성공적으로 끝났는지 여부를 나타냅니다.

유형:boolean

## eventID

처리 중인 이벤트 ID입니다. 이벤트가 외부 이벤트일 경우 이 값은 eventId입니다. 이벤트가 내부 이벤트일 경우 이 값은 내부 eventId(예: scheduledNotificationReceived, executedAction 등)입니다.

유형:문자열

## nodeID

클라이언트 노드 ID(캔버스에서).

유형:문자열

## stepID

현재 처리 중인 단계의 고유 ID입니다.

유형:문자열

## stepName

현재 처리 중인 단계의 이름입니다.

유형:문자열

## stepType

단계의 유형입니다.

유형:문자열

가능한 값:

* 조건
* 작업
* 예약
* 타이머

## stepStatus

단계 상태, 단계 처리가 완료되었을 때(그리고 단계 이벤트가 실행됨) 단계 상태를 나타냅니다.

유형:문자열

상태는 다음과 같습니다.

* 종료:단계에 전환이 없고 처리가 성공적으로 종료되었습니다.
* 오류:단계 처리에서 오류가 발생했습니다.
* 전환:이 단계는 이벤트가 다른 단계로 전환되기를 기다리는 중입니다.
* 제한:실행 또는 농축하는 동안 발생한 예약 오류로 인해 단계가 실패했습니다.
* 시간 제한:실행 또는 농축하는 동안 발생한 시간 초과 오류로 인해 단계가 실패했습니다.
* instanceTime:인스턴스가 시간 초과에 도달했으므로 단계가 처리를 중지했습니다.

## journeyID

여정 ID입니다.

유형:문자열

## journeyVersionID

여정 버전의 ID입니다. 이 id는 journeyStepEvent의 경우 여정에 대한 ID 참조를 나타냅니다.

유형:문자열

## journeyVersionName

여정 버전의 이름입니다.

유형:문자열

## journeyVersion

여정 버전.

유형:문자열

## instanceID

여정 인스턴스의 내부 ID입니다.

유형:문자열

## externalKey

이벤트에서 추출된 외부 키를 사용하여 처리합니다.

유형:문자열

## parentStepID

인스턴스에서 현재 처리된 단계의 상위의 단계 ID입니다.

유형:문자열

## parentStepName

현재 단계의 상위 단계 이름입니다.

유형:문자열

## parentTransitionID

인스턴스를 처리된 단계로 가져온 전환의 ID입니다.

유형:문자열

## parentTransitionName

인스턴스를 처리된 단계로 가져온 전환의 이름입니다.

유형:문자열

## inTest

이 여정이 테스트 모드인지 여부를 나타냅니다.

유형:boolean

## processingTime

인스턴스 단계 시작에서 처리 종료까지의 총 시간(밀리초)입니다.

유형:long

## instanceType

인스턴스 유형이 일괄 처리이거나 유니어일 경우 인스턴스 유형을 나타냅니다.

유형:문자열

값:일괄/균일

## recurenceIndex

여정이 일괄 처리되고 반복(첫 번째 실행에는 recurenceIndex = 1)인 경우 되풀이 인덱스입니다.

유형:long

## isBatchToUnique

이 단일 인스턴스가 배치 인스턴스에서 트리거되었는지 여부를 나타냅니다.

유형:boolean

## batchExternalKey

일괄 처리 이벤트에 대한 외부 키.

유형:문자열

## batchInstanceID

일괄 처리 인스턴스 ID입니다.

유형:문자열

## batchUniqueBranchID

인스턴스가 일괄 처리 인스턴스에서 트리거된 경우 단일 분기 ID가 생성됩니다.

유형:문자열
