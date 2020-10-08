---
title: URL 구성
description: URL 구성에 대해 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# URL 구성 {#concept_gbg_1f1_2gb}

사용자 지정 작업을 구성할 때 다음 **[!UICONTROL URL Configuration]** 매개 변수를 정의해야 합니다.

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >보안상 HTTPS를 사용하는 것이 좋습니다. 공개되지 않은 Adobe 주소 및 IP 주소 사용을 허용하지 않습니다.

1. 다음 호출을 선택합니다 **[!UICONTROL Method]**.또는 **[!UICONTROL POST]** 중 하나일 수 **[!UICONTROL PUT]**&#x200B;있습니다.
1. 섹션에서 **[!UICONTROL Headers]** 을 클릭하여 새 키/값 쌍 **[!UICONTROL Add a header field]** 을 정의합니다. 외부 서비스에 대한 요청의 HTTP 헤더에 해당합니다. 키/값 쌍을 삭제하려면 필드에 커서를 놓고 아이콘을 **[!UICONTROL Headers]** 클릭합니다 **[!UICONTROL Delete]** .

   **[!UICONTROL Content-Type]** 및 **[!UICONTROL Charset]** 는 기본적으로 설정되며 삭제 또는 재정의할 수 없습니다.

   >[!NOTE]
   >
   >헤더는 다음 [구문 분석 규칙에 따라 유효성이 확인됩니다](https://tools.ietf.org/html/rfc7230#section-3.2.4).
