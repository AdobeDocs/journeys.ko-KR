---
product: adobe campaign
title: inSegment
description: inSegment 함수에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 8%

---

# inSegment {#inSegment}

개인이 주어진 세그먼트에 속하는지 확인합니다.

>[!NOTE]
>
>최대 100개의 세그먼트를 검색할 수 있습니다.

세그먼트 이름은 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다.

세그먼트는 [Adobe Experience Platform](https://platform.adobe.com/segment/overview)에 정의됩니다. 표현식 편집기는 자동으로 완료된 세그먼트 목록을 제공합니다.

>[!NOTE]
>
>**실현됨** 및 **기존** 세그먼트 기여도 상태가 있는 개인만 세그먼트의 구성원으로 간주됩니다. 세그먼트를 평가하는 방법에 대한 자세한 내용은 [세분화 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)를 참조하십시오.

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

여정 인스턴스 내의 개인이 &quot;men over 50&quot;(으)로 명명된 Adobe Experience Platform 세그먼트의 일부인 경우 이 함수는 **[!UICONTROL true]**&#x200B;을 반환하고, 그렇지 않으면 **[!UICONTROL false]**&#x200B;을 반환합니다.
