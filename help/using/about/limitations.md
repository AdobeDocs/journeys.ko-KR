---
product: adobe campaign
title: Journey Orchestration 제한 사항
description: Journey Orchestration 제한 사항에 대해 자세히 알아보기
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 42%

---

# 제한 사항 {#limitations}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._



다음은 Journey Orchestration 사용과 관련된 제한 사항입니다.

## 일반 여정 가드레일 {#journeys-guardrails-journeys}

* 한 여정에 넣을 수 있는 활동 수는 50개로 제한됩니다. 활동 수는 여정 캔버스의 왼쪽 위 섹션에 표시됩니다.
* 한 조직에서 만들 수 있는 **라이브 여정**&#x200B;의 수는 샌드박스당 100개로 제한됩니다. 이 한도에 도달하면 더 이상 새 여정을 게시할 수 없습니다.

## 일반 작업 제한 사항

* 오류가 발생하면 시스템에서 세 번 다시 시도합니다. 수신된 오류 메시지에 따라 재시도 횟수를 조정할 수 없습니다. 
* 기본 제공 **반응** 이벤트를 사용하면 기본 작업에 반응할 수 있습니다([페이지](../building-journeys/reaction-events.md) 참조). 사용자 지정 작업을 통해 전송된 메시지에 반응하려면 전용 이벤트를 구성해야 합니다. 

## 여정 버전 제한 사항 {#journey-versions-limitations}

* v1의 이벤트 활동으로 시작하는 여정은 이후 버전의 이벤트 이외의 다른 것으로 시작할 수 없습니다. **세그먼트 선별** 이벤트로 여정을 시작할 수 없습니다.
* v1에서 **세그먼트 선별** 활동으로 시작하는 여정은 이후 버전에서 항상 **세그먼트 선별**&#x200B;로 시작해야 합니다.
* **세그먼트 자격**(첫 번째 노드)에서 선택한 세그먼트 및 네임스페이스는 새 버전에서 변경할 수 없습니다.
* 재입력 규칙은 모든 여정 버전에서 동일해야 합니다.

## 세그먼트 선별 {#segment-qualification}

* 처리량 제한으로 인해 **세그먼트 자격** 활동을 Adobe Campaign Standard 트랜잭션 메시지와 함께 사용할 수 없습니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)을 참조하세요. 
 

## 사용자 지정 작업 제한 사항

* 사용자 정의 작업 URL은 동적 매개 변수를 지원하지 않습니다.  
* POST 및 PUT 호출 메서드만 지원됩니다. 
* 쿼리 매개 변수 또는 헤더의 이름은 “.” 또는 &quot;$&quot;입니다. 
* IP 주소는 허용되지 않습니다. 
* 내부 Adobe 주소(.adobe.)는 허용되지 않습니다.
 

## Adobe Campaign 작업 제한 사항

* Adobe Campaign Standard 트랜잭션 메시지는 주어진 인스턴스에 대해 채널 전체에서 시간당 최대 50,000개의 메시지 크기가 있습니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)을 참조하세요. 
 

## 이벤트 제한 사항

* 시스템 생성 이벤트의 경우 고유한 오케스트레이션 ID를 얻으려면 먼저 고객 여정을 시작하는 데 사용되는 스트리밍 데이터를 Journey Orchestration 내에서 구성해야 합니다. 이 오케스트레이션 ID는 Adobe Experience Platform으로 들어오는 스트리밍 페이로드에 추가되어야 합니다. 이 제한은 규칙 기반 이벤트에는 적용되지 않습니다.
 

## 데이터 소스 제한 사항

* 고객 여정 내에서 외부 데이터 소스를 활용하여 실시간으로 외부 데이터를 조회할 수 있습니다. 이러한 소스는 REST API를 통해 사용할 수 있어야 하고 JSON을 지원하고 요청 볼륨을 처리할 수 있어야 합니다.

## 프로필 만들기와 동시에 시작하는 여정 {#journeys-limitation-profile-creation}

Adobe Experience Platform에서 API 기반 프로필 만들기/업데이트와 관련된 지연이 발생합니다. 지연 시간 측면에서 SLT(서비스 수준 목표)는 20,000RPS(초당 요청) 볼륨에서 95번째 백분위수 요청에 대해 수집에서 통합 프로필까지 1분 미만입니다.

프로필 만들기와 동시에 여정이 트리거되고 Profile Service에서 정보를 즉시 확인/검색하면 제대로 작동하지 않을 수 있습니다.

다음 두 가지 솔루션 중 하나를 선택할 수 있습니다.

* 첫 번째 이벤트 후에 대기 활동을 추가하여 Adobe Experience Platform에 Profile Service에 대한 수집을 수행하는 데 필요한 시간을 제공합니다.

* 프로필을 즉시 활용하지 않는 여정을 설정합니다. 예를 들어 여정이 계정 만들기를 확인하도록 디자인된 경우 경험 이벤트에는 첫 번째 확인 메시지(이름, 성, 이메일 주소 등)를 보내는 데 필요한 정보가 포함될 수 있습니다.
