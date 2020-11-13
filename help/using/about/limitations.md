---
title: Journey Orchestration 제한
description: Journey Orchestration 제한에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: f45069225b284fe47e2acaccb4aa5d34fe171f35
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# 제한 사항 {#limitations}

다음은 Journey Orchestration 사용과 관련된 제한 사항입니다.

## 일반 작업 제한 사항

* 전송 제한이 없습니다. 
* 오류가 발생한 경우 두 번 재시도가 체계적으로 수행됩니다. 받은 오류 메시지에 따라 재시도 횟수를 조정할 수 없습니다. 
* 내장된 **반응** 이벤트를 사용하면 즉시 사용 가능한 동작에 반응할 수 있습니다(이 [페이지](../building-journeys/reaction-events.md)참조). 사용자 지정 작업을 통해 보낸 메시지에 응답하려면 전용 이벤트를 구성해야 합니다. 
* Adobe Campaign Classic 제품 통합은 없습니다.
 
## 사용자 정의 작업 제한

* 사용자 지정 작업 URL은 동적 매개 변수를 지원하지 않습니다. 
* POST 및 PUT 호출 메서드만 지원됩니다. 
* 쿼리 매개 변수 또는 헤더의 이름은 &quot;.&quot;로 시작할 수 없습니다. 또는 &quot;$&quot;. 
* IP 주소는 허용되지 않습니다. 
* 내부 Adobe 주소(.adobe.) 허용되지 않습니다.
 

## Adobe Campaign 작업 제한

* Adobe Campaign Standard 트랜잭션 메시징은 지정된 인스턴스에 대해 채널에서 최대 시간당 50,000개의 메시지 크기를 갖습니다. Adobe Campaign Standard [제품 설명을 참조하십시오](https://helpx.adobe.com/kr/legal/product-descriptions/campaign-standard.html). 
* The **Segment qualification** activity should not be used in such with Adobe Campaign Standard Transactional Messaging daging dillining due to throughput constraints.
 
## 이벤트 제한 사항

* 고유한 오케스트레이션 ID를 얻으려면 고객 여정을 시작하는 데 사용되는 스트리밍 데이터를 먼저 Journey Orchestration 내에 구성해야 합니다. 이 오케스트레이션 ID는 Adobe Experience Platform에 들어오는 스트리밍 페이로드에 추가해야 합니다.
 

## 데이터 소스 제한 사항

* 고객 여정 내에서 외부 데이터 소스를 활용하여 외부 데이터를 실시간으로 조회할 수 있습니다. 이러한 소스는 REST API를 통해 사용할 수 있어야 하며 JSON을 지원하며 요청 양을 처리할 수 있어야 합니다.