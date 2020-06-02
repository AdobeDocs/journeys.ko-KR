---
title: 진행 단계 이벤트 공통 필드
description: 진행 단계 이벤트 공통 필드
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
source-wordcount: '583'
ht-degree: 0%

---


# 진행 단계 이벤트 공통 필드 {#sharing-common-fields}

이 혼합은 journeyStepEvent 및 journeyStepProfileEvent가 공유합니다.

고객 여정 오케스트레이션이 Adobe 데이터 플랫폼으로 전송하는 공통 XDM 필드입니다. 여정에서 처리되는 모든 단계에 대해 공통 필드가 전송됩니다. 사용자 정의 작업 및 개발에 더 구체적인 필드가 사용됩니다.

이러한 필드 중 일부는 특정 처리 패턴(작업 실행, 데이터 가져오기 등)에서만 사용할 수 있습니다. 를 사용하여 이벤트의 크기를 제한합니다.

## 입구

사용자가 여행 경로를 입력했는지 여부를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형: boolean

값: 참/거짓

## 재입구

사용자가 동일한 인스턴스로 여정에 다시 들어왔는지를 나타냅니다. 없으면 값이 false로 간주됩니다.

유형: boolean

값: 참/거짓

## instanceEnded

인스턴스가 성공적으로 끝났는지 여부를 나타냅니다.

유형: boolean

## eventID

처리 중인 이벤트 ID입니다. 이벤트가 외부 이벤트일 경우 값은 eventId입니다. 이벤트가 내부 이벤트일 경우 값은 내부 eventId(예: scheduledNotificationReceived, executedAction 등)입니다.

유형: 문자열

## nodeID

Client node id (from the canvas).

유형: 문자열

## stepID

현재 처리 중인 단계의 고유 ID입니다.

유형: 문자열

## stepName

현재 처리 중인 단계의 이름입니다.

유형: 문자열

## stepType

단계 유형입니다.

유형: 문자열

가능한 값:

* 조건
* 작업
* 예약
* 타이머

## stepStatus

단계 상태, 단계의 처리가 완료된 시간(및 단계 이벤트 실행)을 나타냅니다.

유형: 문자열

상태는 다음과 같습니다.

* 종료: 단계가 전환되지 않고 처리가 성공적으로 종료되었습니다.
* error: 단계 처리에 오류가 발생했습니다.
* 전환: 이 단계는 이벤트가 다른 단계로 전환되기를 기다리는 중입니다.
* mined: 조치 또는 농축에서 발생한 예약 오류로 이 단계가 실패했습니다.
* 시간 제한: 작업 또는 농축하는 동안 발생한 시간 초과 오류로 단계를 수행하지 못했습니다.
* instanceTime: 인스턴스가 시간 제한에 도달하여 단계가 처리를 중지했습니다.

## journeyID

경로의 ID입니다.

유형: 문자열

## journeyVersionID

경로 버전의 ID입니다. 이 id는 journeyStepEvent의 경우 경로의 ID 참조를 나타냅니다.

유형: 문자열

## journeyVersionName

경로 버전의 이름입니다.

유형: 문자열

## journeyVersion

경로 버전의 버전입니다.

유형: 문자열

## instanceID

경로 인스턴스의 내부 ID입니다.

유형: 문자열

## externalKey

이벤트에서 추출된 외부 키를 사용하여 처리합니다.

유형: 문자열

## parentStepID

인스턴스의 현재 처리된 단계 상위의 단계 ID.

유형: 문자열

## parentStepName

현재 단계의 상위 단계 이름입니다.

유형: 문자열

## parentTransitionID

인스턴스를 처리된 단계로 가져온 전환의 ID입니다.

유형: 문자열

## parentTransitionName

인스턴스를 처리된 단계로 가져온 전환의 이름입니다.

유형: 문자열

## inTest

이 여정이 테스트 모드인지 여부를 나타냅니다.

유형: boolean

## processingTime

인스턴스 단계 시작에서 처리 종료까지의 총 시간(밀리초)입니다.

유형: long

## instanceType

인스턴스 유형이 일괄 처리이거나 유니식인 경우 인스턴스 유형을 나타냅니다.

유형: 문자열

값: 일괄/단음

## recurseIndex

진행이 일괄 처리되고 반복되는 경우(첫 번째 실행에는 recurenceIndex = 1)인 반복의 인덱스입니다.

유형: long

## isBatchToUnior

이 단일 인스턴스가 배치 인스턴스에서 트리거되었는지 여부를 나타냅니다.

유형: boolean

## batchExternalKey

배치 이벤트에 대한 외부 키.

유형: 문자열

## batchInstanceID

배치 인스턴스 ID입니다.

유형: 문자열

## batchUnitiveBranchID

인스턴스가 배치 인스턴스에서 트리거된 경우 단일 분기 ID가 반환됩니다.

유형: 문자열
