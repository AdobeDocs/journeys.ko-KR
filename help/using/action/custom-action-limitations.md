---
title: 사용자 지정 작업 제한
description: 사용자 지정 작업 제한에 대한 자세한 내용
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 사용자 지정 작업 제한 {#concept_lh2_df1_2gb}

다음은 사용자 지정 작업 사용에 대한 몇 가지 제한 사항입니다.

* 캡처 또는 전송 볼륨 버퍼링/평활이 없습니다.
* 오류가 발생할 경우 두 번 재시도가 체계적으로 수행됩니다. 받은 오류 메시지에 따라 재시도 횟수를 조정할 수 없습니다.
* 기본 제공 **[!UICONTROL Reaction]**이벤트를 사용하면 즉시 사용할 수 있는 동작에 반응할 수 있습니다(참조[](../building-journeys/event-activities.md)). 사용자 지정 작업을 통해 전송된 메시지에 응답하려면 전용 이벤트를 구성해야 합니다.
* 사용자 지정 작업 URL은 동적 매개 변수를 지원하지 않습니다.
* POST 및 PUT 호출 메서드만 지원됩니다.
* 쿼리 매개 변수 또는 헤더의 이름은 &quot;.&quot;로 시작할 수 없습니다. 또는 &quot;$&quot;을(를) 참조하십시오.
* IP 주소는 허용되지 않습니다.
* 내부 Adobe 주소(.adobe.) 은 허용되지 않습니다.
