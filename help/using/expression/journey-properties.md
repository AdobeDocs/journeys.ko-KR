---
product: adobe campaign
solution: Journey Orchestration
title: 여정 속성
description: 여정 속성에 대해 알아보기
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 4%

---


# 여정 속성 특성 {#journey-properties}

고급 표현식 편집기에서 이벤트 및 데이터 소스 카테고리 아래에 **여정 속성** 카테고리를 찾을 수 있습니다. 이 카테고리는 지정된 프로필의 여정과 관련된 기술 필드를 포함합니다. 여정 ID 또는 발생한 특정 오류와 같은 라이브 여정 시스템에서 검색한 정보입니다.

>[!NOTE]
>
>여정 속성 속성은 간단한 표현식 편집기에서도 사용할 수 있습니다. 이 [섹션](../building-journeys/condition-activity.md#about_condition) 참조

![](../assets/journey-properties.png)

다음과 같은 정보를 찾을 수 있습니다.

* 여정 버전:여정 uid, 여정 버전 uid, 인스턴스 uid 등
* 오류:데이터 가져오기, 작업 실행 등
* 현재 단계, 마지막 현재 단계 등
* 폐기된 프로파일

이러한 필드를 사용하여 표현식을 만들 수 있습니다. 여정을 실행하는 동안 값이 여정에서 직접 검색됩니다.

다음은 사용 사례의 몇 가지 예입니다.

* **폐기된 로그 프로필**:매핑 규칙을 로그하기 위해 제3자 시스템에 전송하여 메시지에서 제외된 모든 프로필을 보낼 수 있습니다. 이와 같이 시간 초과와 오류가 발생하는 경우 경로를 설정하고 특정 오류 유형을 필터링할 조건을 추가합니다.&quot;규칙을 클릭하여 사람 삭제&quot; 그런 다음 사용자 지정 작업을 통해 삭제된 프로파일을 제3자 시스템으로 푸시할 수 있습니다.

* **오류 발생 시 경고 보내기**:메시지에 오류가 발생할 때마다 제3자 시스템에 알림을 보낼 수 있습니다. 이 경우 오류가 발생할 경우 경로를 설정하고 조건 및 사용자 지정 작업을 추가합니다. 발생한 오류에 대한 설명과 함께 Slack 채널에 알림을 보낼 수 있습니다.

* **보고의 오류 수정** :오류가 발생한 메시지에 대한 경로를 하나만 갖는 대신 오류 유형별로 조건을 정의할 수 있습니다. 이렇게 하면 보고를 세분화하고 모든 오류 유형 데이터를 볼 수 있습니다.

## {#journey-properties-fields} 필드 목록

| 카테고리 | 필드 이름 | 레이블 | 설명 |
|---|---|---|------------|
| 여정 버전 | journeyUID | 여정 식별자 |  |
|  | journeyVersionUID | 여정 버전 식별자 |  |
|  | journeyVersionName | 여정 버전 이름 |  |
|  | journeyVersionDescription | 여정 버전 설명 |  |
|  | journeyVersion | 여정 버전 |  |
| 여정 인스턴스 | instanceUID | 여정 인스턴스 식별자 | 인스턴스의 ID |
|  | externalKey | 외부 키 | 여정을 트리거하는 개별 식별자 |
|  | organizationId | 조직 식별자 | 브랜드 조직 |
|  | sandboxName | 샌드박스 이름 | 샌드박스의 이름 |
| ID | profileId | 프로필 ID 식별자 | 여정의 프로파일 식별자 |
|  | namespace | 프로필 ID 네임스페이스 | 여정에 있는 프로필의 네임스페이스(예:ECID) |
| 현재 노드 | currentNodeId | 현재 노드 식별자 | 현재 활동의 식별자(노드) |
|  | currentNodeName | 현재 노드 이름 | 현재 활동의 이름(노드) |
| 이전 노드 | previousNodeId | 이전 노드 식별자 | 이전 활동의 식별자(노드) |
|  | previousNodeName | 이전 노드 이름 | 이전 활동의 이름(노드) |
| 오류 | lastNodeUIDInError | 오류가 발생한 마지막 노드 식별자 | 오류가 발생한 최신 활동(노드)의 식별자 |
|  | lastNodeNameInError | 오류가 있는 마지막 노드 이름 | 오류가 발생한 최신 활동(노드)의 이름 |
|  | lastNodeTypeInError | 마지막 노드 유형 오류 | 오류가 발생한 최신 활동(노드)의 오류 유형입니다. 가능한 유형:<ul><li>이벤트:이벤트, 반응, SQ(예:세그먼트 자격 조건)</li><li>흐름 제어:끝, 조건, 대기</li><li>작업:ACS 작업, 점프, 사용자 지정 작업</li></ul> |
|  | lastErrorCode | 마지막 오류 코드 | 오류가 발생한 최신 활동(노드)의 오류 코드입니다. 가능한 오류: <ul><li>HTTP 오류 코드</li><li>widget</li><li>timedOut</li><li>error(예:기본값을 설정합니다. 거의 발생하지 않아야 한다.)</li></ul> |
|  | lastExecutedActionErrorCode | 마지막으로 실행된 작업 오류 코드 | 오류가 발생한 최신 작업의 오류 코드 |
|  | lastDataFetchErrorCode | 마지막 데이터 가져오기 오류 코드 | 데이터 소스에서 최근 데이터 가져오기 오류 코드 |
| 시간 | lastActionExecutionElapsedTime | 마지막 작업 실행 경과 시간 | 최신 작업을 실행하는 데 걸린 시간 |
|  | lastDataFetchElapedTime | 마지막 데이터 가져오기 경과 시간 | 데이터 소스에서 가져온 최신 데이터 가져오기 실행 시간 |
