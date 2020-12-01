---
product: adobe campaign
solution: Journey Orchestration
title: 여정 속성
description: 고객 여정 속성에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: b989e167c4aa5d8ef2667442231ff8857c5f0b18
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# 경로 속성 {#journey-properties}

고급 표현식 편집기에서 **경로 속성** 카테고리가 이벤트 및 데이터 소스 카테고리 아래에 있습니다. 이 카테고리는 지정된 프로필의 여정과 관련된 기술 필드를 포함합니다. 이 정보는 방문 ID 또는 발생한 특정 오류와 같이 시스템이 라이브 경로에서 검색한 정보입니다.

![](../assets/journey-properties.png)

다음과 같은 정보를 찾을 수 있습니다.

* 경로:경로 uid, 경로 버전 uid, 인스턴스 uid 등
* 오류:데이터 가져오기, 작업 실행 등
* 현재 단계, 마지막 현재 단계 등
* 폐기된 프로필

이러한 필드를 사용하여 표현식을 만들 수 있습니다. 경로 실행 중에 값이 경로에서 직접 검색됩니다.

다음은 몇 가지 사용 사례입니다.

* **폐기된 로그 프로필**:캡핑 규칙을 로그하기 위해 타사 시스템에 전송하여 메시지에서 제외된 모든 프로필을 보낼 수 있습니다. 이와 같이, 시간 초과와 오류가 발생하는 경우 경로를 설정하고 특정 오류 유형에 대해 필터링하는 조건을 추가합니다.&quot;규칙을 클릭하여 사람 삭제&quot; 그런 다음 사용자 지정 작업을 통해 삭제된 프로필을 타사 시스템으로 푸시할 수 있습니다.

* **오류** 발생 시 푸시 알림 전송:메시지에 오류가 발생할 때마다 타사 시스템에 알림을 보낼 수 있습니다. 이 경우 오류가 발생할 경우 경로를 설정하고 조건 및 사용자 지정 작업을 추가합니다. 발생한 오류에 대한 설명과 함께 Slack 채널에 알림을 전송할 수 있습니다.

* **보고의 오류 수정** :오류 메시지에 대한 경로를 하나만 가지는 대신 오류 유형별로 조건을 정의할 수 있습니다. 이렇게 하면 보고를 세분화하고 모든 오류 유형 데이터를 볼 수 있습니다.

## {#journey-properties-fields} 필드 목록

| 범주 | 필드 이름 | 레이블 | 설명 |
|---|---|---|------------|
| 고객 여정 버전 | journeyUID | 경로 식별자 |  |
|  | journeyVersionUID | 경로 버전 식별자 |  |
|  | journeyVersionName | 경로 버전 이름 |  |
|  | journeyVersionDescription | 경로 버전 설명 |  |
|  | journeyVersion | 고객 여정 버전 |  |
| 경로 인스턴스 | instanceUID | 경로 인스턴스 식별자 | 인스턴스의 ID |
|  | externalKey | 외부 키 | 여정을 트리거하는 개별 식별자 |
| ID | profileId | 프로필 ID 식별자 | 경로 내 프로필의 식별자 |
|  | namespace | 프로필 ID 네임스페이스 | 경로의 네임스페이스(예:ECID) |
| 현재 노드 | currentNodeId | 현재 노드 식별자 | 현재 활동의 식별자(노드) |
|  | currentNodeName | 현재 노드 이름 | 현재 활동의 이름(노드) |
| 이전 노드 | previousNodeId | 이전 노드 식별자 | 이전 활동의 식별자(노드) |
|  | previousNodeName | 이전 노드 이름 | 이전 활동의 이름(노드) |
| 오류 | lastNodeUIDInError | 마지막 노드 식별자(오류) | 오류가 발생한 최신 활동(노드)의 식별자입니다. |
|  | lastNodeNameInError | 마지막 노드 이름 오류 | 오류가 발생한 최신 활동(노드)의 이름 |
|  | lastNodeTypeInError | 마지막 노드 유형 오류 | 오류가 있는 최신 활동(노드)의 오류 유형입니다. 가능한 유형:<ul><li>이벤트:이벤트, 반응, SQ(예:세그먼트 자격 조건)</li><li>흐름 제어:끝, 조건, 대기</li><li>작업:ACS 작업, 이동, 사용자 지정 작업</li></ul> |
|  | lastErrorCode | 마지막 오류 코드 | 오류가 있는 최신 활동(노드)의 오류 코드입니다. 가능한 오류: <ul><li>HTTP 오류 코드</li><li>우</li><li>timedOut</li><li>error(예:기본값이 예기치 않은 오류가 발생한 경우 이 값이 무시됩니다. 극히 드물게 일어나는 일)</li></ul> |
|  | lastExecutedActionErrorCode | 마지막으로 실행된 작업 오류 코드 | 오류가 발생한 최신 작업의 오류 코드 |
|  | lastDataFetchErrorCode | 마지막 데이터 가져오기 오류 코드 | 데이터 소스에서 가져온 최신 데이터 가져오기의 오류 코드 |
| 시간 | lastActionExecutionElapsedTime | 마지막 작업 실행 경과 시간 | 최신 작업을 실행하는 데 걸린 시간 |
|  | lastDataFetchElapsedTime | 마지막 데이터 가져오기 경과 시간 | 데이터 소스에서 가져온 최신 데이터 가져오기 실행 시간 |
