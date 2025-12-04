---
product: adobe campaign
title: replace
description: 함수 바꾸기에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 12%

---

# replace {#replace}

대상 문자열과 일치하는 첫 번째 발생 횟수를 기본 문자열의 대체 문자열로 바꿉니다.

교체는 문자열 시작부터 끝까지 진행됩니다. 예를 들어, 문자열 &quot;aaa&quot;에서 &quot;aa&quot;를 &quot;b&quot;로 바꾸면 &quot;ab&quot;가 아닌 &quot;ba&quot;가 생성됩니다.

## 카테고리

문자열

## 함수 구문

`replace(<parameters>)`

## 매개변수

| 매개변수 | 유형 |
|-----------|--------------|
| 기본 | 문자열 |
| 대상 | 문자열(RegExp) |
| 교체 | 문자열 |

## 서명 및 반환된 유형

`replace(<base>,<target>,<replacement>)`

문자열을 반환합니다.

## 예제 1

`replace("Hello World", "l", "x")`

&quot;Hexlo World&quot;를 반환합니다.

## 예제 2 {#example_2}

대상 매개 변수는 RegExp이므로 바꿀 문자열에 따라 일부 문자를 이스케이프해야 할 수 있습니다. 다음은 한 예입니다.

* 평가할 문자열: `|OFFER_A|OFFER_B`
* 프로필 특성 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`에서 제공함
* 바꿀 문자열: `|OFFER_A`
* 문자열을 `''`(으)로 대체함
* `\\`자 앞에 `|`을(를) 추가해야 합니다.

표현식:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

반환된 문자열: `|OFFER_B`

지정된 속성에서 대체할 문자열을 빌드할 수도 있습니다.

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
