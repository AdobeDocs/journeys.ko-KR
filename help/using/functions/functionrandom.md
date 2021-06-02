---
product: adobe campaign
title: random
description: 임의 함수에 대해 알아보기
feature: 여정
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

---

# random {#random}

0에서 1 사이의 난수를 생성합니다.

## 카테고리

수학

## 함수 구문

`random(<parameters>)`

## 서명 및 반환된 형식

`random()`

소수점 반환

## 예제

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

설명:성공 비율에 값이 없거나 값이 null이면 기본값이 적용되고 0에서 1 * 100 사이의 임의 숫자가 됩니다(0~100 의미).
