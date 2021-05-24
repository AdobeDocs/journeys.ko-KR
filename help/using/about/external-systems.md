---
product: adobe campaign
solution: Journey Orchestration
title: 외부 시스템과 통합
description: 외부 시스템을 통합할 때 모범 사례에 대해 배웁니다.
feature: 여정
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# 외부 시스템과 통합 {#external-systems}

이 페이지에서는 외부 시스템을 통합할 때 Journey Orchestration이 제공하는 다양한 보호 기능과 우수 사례를 보여 줍니다.최대 가용량 API를 사용하여 외부 시스템의 보호를 최적화하는 방법, 여정 시간 제한을 구성하는 방법 및 다시 시도 작동 방법을 설명합니다.

Journey Orchestration을 사용하면 사용자 지정 데이터 소스 및 사용자 지정 작업을 통해 외부 시스템에 대한 연결을 구성할 수 있습니다. 예를 들어 외부 예약 시스템에서 가져온 데이터로 여정을 보강하거나 Epsilon 또는 Facebook과 같은 타사 시스템을 사용하여 메시지를 전송할 수 있습니다.

외부 시스템을 통합할 때 몇 가지 문제가 발생할 수 있고, 시스템이 느리거나, 응답을 중단할 수 있거나, 큰 볼륨을 처리하지 못할 수 있습니다. Journey Orchestration은 시스템이 오버로드되지 않도록 보호하기 위해 몇 가지 보안 기능을 제공합니다.

모든 외부 시스템은 성능 면에서 다릅니다. 각 사용 사례에 맞게 구성을 조정해야 합니다.

Journey Orchestration이 외부 API에 대한 호출을 실행하면 다음과 같이 기술 보호 기능이 실행됩니다.

1. 최대 가용량:최대 가용량 규칙 적용
2. 시간 제한 및 다시 시도:

## 최대 가용량

기본 제공 Capping API는 외부 시스템을 보호하는 데 도움이 되는 업스트림 기술 보호 기능을 제공합니다. 미리 외부 API의 용량을 평가해야 합니다. 예를 들어, Journey Orchestration이 초당 1000개의 호출을 전송하고 시스템이 초당 100개의 호출만 지원할 수 있는 경우 시스템이 포화되지 않도록 최대 가용량 규칙을 정의해야 합니다.

최대 가용량 규칙은 특정 끝점에 대한 샌드독스 수준에서 정의됩니다(URL이 호출됨). 런타임 시 Journey Orchestration은 캡핑 규칙이 정의되어 있는지 확인하고 호출 중에 정의된 비율을 해당 종단점에 적용합니다. 호출 수가 정의된 속도를 초과하는 경우 나머지 호출은 무시됩니다.

최대 가용량 규칙은 한 개의 종단점에 특정하지만 샌드박스의 모든 여정에 적용됩니다. 즉, 호출 슬롯은 샌드박스의 모든 여정 간에 공유됩니다. 예를 들어 외부 시스템에 초당 100번의 호출로 정의된 최대 캡션이 있고 10개의 다른 여정에 있는 사용자 지정 작업에 의해 호출된다고 가정해 보겠습니다. 한 여정이 초당 200개의 호출을 받으면 100개의 슬롯을 사용할 수 있도록 유지하고 나머지 100개의 슬롯을 삭제합니다. 최대 속도가 이미 초과되었으므로 다른 9개의 여정에 사용 가능한 슬롯이 없습니다. 이러한 세부기간을 통해 외부 시스템을 오버로드 및 충돌으로부터 보호할 수 있습니다.

최대 가용량 제한으로 인해 삭제된 호출은 보고에서 오류로 카운트됩니다.

최대 가용량 규칙을 구성하는 방법에 대한 자세한 내용은 [이 페이지](../api/timezone-management.md)를 참조하십시오.

## 시간 초과 및 다시 시도

Ensuite -> timeout defini, et qui definir le maximal&#39;qu&#39;on aloue a lapl au sys externe. 펜던트 ce temps là, on essaie de faure des apels. 빠르게 종료되면, voit에서 si를 초과하는 긴 임시적 시간 초과 ca marche가 추가되면 une timeout error가 발생할 수 있으며, conté reporting commone reur를 참조하십시오. si&#39;appel echoe, (plantter sur 500 ou aughter), 다시 시도하십시오. 최대 3회 다시 시도, 구성할 수 있습니다. SI가 시간 초과 글로벌(par exemumes 2 essais, mais depse le timeout) 제한 시간을 초과할 수 있습니다. 판수 드 탕트 쿠크는 필요한 것이다. 모든 오 다시 시도를 다시 시도하는 동안 시간 초과 기간 최대 쿠가 표시됩니다.

