---
product: adobe campaign
title: 사용자 지정 작업 사용
description: 작업 활동에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# 사용자 지정 작업 사용 {#section_f2c_hbg_nhb}

활동 구성 창에는 사용자 지정 작업에 대해 구성된 URL 구성 매개 변수와 인증 매개 변수가 표시됩니다. [자세히 알아보기](../action/about-custom-action-configuration.md).

## URL 구성

### 동적 경로

URL에 동적 경로가 포함된 경우 **[!UICONTROL Path]** 필드에 경로를 지정하십시오.

>[!NOTE]
>
>여정에서 URL의 정적 부분을 설정할 수 없지만 사용자 지정 작업의 전역 구성에서는 설정할 수 있습니다. [자세히 알아보기](../action/about-custom-action-configuration.md).

필드와 일반 텍스트 문자열을 연결하려면 고급 표현식 편집기에서 String 함수 또는 더하기 기호(+)를 사용하십시오. 일반 텍스트 문자열을 작은따옴표(&#39;) 또는 큰따옴표(&quot;)로 묶습니다. [자세히 알아보기](../expression/expressionadvanced.md).

이 표에서는 구성의 예를 보여 줍니다.

| 필드 | 값 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| 경로 | `The id of marketingCampaign + '/messages'` |

연결된 URL의 형식은 다음과 같습니다.

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;캠페인 ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### 헤더

**[!UICONTROL URL Configuration]** 섹션에는 동적 헤더 필드가 표시되지만 상수 헤더 필드는 표시되지 않습니다. 동적 헤더 필드는 값이 변수로 구성된 HTTP 헤더 필드입니다. [자세히 알아보기](../action/about-custom-action-configuration.md).

필요한 경우 동적 헤더 필드의 값을 지정합니다.

1. 여정에서 사용자 지정 작업을 선택합니다.
1. 구성 창에서 **[!UICONTROL URL Configuration]** 섹션의 머리글 필드 옆에 있는 연필 아이콘을 클릭합니다.

   ![](../assets/journey-dynamicheaderfield.png)

1. 필드를 선택하고 **[!UICONTROL OK]**&#x200B;을(를) 클릭합니다.

## 작업 매개 변수

**[!UICONTROL Action parameters]** 섹션에는 _&quot;변수&quot;_(으)로 정의된 메시지 매개 변수가 표시됩니다. 이러한 매개 변수의 경우 이 정보를 가져올 위치(예: 이벤트, 데이터 소스)를 정의하거나, 값을 수동으로 전달하거나, 고급 사용 사례에 고급 표현식 편집기를 사용할 수 있습니다. 고급 사용 사례는 데이터 조작 및 기타 함수 사용일 수 있습니다. [자세히 알아보기](../expression/expressionadvanced.md).

**관련 항목**

[작업 구성](../action/about-custom-action-configuration.md)
