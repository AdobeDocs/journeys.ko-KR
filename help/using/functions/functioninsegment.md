---
product: adobe campaign
title: inSegment
description: inSegment 함수에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# inSegment {#inSegment}

개인이 주어진 세그먼트에 속하는지 확인합니다.

>[!NOTE]
>
>최대 100개의 세그먼트를 검색할 수 있습니다.

세그먼트 이름은 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다.

세그먼트는 [Adobe Experience Platform](https://platform.adobe.com/segment/overview). 표현식 편집기는 자동으로 완료된 세그먼트 목록을 제공합니다.

세그먼트에는 다음과 같은 세 가지 상태가 있을 수 있습니다.

* 기존: 엔티티는 세그먼트에 계속 있습니다.
* 실현: 엔티티가 세그먼트를 입력하고 있습니다.
* 종료됨: 엔티티가 세그먼트를 종료 중입니다.

오직 **실현** 및 **기존** 세그먼트 기여도 상태는 세그먼트의 구성원으로 간주됩니다. 세그먼트 평가 방법에 대한 자세한 내용은 [Segmentation Service 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` 은(는) 입력한/기존 상태의 segmentMembership을 가지고 있음을 의미합니다.

`ELSE inSegment('segmentName') == false` 종료한 상태의 segmentMembership이 있음을 의미합니다.

## 카테고리

Adobe Experience Platform

## 함수 구문

`inSegment(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 | 유형 |
|--- |--- |--- |
| 세그먼트 | 세그먼트 이름 | `<string>` |

## 서명 및 반환된 형식

`inSegment(<string>)`

부울을 반환합니다.

## 예

`inSegment("men over 50")`

설명:

함수는 **[!UICONTROL true]** 여정 인스턴스 내의 개인이 &quot;men over 50&quot;이라는 Adobe Experience Platform 세그먼트의 일부인 경우, **[!UICONTROL false]** 그렇지 않은 경우
