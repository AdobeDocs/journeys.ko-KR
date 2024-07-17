---
product: adobe campaign
title: 필드 참조
description: 고급 표현식의 필드 참조에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 2%

---

# 필드 참조 {#concept_fkj_ll5_dgb}

필드 참조는 이벤트 또는 필드 그룹에 첨부할 수 있습니다. 유일한 의미 있는 정보는 필드의 이름과 경로입니다.

필드에 특수 문자를 사용하는 경우 큰따옴표나 간단한 따옴표를 사용해야 합니다. 견적이 필요한 경우는 다음과 같습니다.

* 필드는 숫자로 시작합니다.
* 필드는 &quot;-&quot; 문자로 시작합니다.
* 필드에 _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_ 이외의 항목이 포함되어 있습니다.

예를들어 필드가 _3h_&#x200B;인 경우 _#{OpenWeather.weatherData.rain&#39;.3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

식에서 이벤트 필드는 &quot;@&quot;에서 참조되고 데이터 소스 필드는 &quot;#&quot;에서 참조됩니다.

구문 색상은 이벤트 필드(녹색)와 필드 그룹(파란색)을 시각적으로 구별하는 데 사용됩니다.

## 필드 참조의 기본값 {#default-value}

기본값은 필드 이름과 연결할 수 있습니다. 구문은 다음과 같습니다.

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>필드 유형과 기본값은 동일해야 합니다. 예: @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2}은(는) 기본값이 정수이지만 예상 값은 문자열이어야 하므로 잘못되었습니다.

예:

```json
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

모든 종류의 표현식을 기본값으로 추가할 수 있습니다. 유일한 제약 조건은 식이 예상 데이터 형식을 반환해야 한다는 것입니다. 함수를 사용할 때 ()로 함수를 캡슐화해야 합니다.

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## 컬렉션 내의 필드 참조

컬렉션 내에 정의된 요소는 특정 함수 `all`, `first` 및 `last`을(를) 사용하여 참조됩니다. 자세한 정보는 [이 페이지](../expression/collection-management-functions.md)를 참조하십시오.

예 :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 맵에 정의된 필드 참조

### `entry` 함수

맵에서 요소를 검색하기 위해 주어진 키와 함께 entry 함수를 사용한다. 예를 들어 선택한 네임스페이스에 따라 이벤트의 키를 정의할 때 사용됩니다. 네임스페이스 선택을 참조하십시오. 자세한 내용은 [이 페이지](../event/selecting-the-namespace.md)를 참조하세요.

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

이 표현식에서 이벤트의 &#39;IdentityMap&#39; 필드의 &#39;이메일&#39; 키 항목을 가져옵니다. &#39;Email&#39; 항목은 컬렉션이며, 여기에서 &#39;first()&#39;를 사용하여 첫 번째 요소의 &#39;id&#39;를 가져옵니다. 자세한 내용은 [이 페이지](../expression/collection-management-functions.md)를 참조하세요.

### `firstEntryKey` 함수

맵의 첫 번째 시작 키를 검색하려면 `firstEntryKey` 함수를 사용하십시오.

다음 예에서는 특정 목록의 구독자에 대한 첫 번째 이메일 주소를 검색하는 방법을 보여 줍니다.

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

이 예제에서 구독 목록의 이름은 `daily-email`입니다. 이메일 주소는 `subscribers` 맵에서 구독 목록 맵에 연결된 키로 정의됩니다.

### `keys` 함수

맵의 모든 키로 검색하려면 `keys` 함수를 사용하십시오.

다음 예에서는 특정 프로필에 대해 특정 목록의 구독자와 연결된 모든 이메일 주소를 검색하는 방법을 보여 줍니다.

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 데이터 소스의 매개 변수 값(데이터 소스 동적 값)

매개 변수를 호출해야 하는 외부 데이터 소스에서 필드를 선택하는 경우 이 매개 변수를 지정할 수 있도록 오른쪽에 새 탭이 나타납니다. [이 페이지](../expression/expressionadvanced.md)를 참조하십시오.

보다 복잡한 사용 사례에서는 기본 식에 데이터 원본의 매개 변수를 포함하려는 경우 키워드 _params_&#x200B;을 사용하여 해당 값을 정의할 수 있습니다. 매개 변수는 다른 매개 변수를 포함하는 다른 데이터 소스에서도 유효한 표현식이 될 수 있습니다.

>[!NOTE]
>
>표현식에서 매개 변수 값을 정의하면 오른쪽에 있는 탭이 사라집니다.

다음 구문을 사용합니다.

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: 데이터 원본의 첫 번째 매개 변수의 정확한 이름.
* **`<params-1-value>`**: 첫 번째 매개 변수의 값입니다. 모든 유효한 표현식일 수 있습니다.

예:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
