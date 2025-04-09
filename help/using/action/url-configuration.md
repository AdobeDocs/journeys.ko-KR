---
product: adobe campaign
title: URL 구성
description: URL 구성에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 3%

---

# URL 구성 {#concept_gbg_1f1_2gb}



>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


사용자 지정 작업을 구성할 때 다음 **[!UICONTROL URL Configuration]**&#x200B;개의 매개 변수를 정의해야 합니다.

![](../assets/journeyurlconfiguration.png)

1. **[!UICONTROL URL]** 필드에 외부 서비스의 URL을 지정하십시오.

   * URL이 정적인 경우 이 필드에 URL을 입력합니다.

   * URL에 동적 경로가 포함된 경우 URL의 정적 부분, 즉 체계, 호스트, 포트 및 경로의 정적 부분(선택 사항)만 입력합니다.

     예: `https://xxx.yyy.com/somethingstatic/`

     사용자 지정 작업을 여정에 추가할 때 URL의 동적 경로를 지정합니다. [자세히 알아보기](../building-journeys/using-custom-actions.md).

   >[!NOTE]
   >
   >보안상의 이유로 URL에 HTTPS 스키마를 사용하는 것이 좋습니다. 공개되지 않은 Adobe 주소 및 IP 주소의 사용은 허용되지 않습니다.
   >
   >사용자 지정 작업을 정의할 때 기본 포트만 허용됩니다. http의 경우 80, https의 경우 443.

1. 호출 **[!UICONTROL Method]**&#x200B;을(를) 선택합니다. **[!UICONTROL POST]** 또는 **[!UICONTROL PUT]**&#x200B;일 수 있습니다.
1. **[!UICONTROL Headers]** 섹션에서 외부 서비스로 보낼 요청 메시지의 HTTP 헤더를 정의합니다.
   1. 헤더 필드를 추가하려면 **[!UICONTROL Add a header field]**&#x200B;을(를) 클릭합니다.
   1. 헤더 필드의 키를 입력합니다.
   1. 키-값 쌍의 동적 값을 설정하려면 **[!UICONTROL Variable]**&#x200B;을(를) 선택합니다. 그렇지 않으면 **[!UICONTROL Constant]**&#x200B;을(를) 선택하십시오.

      예를 들어 타임스탬프의 경우 동적 값을 설정할 수 있습니다.

   1. **[!UICONTROL Constant]**&#x200B;을(를) 선택한 경우 상수 값을 입력하십시오.

      **[!UICONTROL Variable]**&#x200B;을(를) 선택한 경우 여정에 사용자 지정 작업을 추가할 때 이 변수를 지정합니다. [자세히 알아보기](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. 헤더 필드를 삭제하려면 헤더 필드를 가리키고 **[!UICONTROL Delete]** 아이콘을 클릭합니다.

   **[!UICONTROL Content-Type]** 및 **[!UICONTROL Charset]** 헤더 필드는 기본적으로 설정됩니다. 이러한 필드는 수정하거나 삭제할 수 없습니다.

   여정에 사용자 지정 작업을 추가한 후에도 여정이 초안 상태인 경우 헤더 필드를 추가할 수 있습니다. 여정이 구성 변경의 영향을 받지 않도록 하려면 사용자 지정 작업을 복제하고 헤더 필드를 새 사용자 지정 작업에 추가합니다.

   >[!NOTE]
   >
   >헤더는 필드 구문 분석 규칙에 따라 유효성이 검사됩니다. [자세히 알아보기](https://tools.ietf.org/html/rfc7230#section-3.2.4).
