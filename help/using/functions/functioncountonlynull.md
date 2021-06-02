---
product: adobe campaign
title: countOnlyNull
description: 함수 countOnlyNull에 대해 알아봅니다.
feature: 여정
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 27%

---

# countOnlyNull {#countOnlyNull}

목록에서 null 값 수를 계산합니다.

## 카테고리

집계

## 함수 구문

`countOnlyNull(<listAny>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 | listString |
| 목록 | listBoolean |
| 목록 | listInteger |
| 목록 | listDecimal |
| 목록 | listDuration |
| 목록 | listDateTime |
| 목록 | listDateTimeOnly |

## 서명 및 반환된 형식

`countOnlyNull(<listAny>)`

정수를 반환합니다.

## 예제

`count([10,2,10,null])`

1 반환.
