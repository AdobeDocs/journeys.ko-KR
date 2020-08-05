---
title: inSegment
description: inSegment 기능에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 6%

---


# inSegment {#inSegment}

개인이 지정된 세그먼트에 속해 있는지 확인합니다.

세그먼트 이름은 문자열 상수여야 합니다. 필드 참조나 식이 될 수 없습니다.

세그먼트는 [Adobe Experience Platform에 정의됩니다](https://platform.adobe.com/segment/overview). 표현식 편집기는 자동으로 완료된 세그먼트 목록을 제공합니다.

>[!NOTE]
>
>최대 100개의 세그먼트를 검색할 수 있습니다.

## 범주

Adobe Experience Platform

## 함수 구문

`inSegment(<parameter>)`

## 매개 변수

| 매개 변수 | 설명 | 유형 |
|--- |--- |--- |
| 세그먼트 | 세그먼트 이름 | `<string>` |

## 서명 및 반환된 문자

`inSegment(<string>)`

부울을 반환합니다.

## 예제

`inSegment("men over 50")`

설명:

경로 인스턴스 내의 개인이 &quot;men over 50&quot;이라는 Adobe Experience Platform 세그먼트의 일부인 경우 이 함수는 **[!UICONTROL true]** **[!UICONTROL false]** 반환됩니다.
