---
title: 단계 이벤트 필드 목록
description: 단계 이벤트 필드 목록
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 18%

---

# 단계 이벤트 필드 목록 {#sharing-field-list}

단계 이벤트 필드는 카테고리별로 구성됩니다.

* 디버그 정보 필드
* 여정 필드
* 프로필 필드
* 서비스 이벤트 필드

## debugInfo

| 필드 이름 | 유형 | 설명 |
|---|---|------------|
| requestId | 문자열 | Journey Orchestration에서 요청 흐름을 추적하는 데 사용하는 요청 ID입니다. |

## 여정

이 필드 그룹은 journeyStepEvent와 관련하여 여정 스키마에서 사용됩니다. 여기에는 다음 필드가 포함되어 있습니다.

| 필드 이름 | 유형 | 설명 |
|---|---|------------|
| ID | 문자열 | 지정된 여정의 식별자 |
| VersionID | 문자열 | 여정 버전 ID. 이 ID는 여정 ID를 나타냅니다. |
| 이름 | 문자열 | 여정 이름 |
| 설명 | 문자열 | 여정 설명 |
| version | 문자열 | 버전, 다음으로 표시됨 `major`.`minor` |

## 프로필

이 필드 그룹은 journeyStepEvent에만 해당됩니다. 이 이벤트는 여정과 관련되어 있으며 프로필 ID를 설명하는 identityMap이 없습니다(있는 경우).

journeyStepEvent의 경우 ID와 관련된 필드도 추가해야 합니다.

| 필드 이름 | 유형 | 설명 |
|---|---|------------|
| ID | 문자열 | 프로필 식별자는 여정에서 전송/사용되는 프로필을 식별합니다. 예: foo@adobe.com. |
| namespace | 문자열 | 이 필드에서는 여정에 사용된 프로필에서 참조하는 네임스페이스에 대해 설명합니다. 예: 이메일, ECID |

## 서비스 이벤트

이 mixin에는 프로필 내보내기 작업에 해당하는 모든 필드가 포함되어 있습니다.

| 필드 이름 | 유형 | 설명 |
|---|---|------------|
| ID | 문자열 | 트리거된 세그먼트 내보내기 작업의 식별자 |
| 상태 | 문자열 | 세그먼트 내보내기 작업의 상태: 큐에 있음, 시작됨, 완료됨 |
| 내보내기 개수 합계 | 정수 | 세그먼트 내보내기 작업의 가능한 최대 값 |
| exportCountImproved | 정수 | 작업을 통해 내보낸 실제 세그먼트 수 |
| exportCountFailed | 정수 | 작업을 통해 내보내는 동안 실패한 세그먼트 수 |
| exportSegmentId | 문자열 | 내보내는 세그먼트의 식별자 |
| eventType | 문자열 | 정보 이벤트의 오류 이벤트인지 여부를 나타내는 이벤트 유형: 정보, 오류 |
| eventCode | 문자열 | 해당 eventType의 이유를 나타내는 오류 코드 |

## stepEvent

이 카테고리에는 원래 단계 이벤트 필드가 포함되어 있습니다. 이 [섹션](../building-journeys/sharing-legacy-fields.md)을 참조하십시오.
