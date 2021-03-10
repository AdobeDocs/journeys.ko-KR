---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: 함수 countOnlyNull에 대해 알아보기
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 24%

---


# countOnlyNull {#countOnlyNull}

목록의 null 값 수를 카운트합니다.

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

## 서명 및 반환된 유형

`countOnlyNull(<listAny>)`

정수를 반환합니다.

## 예제

`count([10,2,10,null])`

1을 반환합니다.
