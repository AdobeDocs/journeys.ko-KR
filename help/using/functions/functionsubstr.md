---
product: adobe campaign
title: substr
description: Function substr에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 16%

---

# substr {#substr}

시작 인덱스와 끝 인덱스 사이에 문자열 식의 하위 문자열을 반환합니다. 끝 인덱스가 정의되지 않으면 시작 색인과 끝 사이의 인덱스입니다.

## 카테고리

문자열

## 함수 구문

`substr(<parameters>)`

## 매개 변수

| 매개 변수 | type |
|-------------|----------|
| string | string |
| beginIndex | 정수 |
| endIndex | 정수 |

## 서명 및 반환된 형식

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

문자열을 반환합니다.

## 예

`substr("Hello World",6)`

&quot;World&quot;를 반환합니다.

`substr("Hello World", 0, 5)`

&quot;Hello&quot;를 반환합니다.
