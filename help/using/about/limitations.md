---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration 제한
description: Journey Orchestration 제한에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# 제한 사항 {#limitations}

Journey Orchestration 사용과 관련된 제한 사항은 다음과 같습니다.

## 일반 작업 제한 사항

* 전송 제한이 없습니다. 
* 오류가 발생한 경우 2회 재시도가 체계적으로 수행됩니다. 받은 오류 메시지에 따라 재시도 횟수를 조정할 수 없습니다. 
* 내장된 **Responsive** 이벤트를 사용하면 즉시 실행할 수 있습니다([페이지](../building-journeys/reaction-events.md) 참조). 사용자 지정 작업을 통해 전송된 메시지에 응답하려면 전용 이벤트를 구성해야 합니다. 
* Adobe Campaign Classic 제품 통합 기능이 없습니다.

## 경로 버전 제한: {#journey-versions-limitations}

* v1의 이벤트 활동으로 시작하는 여정은 이후 버전의 이벤트 이외의 것으로 시작할 수 없습니다. **세그먼트 자격 조건** 이벤트로 여정을 시작할 수 없습니다.
* v1의 **세그먼트 자격 조건** 활동으로 시작하는 여정은 항상 추가 버전의 **세그먼트 자격 조건**&#x200B;으로 시작해야 합니다.
* **세그먼트 자격 조건**(첫 번째 노드)에서 선택한 세그먼트 및 네임스페이스는 새 버전에서 변경할 수 없습니다.
* 재진입 규칙은 모든 경로 버전에서 동일해야 합니다.

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

* 고유한 오케스트레이션 ID를 얻으려면 고객 여정을 시작하는 데 사용되는 스트리밍 데이터를 먼저 Journey Orchestration 내에 구성해야 합니다. 이 오케스트레이션 ID는 Adobe Experience Platform에 들어오는 스트리밍 페이로드에 추가해야 합니다.
 

## 데이터 소스 제한 사항

* 고객 여정 내에서 외부 데이터 소스를 활용하여 외부 데이터를 실시간으로 조회할 수 있습니다. 이러한 소스는 REST API를 통해 사용할 수 있어야 하며 JSON을 지원하며 요청 볼륨을 처리할 수 있어야 합니다.