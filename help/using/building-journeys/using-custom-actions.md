---
product: adobe campaign
title: 사용자 지정 작업 사용
description: 작업 활동에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---

# 사용자 지정 작업 사용 {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


The activity configuration pane shows the URL configuration parameters and the authentication parameters that are configured for the custom action. [자세히 알아보기](../action/about-custom-action-configuration.md).

## URL 구성

### 동적 경로

If the URL includes a dynamic path, specify the path in the **[!UICONTROL Path]** field.

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

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### 헤더

The **[!UICONTROL URL Configuration]** section shows the dynamic header fields, but not the constant header fields. Dynamic header fields are HTTP header fields whose value is configured as a variable. [자세히 알아보기](../action/about-custom-action-configuration.md).

If required, specify the value of dynamic header fields:

1. Select the custom action in the journey.
1. In the configuration pane, click the pencil icon next to the header field in the **[!UICONTROL URL Configuration]** section.

   ![](../assets/journey-dynamicheaderfield.png)

1. Select a field and click **[!UICONTROL OK]**.

## 작업 매개 변수

In the **[!UICONTROL Action parameters]** section, you&#39;ll see the message parameters defined as _&quot;Variable&quot;_. 이러한 매개 변수의 경우 이 정보를 가져올 위치(예: 이벤트, 데이터 소스)를 정의하거나, 값을 수동으로 전달하거나, 고급 사용 사례에 고급 표현식 편집기를 사용할 수 있습니다. 고급 사용 사례는 데이터 조작 및 기타 함수 사용일 수 있습니다. [자세히 알아보기](../expression/expressionadvanced.md).

**관련 항목**

[작업 구성](../action/about-custom-action-configuration.md)
