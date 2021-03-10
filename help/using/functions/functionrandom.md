---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 임의 함수 학습
feature: 여정
role: 데이터 엔지니어
level: 경험
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%

---


# random {#random}

0과 1 사이의 난수를 생성합니다.

## 카테고리

수학

## 함수 구문

`random(<parameters>)`

## 서명 및 반환된 유형

`random()`

소수점을 반환합니다.

## 예제

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

설명:성공 비율에 값이 없거나 값이 null이면 기본값이 적용되고 0에서 1 * 100 사이의 임의 숫자가 됩니다(0~100).
