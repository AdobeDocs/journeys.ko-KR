---
product: adobe campaign
title: URL 구성
description: URL 구성에 대해 알아보기
feature: 여정
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 14%

---

# URL 구성 {#concept_gbg_1f1_2gb}

사용자 지정 작업을 구성할 때 다음 **[!UICONTROL URL Configuration]** 매개 변수를 정의해야 합니다.

![](../assets/journeyurlconfiguration.png)

1. 외부 서비스의 **[!UICONTROL URL]**&#x200B;을(를) 추가합니다.

   >[!NOTE]
   >
   >보안상 HTTPS를 사용하는 것이 좋습니다. 공개되지 않은 Adobe 주소 및 IP 주소 사용을 허용하지 않습니다.

1. 호출 **[!UICONTROL Method]**&#x200B;을 선택합니다. **[!UICONTROL POST]** 또는 **[!UICONTROL PUT]**&#x200B;일 수 있습니다.
1. **[!UICONTROL Headers]** 섹션에서 **[!UICONTROL Add a header field]** 를 클릭하여 새 키/값 쌍을 정의합니다. 이는 외부 서비스에 대한 요청의 HTTP 헤더에 해당합니다. 키/값 쌍을 삭제하려면 **[!UICONTROL Headers]** 필드에 커서를 놓고 **[!UICONTROL Delete]** 아이콘을 클릭합니다.

   **[!UICONTROL Content-Type]** 및 **[!UICONTROL Charset]** 는 기본적으로 설정되며 삭제하거나 대체할 수 없습니다.

   >[!NOTE]
   >
   >헤더는 다음 [구문 분석 규칙](https://tools.ietf.org/html/rfc7230#section-3.2.4)에 따라 검증됩니다.
