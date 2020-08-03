---
title: random
description: 임의 함수 학습
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 3%

---


# random {#random}

0과 1 사이의 임의 숫자를 생성합니다.

## 범주

수학

## 함수 구문

`random(<parameters>)`

## 서명 및 반환된 문자

`random()`

소수점을 반환합니다.

## 예

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

설명: 성공 비율에 값이 없거나 null이면 기본값이 적용되고 0에서 1 * 100 사이의 임의 숫자가 됩니다(0에서 100까지의 의미).
