---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration 제한
description: Journey Orchestration 제한에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: a0b6f54e37abded690dc200bc3a901a8e0f04f79
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---


# 제한 사항 {#limitations}

Journey Orchestration 사용과 관련된 제한 사항은 다음과 같습니다.

## 일반 작업 제한 사항

* 전송 제한이 없습니다. 
* 오류가 발생한 경우 2회 재시도가 체계적으로 수행됩니다. 받은 오류 메시지에 따라 재시도 횟수를 조정할 수 없습니다. 
* 내장된 **Responsive** 이벤트를 사용하면 즉시 실행할 수 있습니다([페이지](../building-journeys/reaction-events.md) 참조). 사용자 지정 작업을 통해 전송된 메시지에 응답하려면 전용 이벤트를 구성해야 합니다. 
* Adobe Campaign Classic 제품 통합 기능이 없습니다.

## 여정 버전 제한 사항 {#journey-versions-limitations}

* v1에서 이벤트 활동으로 시작하는 여정은 이후 버전의 이벤트 이외의 다른 항목으로 시작할 수 없습니다. **세그먼트 자격 조건** 이벤트로 여정을 시작할 수 없습니다.
* v1의 **세그먼트 자격 조건** 활동으로 시작하는 여정은 항상 추가 버전의 **세그먼트 자격 조건**&#x200B;으로 시작해야 합니다.
* **세그먼트 자격 조건**(첫 번째 노드)에서 선택한 세그먼트 및 네임스페이스는 새 버전에서 변경할 수 없습니다.
* 재입장 규칙은 모든 여정 버전에서 동일해야 합니다.

## 세그먼트 자격 조건 {#segment-qualification}

* 처리량 제약 문제로 인해 **세그먼트 자격 조건** 활동을 Adobe Campaign Standard 트랜잭션 메시지와 함께 사용할 수 없습니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html)을 참조하십시오. 
 

## 사용자 정의 작업 제한 사항

* 사용자 지정 작업 URL은 동적 매개 변수를 지원하지 않습니다. 
* POST 및 PUT 호출 메서드만 지원됩니다. 
* 쿼리 매개 변수 또는 헤더의 이름은 &quot;.&quot;로 시작할 수 없습니다. 또는 &quot;$&quot;. 
* IP 주소는 허용되지 않습니다. 
* 내부 Adobe 주소(.adobe.) 허용되지 않습니다.
 

## Adobe Campaign 작업 제한 사항

* Adobe Campaign Standard 트랜잭션 메시징에는 지정된 인스턴스에 대해 채널에서 최대 시간당 50,000개의 메시지 범위가 있습니다. [Adobe Campaign Standard 제품 설명](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)을 참조하십시오. 
 

## 이벤트 제한 사항

* 시스템에서 생성된 이벤트의 경우 고유한 오케스트레이션 ID를 얻으려면 먼저 고객 여정 관리 내에 고객 여정을 시작하는 데 사용되는 스트리밍 데이터를 고객 관리 내에 구성해야 합니다. 이 오케스트레이션 ID는 Adobe Experience Platform에 들어오는 스트리밍 페이로드에 추가해야 합니다. 이 제한은 규칙 기반 이벤트에 적용되지 않습니다.
 

## 데이터 소스 제한 사항

* 고객 여정 내에서 외부 데이터 소스를 활용하여 실시간으로 외부 데이터를 조회할 수 있습니다. 이러한 소스는 REST API를 통해 사용할 수 있어야 하며 JSON을 지원하며 요청 볼륨을 처리할 수 있어야 합니다.

## 프로필 만들기 {#journeys-limitation-profile-creation}와 동시에 시작하는 여정

Adobe Experience Platform의 API 기반 프로필 만들기/업데이트와 관련된 지연이 있습니다. 지연에 대한 SLT(서비스 수준 Target)은 요청 백분위수가 95번째 백분위수에 대해 통합 프로파일로 2RPS(초당 20K 요청 수)에서 1분 미만입니다.

여정이 프로필 생성으로 동시에 트리거되고 Profile Service에서 정보를 즉시 확인/검색하는 경우 제대로 작동하지 않을 수 있습니다.

다음 두 솔루션 중 하나를 선택할 수 있습니다.

* 첫 번째 이벤트 이후에 대기 활동을 추가하여 프로필 서비스에 수집이 필요한 시간을 Adobe Experience Platform에 제공합니다.

* 프로파일을 즉시 활용하지 않는 여정을 설정합니다. 예를 들어 여정이 계정 만들기를 확인하도록 설계된 경우 경험 이벤트는 첫 번째 확인 메시지(이름, 성, 이메일 주소 등)를 보내는 데 필요한 정보를 포함할 수 있습니다.