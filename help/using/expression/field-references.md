---
title: 필드 참조
description: 고급 표현식의 필드 참조에 대해 알아보기
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
source-git-commit: 61e269bc319407f48006486b96333385ef8b9c58
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---



# 필드 참조 {#concept_fkj_ll5_dgb}

필드 참조를 이벤트 또는 필드 그룹에 연결할 수 있습니다. 유일한 의미 있는 정보는 필드의 이름과 해당 경로입니다.

필드에 특수 문자를 사용하는 경우 큰 따옴표나 간단한 따옴표를 사용해야 합니다. 다음은 따옴표가 필요한 경우입니다.

* 필드가 숫자 문자로 시작됩니다.
* &quot;-&quot; 문자로 시작하는 필드
* 필드에는 다음과 같은 것 이외의 다른 것이 있습니다. _a_-z _,_ a _-_ z _, jecyn_-0-jecyn _____9,, _ ,_

예를 들어 필드가 _3h인 경우_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

식에서 이벤트 필드는 &quot;@&quot;로 참조되고 데이터 소스 필드는 &quot;#&quot;로 참조됩니다.

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
>필드의 유형과 기본값은 동일해야 합니다. 예: @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 기본값은 정수이지만 예상 값은 문자열이어야 하므로 2}이(가) 잘못되었습니다.

**컬렉션 내 필드 참조**

컬렉션 내에서 정의된 요소는 모두, 첫 번째 및 마지막 특정 함수를 사용하여 참조됩니다. 자세한 내용은 을 참조하십시오 [](../expression/collection-management-functions.md).

예제 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**맵에 정의된 필드 참조**

맵에서 요소를 검색하기 위해 주어진 키와 함께 입력 함수를 사용합니다. 예를 들어 선택한 네임스페이스에 따라 이벤트의 키를 정의할 때 사용됩니다. 네임스페이스 선택을 참조하십시오. 자세한 내용은 을 참조하십시오 [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

이 식에서 이벤트의 &#39;IdentityMap&#39; 필드에 &#39;Email&#39; 키에 대한 항목이 제공됩니다. &#39;Email&#39; 항목은 &#39;first()&#39;를 사용하여 첫 번째 요소에서 &#39;id&#39;를 가져오는 컬렉션입니다. 자세한 내용은 을 참조하십시오 [](../expression/collection-management-functions.md).

**데이터 소스의 매개 변수 값(데이터 소스 동적 값)**

매개 변수를 호출해야 하는 외부 데이터 소스에서 필드를 선택하면 오른쪽에 새 탭이 표시되어 이 매개 변수를 지정할 수 있습니다. [](../expression/expressionadvanced.md)을 참조하십시오.

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. 매개 변수는 다른 매개 변수도 포함하는 다른 데이터 소스의 모든 유효한 표현식이 될 수 있습니다.

>[!NOTE]
>
>표현식에서 매개 변수 값을 정의하면 오른쪽 탭이 사라집니다.

다음 구문을 사용하십시오.

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: 데이터 소스의 첫 번째 매개 변수의 정확한 이름입니다.
* **`<params-1-value>`**: 첫 번째 매개 변수의 값입니다. 유효한 표현일 수 있습니다.

예제:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
