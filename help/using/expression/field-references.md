---
product: adobe campaign
title: 필드 참조
description: 고급 표현식의 필드 참조에 대해 알아봅니다
feature: 여정
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 4%

---

# 필드 참조 {#concept_fkj_ll5_dgb}

필드 참조를 이벤트 또는 필드 그룹에 첨부할 수 있습니다. 유일한 의미 있는 정보는 필드의 이름과 해당 경로입니다.

필드에 특수 문자를 사용하는 경우 큰따옴표나 작은 따옴표를 사용해야 합니다. 다음은 따옴표가 필요한 경우입니다.

* 필드는 숫자 문자로 시작합니다
* 필드는 &quot;-&quot; 문자로 시작합니다
* 필드에는 다음 이외의 다른 항목이 포함되어 있습니다. _a_-_z_, _A_-_Z_, _0_-_9_, _ _-_

예를 들어 필드가 _3h_&#x200B;인 경우: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

식에서 이벤트 필드는 &quot;@&quot;와 함께 참조되고 데이터 소스 필드는 &quot;#&quot;과 함께 참조됩니다.

구문 색상은 이벤트 필드(녹색)와 필드 그룹(파란색)을 시각적으로 구분하는 데 사용됩니다.

**필드 참조의 기본값**

기본값을 필드 이름과 연결할 수 있습니다. 구문은 다음과 같습니다.

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>필드의 유형과 기본값은 같아야 합니다. 예: @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 기본값은 정수이지만 예상 값은 문자열이어야 하므로 2}이(가) 잘못되었습니다.

예

```
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

**컬렉션 내의 필드 참조**

컬렉션 내에 정의된 요소는 첫 번째 및 마지막 모든 특정 함수를 사용하여 참조됩니다. 자세한 정보는 [이 페이지](../expression/collection-management-functions.md)를 참조하십시오.

예 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**맵에 정의된 필드 참조**

맵에서 요소를 검색하려면 지정된 키와 함께 시작 함수를 사용합니다. 예를 들어 선택한 네임스페이스에 따라 이벤트의 키를 정의할 때 사용됩니다. 네임스페이스 선택을 참조하십시오. 자세한 내용은 [이 페이지](../event/selecting-the-namespace.md)를 참조하십시오.

```
@{MyEvent.identityMap.entry('Email').first().id}
```

이 표현식에서는 이벤트의 &#39;IdentityMap&#39; 필드의 &#39;Email&#39; 키에 대한 항목이 제공됩니다. &#39;Email&#39; 항목은 &#39;first()&#39;를 사용하여 첫 번째 요소에서 &#39;id&#39;를 가져오는 컬렉션입니다. 자세한 내용은 [이 페이지](../expression/collection-management-functions.md)를 참조하십시오.

**데이터 소스의 매개 변수 값(데이터 소스 동적 값)**

매개 변수를 호출해야 하는 외부 데이터 소스에서 필드를 선택하는 경우 오른쪽에 이 매개 변수를 지정할 수 있는 새 탭이 나타납니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

보다 복잡한 사용 사례에서는 기본 표현식에 데이터 소스의 매개 변수를 포함하려는 경우 키워드 _params_&#x200B;를 사용하여 해당 값을 정의할 수 있습니다. 매개 변수는 다른 매개 변수도 포함하는 다른 데이터 소스의 모든 유효한 표현식일 수 있습니다.

>[!NOTE]
>
>표현식에서 매개 변수 값을 정의하면 오른쪽의 탭이 사라집니다.

다음 구문을 사용합니다.

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: 데이터 소스에서 첫 번째 매개 변수의 정확한 이름입니다.
* **`<params-1-value>`**: 첫 번째 매개 변수의 값입니다. 유효한 표현식일 수 있습니다.

예:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
