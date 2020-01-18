---
title: 조건부 지침(if, then, else)
description: 조건부 교육에 대한 자세한 내용
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 조건부 지침(if, then, else) {#section_cdz_lsk_w3b}

조건부 지침(if, then, else)은 고급 편집기에서 지원됩니다. 보다 복잡한 표현식을 정의할 수 있습니다. 다음 요소로 구성됩니다.

* **[!UICONTROL if]**:우선 평가할 조건입니다.
* **[!UICONTROL then]**:조건 평가의 결과가 참인 경우에 평가할 식입니다.
* **[!UICONTROL else]**:조건 평가의 결과가 false인 경우에 평가할 식입니다.

>[!NOTE]
>
>모든 표현식에 괄호가 필요합니다.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 을 **부울**&#x200B;값으로 반환해야 합니다.

`<expression2>` 와 `<expression3>` 호환되는 형식은 동일해야 합니다. 지원되는 서명 및 반환된 유형은 다음과 같습니다.

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**사용**

조건부 명령을 사용하면 조건 활동의 수를 줄여 경로 워크플로우를 최적화할 수 있습니다. 예를 들어 동일한 작업 활동 내에서 하나의 조건 표현식만 사용하여 필드 정의에 대해 두 가지 대체 요소를 지정할 수 있습니다.

작업 활동의 예(조건부 명령의 결과로 문자열을 예상하는 필드의 경우):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
