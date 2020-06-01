---
title: 사용자 인터페이스
description: 사용자 인터페이스에 대해 자세히 알아보기
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: ht
source-wordcount: '995'
ht-degree: 100%

---


# 사용자 인터페이스{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Journey Orchestration을 최대한 활용하려면 인터넷 브라우저로 Chrome을 사용하는 것이 좋습니다.
>
>이 설명서는 제품의 최근 변경 사항을 반영하여 자주 업데이트됩니다. 그러나 실제 제품 인터페이스와 약간 다른 스크린샷도 있습니다.

## Journey Orchestration 액세스{#accessing_journey_orchestration}

Journey Orchestration 인터페이스에 액세스하려면 오른쪽 위의 **[!UICONTROL App Selector]** 아이콘을 클릭합니다. 그런 다음 오른쪽의 &quot;Experience Platform&quot; 아래에서 **[!UICONTROL Journey Orchestration]**&#x200B;을 클릭합니다.

![](../assets/journey1.png)

Experience Cloud 홈 페이지의 **[!UICONTROL Quick access]** 섹션에서 Journey Orchestration에 액세스할 수도 있습니다.

![](../assets/journey1bis.png)

## 인터페이스 살펴보기{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="경로 목록"
>abstract="경로 목록에서는 모든 경로를 한꺼번에 표시하여 해당 상태를 확인하고 기본적인 작업을 수행할 수 있습니다. 경로 복제, 정지, 삭제도 가능합니다. 특정 작업은 수행할 수 없는 경로도 있습니다. 예를 들어 완료된 경로는 삭제하거나 재시작할 수 없습니다. 단, 완료된 경로에서 새 버전을 만들거나 완료된 경로를 복제할 수는 있습니다. 검색 창에서 경로를 검색할 수도 있습니다."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="데모 비디오 시청"

상단 메뉴에서는 **[!UICONTROL Home]**(경로),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**&#x200B;과 같은 Journey Orchestration의 다양한 기능 간을 이동할 수 있습니다.

![](../assets/journey2.png)

화면 오른쪽 위의 ![](../assets/icon-context.png) 아이콘을 클릭하면 상황별 도움말이 표시됩니다. 경로, 이벤트, 작업, 데이터 소스 등의 다양한 Journey Orchestration 목록 화면에서 이 아이콘이 제공됩니다. 이 아이콘을 통해 현재 사용 중인 기능의 간략한 설명을 확인하고 관련 문서와 비디오에 액세스할 수 있습니다.

![](../assets/journey2bis.png)

## 검색 및 필터링{#section_lgm_hpz_pgb}

**[!UICONTROL Home]**,**[!UICONTROL Data Sources]**, **[!UICONTROL Events]** 및 **[!UICONTROL Actions]** 목록의 검색 창에서는 특정 항목을 검색할 수 있습니다.

목록 왼쪽 위의 필터 아이콘을 클릭하면 **[!UICONTROL Filters]**&#x200B;에 액세스할 수 있습니다. 필터 메뉴에서는 표시된 요소를 다양한 조건에 따라 필터링할 수 있습니다. 예를 들어 특정 유형이나 상태의 요소, 직접 만든 요소 또는 지난 30일 동안 수정한 요소만 표시하도록 선택할 수 있습니다.

**[!UICONTROL Data Sources]**, **[!UICONTROL Events]** 및 **[!UICONTROL Actions]** 목록에서 **만들기 필터**&#x200B;를 사용하면 만든 날짜와 사용자를 기준으로 필터링할 수 있습니다. 예를 들어 지난 30일 동안 만든 이벤트만 표시하도록 선택할 수 있습니다.

**[!UICONTROL Home]** 아래의 경로 목록에서는 **[!UICONTROL Creation filters]**&#x200B;를 사용할 수 있을 뿐 아니라, **[!UICONTROL Status and version filters]**&#x200B;를 사용하여 표시된 경로를 상태와 버전에 따라 필터링할 수도 있습니다. **[!UICONTROL Activity filters]** 및 **[!UICONTROL Data filters]**&#x200B;를 사용하면 특정 이벤트, 필드 그룹 또는 작업을 사용하는 경로만 표시하도록 선택할 수도 있습니다. 그리고 **[!UICONTROL Publication filters]**&#x200B;를 사용하면 게시 날짜나 사용자를 선택할 수 있습니다. 예를 들어 어제 게시된 라이브 경로의 최신 버전만 표시하도록 선택할 수 있습니다. [](../building-journeys/using-the-journey-designer.md)을 참조하십시오.

>[!NOTE]
>
>목록 오른쪽 위의 구성 버튼을 사용하면 표시되는 열을 개인화할 수 있습니다. 개인화는 내용은 각 사용자별로 저장됩니다.

**[!UICONTROL Last update]** 및 **[!UICONTROL Last update by]** 열에는 경로가 마지막으로 업데이트된 시간과 업데이트를 수행한 사용자를 표시할 수 있습니다.

![](../assets/journey74.png)

이벤트, 데이터 소스 및 작업 구성 창에서 **[!UICONTROL Used in]** 필드를 적용하면 특정 이벤트, 필드 그룹 또는 작업을 사용하는 경로 수가 표시됩니다. **[!UICONTROL View journeys]** 버튼을 클릭하여 해당 경로의 목록을 표시할 수 있습니다.

