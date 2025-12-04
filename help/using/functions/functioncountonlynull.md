---
product: adobe campaign
title: countOnlyNull
description: countOnlyNull 함수에 대해 알아봅니다
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# countOnlyNull {#countOnlyNull}

목록의 null 값 수를 계산합니다.

## 카테고리

집계

## 함수 구문

`countOnlyNull(<listAny>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | list부울 |
| 목록 | list정수 |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |
| 목록 | listDateOnly |

## 서명 및 반환된 유형

`countOnlyNull(<listAny>)`

정수 반환.

## 예

`countOnlyNull([10,2,10,null])`

1을 반환합니다.
