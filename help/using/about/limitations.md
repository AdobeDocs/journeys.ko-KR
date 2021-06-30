---
product: adobe campaign
title: Journey Orchestration 제한 사항
description: Journey Orchestration 제한에 대해 자세히 알아보기
feature: 여정
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 784c91054e0f6b9ea12aa4b7f4079f7c2da8f949
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 2%

---

# 제한 사항 {#limitations}

다음은 Journey Orchestration 사용과 관련된 제한 사항입니다.

## 일반 작업 제한 사항

* 전송 제한이 없습니다. 
* 오류가 발생한 경우 세 번 다시 시도가 체계적으로 수행됩니다. 받은 오류 메시지에 따라 다시 시도 횟수를 조정할 수 없습니다. 
* 기본 제공 **Reaction** 이벤트를 사용하면 기본 작업에 응답할 수 있습니다( 이 [page](../building-journeys/reaction-events.md) 참조). 사용자 지정 작업을 통해 전송된 메시지에 응답하려면 전용 이벤트를 구성해야 합니다. 

## 여정 버전 제한 사항 {#journey-versions-limitations}

* v1에서 이벤트 활동으로 시작하는 여정은 이후 버전의 이벤트 이외의 항목으로 시작할 수 없습니다. **여정 자격** 이벤트로 세그먼트를 시작할 수 없습니다.
* v1에서 **세그먼트 자격** 활동으로 시작하는 여정은 항상 추가 버전에서 **세그먼트 자격**&#x200B;으로 시작해야 합니다.
* **세그먼트 자격**(첫 번째 노드)에서 선택한 세그먼트와 네임스페이스는 새 버전에서 변경할 수 없습니다.
* 재시작 규칙은 모든 여정 버전에서 동일해야 합니다.

## 세그먼트 자격 {#segment-qualification}

* 처리량 제한으로 인해 **세그먼트 자격** 활동을 Adobe Campaign Standard 트랜잭션 메시지와 함께 사용할 수 없습니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)을 참조하십시오. 
 

## 사용자 지정 작업 제한

* 사용자 지정 작업 URL은 동적 매개 변수를 지원하지 않습니다. 
* POST 및 PUT 호출 메서드만 지원됩니다. 
* 쿼리 매개 변수 또는 헤더의 이름은 &quot;.&quot;로 시작하면 안 됩니다. 또는 &quot;$&quot;. 
* IP 주소는 허용되지 않습니다. 
* 내부 Adobe 주소(.adobe.) 허용되지 않습니다.
 

## Adobe Campaign 작업 제한 사항

* Adobe Campaign Standard 트랜잭션 메시징의 스케일은 주어진 인스턴스에 대해 채널 간에 최대 시간당 50,000개의 메시지 수입니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)을 참조하십시오. 
 

## 이벤트 제한 사항

* 시스템 생성 이벤트의 경우, 고유한 오케스트레이션 ID를 얻으려면 먼저 Journey Orchestration 내에서 고객 여정을 시작하는 데 사용되는 스트리밍 데이터를 구성해야 합니다. 이 오케스트레이션 ID는 Adobe Experience Platform으로 들어오는 스트리밍 페이로드에 추가해야 합니다. 이 제한은 규칙 기반 이벤트에는 적용되지 않습니다.
 

## 데이터 소스 제한 사항

* 고객 여정 내에서 외부 데이터 소스를 활용하여 외부 데이터를 실시간으로 조회할 수 있습니다. 이러한 소스는 REST API를 통해 사용할 수 있어야 하며, JSON을 지원하고, 요청 볼륨을 처리할 수 있어야 합니다.

## 여정 만들기와 동시에 시작 {#journeys-limitation-profile-creation}

Adobe Experience Platform의 API 기반 프로필 만들기/업데이트와 연관된 지연이 있습니다. 지연에 대한 SLT(서비스 수준 Target)은 RPS(초당 20K 요청 수)로 요청의 95번째 백분위수에 대한 통합 프로필에 대해 수집에서 1분 미만입니다.

여정이 프로필 만들기로 동시에 트리거되고 프로필 서비스에서 정보를 즉시 확인/검색하는 경우 제대로 작동하지 않을 수 있습니다.

다음 두 솔루션 중 하나를 선택할 수 있습니다.

* 첫 번째 이벤트 다음에 대기 활동을 추가하여 Adobe Experience Platform에 프로필 서비스에 수집을 수행해야 하는 시간을 지정합니다.

* 프로필을 즉시 활용하지 않는 여정을 설정합니다. 예를 들어 여정이 계정 만들기를 확인하도록 디자인된 경우 경험 이벤트에는 첫 번째 확인 메시지(이름, 성, 이메일 주소 등)를 전송하는 데 필요한 정보가 포함될 수 있습니다.
