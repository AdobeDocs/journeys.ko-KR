---
product: adobe campaign
title: substr
description: 함수 substr에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 18%
---
# substr {#substr}

시작 색인과 끝 색인 사이에 있는 문자열 식의 하위 문자열을 반환합니다. 끝 색인이 정의되지 않으면 시작 색인과 끝 사이에 있습니다.

## 카테고리

문자열

## 함수 구문

`substr(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-------------|----------|
| 문자열 | 문자열 |
| beginIndex | 정수 |
| endIndex | 정수 |

## 서명 및 반환된 유형

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

문자열을 반환합니다.

## 예

`substr("Hello World",6)`

&quot;World&quot;를 반환합니다.

`substr("Hello World", 0, 5)`

&quot;Hello&quot;를 반환합니다.
