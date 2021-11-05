---
product: adobe campaign
title: 조건부 지침(if, then, else)
description: 조건부 지침에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# 조건부 지침(if, then, else) {#section_cdz_lsk_w3b}

조건부 지침(if, then, else)은 고급 편집기에서 지원됩니다. 이를 통해 더 복잡한 표현식을 정의할 수 있습니다. 다음 요소로 구성됩니다.

* **[!UICONTROL if]**: 먼저 평가될 조건입니다.
* **[!UICONTROL then]**: 조건 평가의 결과가 true일 경우에 평가할 식입니다.
* **[!UICONTROL else]**: 조건 평가 결과가 false인 경우 평가할 식입니다.

>[!NOTE]
>
>모든 표현식에서 괄호가 필요합니다.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 를 반환해야 합니다. **부울**.

`<expression2>` 및 `<expression3>` 형식 또는 호환 형식이 같아야 합니다. 지원되는 서명 및 반환된 유형은 다음과 같습니다.

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**사용**

조건부 명령을 사용하면 조건 활동 수를 줄여 여정 워크플로우를 최적화할 수 있습니다. 예를 들어 동일한 작업 활동 내에서 하나의 조건 표현식만 사용하여 필드 정의에 두 개의 대체 요소를 지정할 수 있습니다.

작업 활동의 예(조건부 명령의 결과로 문자열이 필요한 필드):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