![](../assets/journey3bis.png)

여러 목록에서 각 요소에 대해 기본적인 작업을 수행할 수 있습니다. 예를 들어 항목을 복제하거나 삭제할 수 있습니다.

![](../assets/journey4.png)

## 데이터 플랫폼 필드 탐색 {#friendly-names-display}

[이벤트 페이로드](../event/defining-the-payload-fields.md)와 [필드 그룹 페이로드](../datasource/field-groups.md)를 정의하고 [표현식 편집기](../expression/expressionadvanced.md)에서 필드를 선택할 때는 필드 이름과 함께 표시 이름도 표시됩니다. 이 정보는 Experience Data Model의 스키마 정의에서 검색됩니다.

스키마를 설정할 때 &quot;xdm:alternateDisplayInfo&quot;와 같은 설명자를 입력하면 사용자에게 친숙한 이름이 표시 이름 대신 표시됩니다. 따라서 &quot;eVar&quot; 및 일반 필드 사용 시에 특히 유용합니다. 친숙한 이름 설명자는 API 호출을 통해 구성할 수 있습니다. 자세한 내용은 [스키마 레지스트리 개발자 안내서](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/api/getting-started.html)를 참조하십시오.

![](../assets/xdm-from-descriptors.png)

친숙한 이름을 사용할 수 있으면 필드가 `<friendly-name>(<name>)`으로 표시됩니다. 친숙한 이름을 사용할 수 없으면 `<display-name>(<name>)`과 같이 표시 이름이 표시됩니다. 어떤 이름도 정의되어 있지 않으면 필드의 기술적 이름(`<name>`)만 표시됩니다.

>[!NOTE]
>
>스키마 조합에서 필드를 선택하면 친숙한 이름이 검색되지 않습니다.

## 다양한 단축키 사용{#section_ksq_zr1_ffb}

Journey Orchestration 인터페이스에서는 다음과 같은 여러 단축키를 사용할 수 있습니다.

_경로, 작업, 데이터 소스 또는 이벤트 목록:_

* 새 경로, 작업, 데이터 소스 또는 이벤트를 만들려면 **c** 키를 누릅니다.

_경로에서 활동 구성 시:_

캔버스는 자동으로 저장됩니다. 캔버스 왼쪽 위에서 저장 상태를 확인할 수 있습니다.

* 구성 창을 닫고 적용한 변경 사항을 취소하려면 **Esc** 키를 누릅니다. 그러면 **[!UICONTROL Cancel]** 버튼을 누르는 것과 같은 작업이 수행됩니다.
* 구성 창을 닫으려면 **[!UICONTROL Enter]** 키를 누르거나 창 바깥쪽을 클릭합니다. 그러면 변경 사항이 저장됩니다. 즉, **[!UICONTROL Ok]** 버튼을 누르는 것과 같은 작업이 수행됩니다.
* **[!UICONTROL Delete]** 또는 **백스페이스** 키를 누른 다음 **[!UICONTROL Enter]** 키를 눌러 삭제를 확인할 수 있습니다.

_팝업:_

* 팝업을 닫으려면 **Esc** 키를 누릅니다. 그러면 **취소** 버튼을 누르는 것과 같은 작업이 수행됩니다.
* 저장하거나 확인하려면 **[!UICONTROL Enter]** 키를 누릅니다. 그러면 **[!UICONTROL Ok]** 또는 **[!UICONTROL Save]** 버튼을 누르는 것과 같은 작업이 수행됩니다.

_이벤트, 데이터 소스 또는 작업 구성 창:_

* 내용을 저장하지 않고 구성 창을 닫으려면 **Esc** 키를 누릅니다.
* 수정 사항을 저장하고 구성 창을 닫으려면 **[!UICONTROL Enter]** 키를 누릅니다.
* 구성하려는 필드 간을 이동하려면 **Tab** 키를 누릅니다.

_단순 표현식 편집기:_

* 왼쪽의 필드를 두 번 클릭하여 쿼리를 추가합니다. 그러면 쿼리를 끌어서 놓는 것과 같은 작업이 수행됩니다.

_XDM 필드 검색 시:_

* &quot;node&quot;를 선택하면 노드의 모든 필드가 선택됩니다.

_모든 텍스트 영역:_

* 텍스트를 선택하려면 **Ctrl/Command+A** 키 조합을 사용합니다. 페이로드 미리 보기에서 이 키 조합을 누르면 페이로드가 선택됩니다.

_검색 창이 있는 화면:_

* 검색 창을 선택하려면 **Ctrl/Command+F** 키 조합을 사용합니다.

_경로의 캔버스:_

* 모든 활동을 선택하려면 **Ctrl/Command+A** 키 조합을 사용합니다.
* 선택한 하나 이상의 활동을 삭제하려면 **[!UICONTROL Delete]** 또는 **백스페이스** 키를 누릅니다. 그런 다음 **[!UICONTROL Enter]** 키를 눌러 확인 팝업에서 삭제를 확인할 수 있습니다.
* 활동을 사용 가능한 첫 번째 위치(위쪽부터)에 추가하려면 왼쪽 팔레트에서 해당 활동을 두 번 클릭합니다.
