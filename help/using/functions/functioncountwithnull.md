---
product: adobe campaign
title: countWithNull
description: countWithNull 함수에 대해 알아봅니다
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# countWithNull {#countWithNull}

null 값을 포함하여 목록의 모든 요소를 계산합니다.

## 카테고리

집계

## 함수 구문

`countWithNull(<listAny>)`

## 매개 변수

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

`countWithNull(<listAny>)`

정수 반환.

## 예

`countWithNull([10,2,10,null])`

4를 반환합니다.
