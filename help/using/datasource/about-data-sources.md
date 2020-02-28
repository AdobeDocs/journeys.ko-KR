---
title: 데이터 소스 정보
description: '데이터 소스 구성 방법 살펴보기 '
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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---


# 데이터 소스 정보 {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;데이터 소스 정보&quot;
>abstract=&quot;데이터 소스 구성은 기술 사용자가 항상 수행합니다. 데이터 소스 구성을 사용하면 시스템에 대한 연결을 정의하여 다음 경우에 사용할 추가 정보를 검색할 수 있습니다.동작의 조건 정의, 매개 변수 및 개인화 데이터, 사용자 정의 대기 정의, 사용자 정의 시간대 정의.&quot;

데이터 소스 구성을 사용하면 시스템에 대한 연결을 정의하여 다음 경우에 사용할 추가 정보를 검색할 수 있습니다.

* [조건 정의](../building-journeys/condition-activity.md)
* 매개 변수 및 [액션 개인화 데이터](../action/action.md)
* [사용자 지정 대기 정의](../building-journeys/wait-activity.md#custom)
* [사용자 지정 시간대 정의](../building-journeys/timezone-management.md)

이 구성은 여정이 이벤트 페이로드에서 나오는 로컬 데이터만 활용하는 경우에는 필요하지 않습니다. 예를 들어, 여행에서 이벤트의 데이터만 사용하는 이메일 활동이 뒤에 오는 이벤트로 구성된 경우 데이터 소스를 구성할 필요가 없습니다.

두 가지 유형의 데이터 소스가 있습니다.

* 실시간 고객 프로필 서비스에 대한 연결을 정의하는 사전 구성된 경험 플랫폼 데이터 소스입니다. 기본 제공 데이터 소스입니다. 을 [](../datasource/adobe-experience-platform-data-source.md)참조하십시오.
* 외부 시스템에 대한 연결을 정의할 수 있는 외부 데이터 소스입니다. 이러한 기능을 통해 제작할 수 있습니다. 을 [](../datasource/external-data-sources.md)참조하십시오.

각 데이터 소스에 대해 필드 그룹을 사용하여 검색할 정보를 정의합니다. 필드 그룹은 데이터 소스에서 검색할 수 있는 필드 세트입니다. 을 [](../datasource/field-groups.md)참조하십시오.

경험 플랫폼 데이터 소스 및 외부 데이터 소스를 구성하는 방법과 여정에서 데이터를 찾고 사용하는 방법에 대한 자세한 내용은 이 [자습서 비디오를](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)참조하십시오.

다음은 기본 데이터 소스 구성 단계입니다.

>[!NOTE]
>
>데이터 소스 구성은 항상 **기술 사용자가**&#x200B;수행합니다.

1. 상단 메뉴에서 **[!UICONTROL Data Sources]** 탭을 클릭합니다.

   데이터 소스 목록이 표시됩니다. 인터페이스에 [](../about/user-interface.md) 대한 자세한 내용은 을 참조하십시오.

   ![](../assets/journey18.png)

1. 그런 다음 기본 제공 데이터 소스에 필드 그룹을 추가하거나( [](../datasource/adobe-experience-platform-data-source.md)참조) 새 외부 데이터 소스( [](../datasource/external-data-sources.md)참조) 및 관련 필드 그룹을 만들 수 있습니다( 참조 [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. 클릭 **[!UICONTROL Save]**.

   이제 데이터 소스가 구성되어 사용 중에 사용할 준비가 되었습니다.
