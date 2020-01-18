---
title: URL 구성
description: URL 구성에 대한 자세한 내용
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


# URL 구성 {#concept_gbg_1f1_2gb}

사용자 지정 작업을 구성할 때 다음 **[!UICONTROL URL Configuration]**매개 변수를 정의해야 합니다.

![](../assets/journeyurlconfiguration.png)

1. 외부 **[!UICONTROL URL]**서비스의 추가

   >[!NOTE]
   >
   >보안상의 이유로 HTTPS를 사용하는 것이 좋습니다. Adobe는 공개되지 않은 Adobe 주소 및 IP 주소 사용을 허용하지 않습니다.

1. 다음을 **[!UICONTROL Method]**선택합니다.또는**[!UICONTROL POST]** 중 하나일 수 **[!UICONTROL PUT]**있습니다.
1. 섹션에서 을 클릭하여 새 키/값 쌍을 **[!UICONTROL Headers]****[!UICONTROL Add a header field]** 정의합니다. 외부 서비스에 대한 요청의 HTTP 헤더에 해당합니다. 키/값 쌍을 삭제하려면 **[!UICONTROL Headers]**필드에 커서를 놓고 아이콘을 클릭합니다**[!UICONTROL Delete]** .

   **[!UICONTROL Content-Type]**기본적으로 설정되어**[!UICONTROL Charset]** 있으며 삭제 또는 재정의할 수 없습니다.

   >[!NOTE]
   >
   >헤더는 다음 [구문 분석 규칙에](https://tools.ietf.org/html/rfc7230#section-3.2.4)따라 유효성이 확인됩니다.
