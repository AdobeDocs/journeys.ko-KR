---
title: getBestSendTime
description: getBestSendTime 함수에 대한 자세한 내용
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

고객에게 이메일을 전달하는 데 가장 적합한 시간을 예측합니다.

이 함수는 플랫폼에서 계산된 점수를 사용합니다. 점수는 과거의 행동을 기반으로 향후 이메일을 클릭하거나 여는 경향을 계산합니다. 점수를 계산하는 알고리즘은 작동하기 위해 일정 양의 데이터가 필요합니다. 따라서 데이터가 충분하지 않으면 기본 시간이 적용됩니다. 자세한 내용은 을 참조하십시오 [](../building-journeys/wait-activity.md).

이 함수를 사용하려면 [네임스페이스가](../event/selecting-the-namespace.md) 필요합니다.

>[!NOTE]
>
>계산을 수행할 데이터가 충분하지 않으면 최고의 전송 시간 점수를 사용할 수 없습니다. 이 경우 게시 시 기본 시간이 적용된다는 메시지가 표시됩니다.

## 카테고리

Adobe Experience Platform

## 함수 구문

`getBestSendTime(<parameters>)`

## 매개 변수

| 매개 변수 | 설명 | 유형 |
|--- |--- |--- |
| 시간 | 현재 시간에서 고려할 시간(최대 :168) 이메일 전송 최적화 | `<integer>` |
| 최적화 유형 | &quot;open&quot; 또는 &quot;click&quot; | `<string>` |
| 기본 시간(시간) 대기 | 예측 전송 시간 점수를 사용할 수 없는 경우 | `<integer>` |

## 서명 및 반환된 유형

`getBestSendTime(<integer>,<string>,<integer>)`

dateTime을 반환합니다.

## 예

getBestSendTime(12,&quot;open&quot;,8)

설명:

이 함수는 다음 12시간 내에 메시지를 보내는 가장 좋은 시간을 반환하여 경로 인스턴스에서 메시지를 열 개개인에 대한 확률을 최적화합니다. 데이터가 부족하여 계산을 수행할 수 없는 경우 반환된 시간은 현재 시간으로부터 8시간 이내입니다.
