---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Bool 기능에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# toBool {#toBool}

해당 유형에 따라 인수 값을 부울 값으로 변환합니다.

* 문자열:문자열 값이 &quot;true&quot;이면 &quot;true&quot;이고, 그렇지 않으면 false입니다.
* 숫자:숫자 값이 0과 같지 않으면 true, 그렇지 않으면 false

## 범주

전환

## 함수 구문

`toBool(<parameter>)`

## 매개 변수

* 소수
* boolean
* 문자열
* 정수

## 서명 및 반환된 유형

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

부울 값을 반환합니다.

## 예제

`toBool("true")`

`toBool(1)`

true를 반환합니다.

`toBool("this is not a boolean")`

false를 반환합니다.
