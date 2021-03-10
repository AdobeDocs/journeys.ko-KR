---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: inSegment 함수에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---


# inSegment {#inSegment}

개인이 지정된 세그먼트에 속해 있는지 확인합니다.

세그먼트 이름은 문자열 상수여야 합니다. 필드 참조나 표현식이 될 수 없습니다.

세그먼트는 [Adobe Experience Platform](https://platform.adobe.com/segment/overview)에 정의됩니다. 표현식 편집기는 자동으로 완료된 세그먼트 목록을 제공합니다.

>[!NOTE]
>
>최대 100개의 세그먼트를 검색할 수 있습니다.

## 카테고리

Adobe Experience Platform

## 함수 구문

`inSegment(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 | 유형 |
|--- |--- |--- |
| 세그먼트 | 세그먼트 이름 | `<string>` |

## 서명 및 반환된 유형

`inSegment(<string>)`

부울 값을 반환합니다.

## 예제

`inSegment("men over 50")`

설명:

여정 인스턴스 내의 개인이 &quot;men over 50&quot;이라는 Adobe Experience Platform 세그먼트의 일부인 경우 이 함수는 **[!UICONTROL true]**&#x200B;을 반환하고, 그렇지 않은 경우 **[!UICONTROL false]**&#x200B;을 반환합니다.
