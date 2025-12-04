---
product: adobe campaign
title: inSegment
description: inSegment 함수에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 6%

---

# inSegment {#inSegment}

개인이 주어진 세그먼트에 속하는지 확인합니다.

>[!NOTE]
>
>최대 100개의 세그먼트를 검색할 수 있습니다.

세그먼트 이름은 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다.

세그먼트는 [Adobe Experience Platform](https://platform.adobe.com/segment/overview)에 정의되어 있습니다. 표현식 편집기는 자동으로 완성된 세그먼트 목록을 제공합니다.

세그먼트는 세 가지 상태를 가질 수 있습니다.

* 기존: 엔티티가 계속 세그먼트에 있습니다.
* 인식됨: 엔티티가 세그먼트를 입력 중입니다.
* 종료됨: 엔티티가 세그먼트를 종료 중입니다.

**실현됨** 및 **기존** 세그먼트 참여 상태가 있는 개인만 세그먼트의 구성원으로 간주됩니다. 세그먼트를 평가하는 방법에 대한 자세한 내용은 [세그먼테이션 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ko#interpret-segment-results)를 참조하세요.

`IF inSegment('segmentName') == true`은(는) 입력한/기존 상태의 segmentMembership이 있음을 의미합니다.

`ELSE inSegment('segmentName') == false`은(는) 종료한 상태의 segmentMembership이 있음을 의미합니다.

## 카테고리

Adobe Experience Platform

## 함수 구문

`inSegment(<parameter>)`

## 매개변수

| 매개변수 | 설명 | 유형 |
|--- |--- |--- |
| 세그먼트 | 세그먼트 이름 | `<string>` |

## 서명 및 반환된 유형

`inSegment(<string>)`

부울 반환.

## 예

`inSegment("men over 50")`

설명:

함수는 여정 인스턴스 내의 개인이 &quot;50세 이상 남성&quot;이라는 Adobe Experience Platform 세그먼트에 속하는 경우 **[!UICONTROL true]**&#x200B;을(를) 반환하고 그렇지 않으면 **[!UICONTROL false]**&#x200B;을(를) 반환합니다.
