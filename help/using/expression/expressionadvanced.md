---
title: 고급 표현식 편집기 정보
description: 고급 표현식을 작성하는 방법 살펴보기
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 고급 표현식 편집기 정보 {#concept_uyj_trt_52b}

고급 표현식 편집기를 사용하면 데이터 소스 조건을 정의할 때와 같이 인터페이스의 다양한 화면에서 고급 표현식을 작성할 수 있습니다.
특정 데이터 조작이 필요한 작업 매개 변수를 정의해야 할 때마다 이 매개 변수를 사용할 수도 있습니다. 이벤트에서 오는 데이터나 데이터 소스에서 검색된 추가 정보를 활용할 수 있습니다. 여정에서 표시되는 이벤트 필드 목록은 상황에 따라 다르며 여정에 추가된 이벤트에 따라 달라집니다.

고급 표현식 편집기에서는 값을 조작하고 필요에 맞는 표현식을 정의할 수 있도록 해주는 내장 함수와 연산자를 제공합니다. 또한 고급 표현식 편집기를 사용하여 외부 데이터 소스 매개 변수의 값을 정의하고, 맵 필드와 컬렉션(예: 경험 이벤트)을 조작할 수 있습니다.

![](../assets/journey65.png)

_고급 표현식 편집기 인터페이스_

고급 표현식 편집기를 사용하여 다음을 수행할 수 있습니다.

* 데이터 소스 및 이벤트 정보에 대한 [고급 조건](../building-journeys/condition-activity.md#about_condition) 만들기
* 날짜 조건에서 사용자 지정 [시간대를](../building-journeys/timezone-management.md) 정의하고, 고정 날짜 대기 활동, 사용자 지정 대기 활동
* 사용자 지정 [대기 활동 정의](../building-journeys/wait-activity.md#custom)
* 작업 매개변수 매핑 정의

가능한 경우 **[!UICONTROL Advanced mode]**/**[!UICONTROL Simple mode]** 단추를 사용하여 두 모드 간을 전환할 수 있습니다. 간단한 모드는 [여기에서](../building-journeys/condition-activity.md#about_condition)설명합니다.

>[!NOTE]
>
>조건은 단순 또는 고급 표현식 편집기에서 정의할 수 있습니다. 항상 부울 형식을 반환합니다.
>
>작업 매개 변수는 필드를 선택하거나 고급 표현식 편집기를 통해 정의할 수 있습니다. 표현식에 따라 특정 데이터 형식을 반환합니다.

## 고급 표현식 편집기 액세스 {#section_fdz_4nj_cjb}

다음과 같은 다양한 방법으로 고급 표현식 편집기에 액세스할 수 있습니다.

* 데이터 소스 조건을 만들 때 을 클릭하여 고급 편집기에 액세스할 수 **[!UICONTROL Advanced mode]**있습니다.

   ![](../assets/journeyuc2_33.png)

* 사용자 지정 시간대나 사용자 지정 타이머를 만들면 고급 편집기가 직접 표시됩니다.
* 작업 매개 변수를 매핑하면 을 클릭합니다 **[!UICONTROL Advanced mode]**.

## 인터페이스 살펴보기{#section_otq_tnj_cjb}

이 화면에서는 표현식을 수동으로 작성할 수 있습니다.

![](../assets/journey70.png)

화면의 왼쪽에 사용 가능한 필드와 기능이 표시됩니다.

* **[!UICONTROL Events]**:인바운드 이벤트에서 받은 필드 중 하나를 선택합니다. 표시된 이벤트 필드 목록은 상황에 따라 다르며 여정에 추가된 이벤트에 따라 달라집니다.
* **[!UICONTROL Data Sources]**:데이터 소스의 필드 그룹에서 사용할 수 있는 필드 목록에서 선택합니다.
* **[!UICONTROL Functions]**:복잡한 필터링을 수행할 수 있는 내장 함수 목록에서 선택하십시오. 함수는 범주별로 구성됩니다.

![](../assets/journey65.png)

자동 완성 메커니즘에는 상황에 맞는 제안이 표시됩니다.

![](../assets/journey68.png)

구문 유효성 검사 메커니즘은 코드의 무결성을 확인합니다. 편집기의 맨 위에 오류가 표시됩니다.

![](../assets/journey69.png)

**고급 표현식 편집기를 사용하여 조건을 작성할 때 매개 변수 필요**

매개 변수를 호출해야 하는 외부 데이터 소스에서 필드를 선택하는 경우( [](../datasource/external-data-sources.md)참조) 예를 들어 날씨 관련 데이터 소스에서 자주 사용되는 매개 변수는 &quot;city&quot;입니다. 따라서 이 도시 매개 변수를 가져올 위치를 선택해야 합니다. 매개 변수에 함수를 적용하여 형식 변경 또는 연결을 수행할 수도 있습니다.

![](../assets/journeyuc2_19.png)

보다 복잡한 사용 사례의 경우 기본 표현식에 데이터 소스의 매개 변수를 포함하려는 경우 &quot;params&quot; 키워드를 사용하여 해당 값을 정의할 수 있습니다. 이 [페이지를](../expression/field-references.md)참조하십시오.
