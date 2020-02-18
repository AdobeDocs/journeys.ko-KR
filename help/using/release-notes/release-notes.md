---
title: 년 릴리스 정보
description: 릴리스 노트에 대한 자세한 내용
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# 릴리스 정보 {#release-notes}

이 페이지에는 고객 여정 오케스트레이션에 대한 모든 새로운 기능과 향상된 기능이 나열됩니다.
설명서 업데이트를 참조할 수도 [있습니다](../release-notes/documentation-updates.md).

## 1분기 릴리스 - 2019년 2월 {#q1-release---february-2019}

**시간대 관리**

이제 시간대는 경로 수준에서 관리됩니다. 경로 속성에 두 개의 매개 변수가 추가되었습니다.

* 시간대 **드롭다운을** 사용하면 특정 시간대를 선택할 수 있습니다. 기본적으로 브라우저의 표준 시간대가 사용됩니다.

* 프로필 **표준 시간대** 확인란을 사용하여 여정에 들어오는 사람의 경험 플랫폼 프로필 표준 시간대를 사용할 수 있습니다(가능한 경우). 그렇지 않은 경우 드롭다운에 정의된 시간대가 사용됩니다. 이 기능은 네임스페이스가 없는 여정과 호환되지 않습니다.

**상황에 맞는 도움말**

이제 상황에 맞는 도움말 기능을 여러 여정 운영 화면에서 사용할 수 있습니다. 즉, 한 번의 클릭으로 현재 사용 중인 기능에 대한 문서에 직접 액세스할 수 있습니다.

상황에 맞는 도움말을 표시하려면 화면의 오른쪽 위 모서리에 있는 &#39;i&#39; 아이콘을 클릭합니다.

현재 이 기능은 홈, 데이터 소스, 이벤트 및 작업 목록 화면에서 사용할 수 있습니다.

**기타 변경 사항**

* 테스트 모드에서 새 매개 변수를 사용하면 시간 컨테이너를 정의할 수 있습니다.  시간 대기 활동은 지속될 수 있습니다. 이렇게 하면 테스트 결과에 신속하게 액세스할 수 있습니다.

* 이제 테스트 모드에서 경로의 모든 이벤트를 트리거할 수 있습니다.


* 새 매개 변수를 사용하면 시간 컨테이너를 정의할 수 있습니다.  시간 대기 활동은 지속될 수 있습니다. 이렇게 하면 테스트 결과에 신속하게 액세스할 수 있습니다.

* 이제 EMEA에서 Journeys Orchestration을 사용할 수 있습니다.

* 팔레트의 새 아이콘을 사용하여 사용 가능한 항목을 표시하거나 수정할 수 없습니다. sans namespace. par default.

* 캔버스, 정화, 작은 아이콘, qui dit disconnected node.

* 짧은 C 문자 목록

* palette UI, icone de search results

* Pouvoir capper les call a des APIS externs (data sources ou ou ou ou ou action). 마르케 n accepted que 500 calls par seconde, elle pourra meter un clicking a 500 qui evite de surcharger system de loyment ties

* 로그 뒤 테스트 로그 전위 상태 = 오류입니다. 애플리케이션 시스템 요구 사항 Possibilityé de voir code erreur voyé le system. -> 테스트 실행 취소, 시스템 계층, 오류 코드, 오류 응답

* 경로 삭제

* 경로:버전 1 il met is latest

1번 화성에서


## GA 릴리스 - 2019년 12월 {#ga-release---december-2019}

고객 여정 통합 운영

이벤트 또는 데이터 소스에 저장된 컨텍스트 데이터를 활용하여 실시간 통합 활용 사례를 구축할 수 있습니다.

고객 여정 통합 운영을 통해 이벤트, Adobe Experience Platform의 정보 또는 타사 API 서비스의 데이터를 기반으로 한 컨텍스트 기반의 실시간 통합 기능을 사용할 수 있습니다. 이 애플리케이션은 여러 단계로 구성된 흐름에서 소비자의 프로필과 행동을 기반으로 고객에게 적합한 다음 최고의 행동이라고 합니다. 이는 최적의 타이밍뿐만 아니라 Adobe Campaign Standard 트랜잭션 메시징 기능(Adobe Campaign Standard 필요) 또는 타사 시스템의 알림을 통해 고객에게 푸시 알림을 전송하는 등의 작업 유형으로 구성됩니다. 이러한 결정은 규칙과 Sensei 점수를 기반으로 합니다.

[고객 여정 통합 운영에 대한 자세한](../action/working-with-adobe-campaign.md) 내용을 살펴보십시오.

추가 리소스:

* [튜토리얼](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [커뮤니티](https://www.adobe.com/go/journeyorchestrationcommunity)