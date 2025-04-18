---
product: adobe campaign
title: 여정 보고서 만들기
description: 여정 보고서를 만드는 방법을 알아봅니다
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 2%

---

# 여정 보고서 만들기 {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


## 보고서 액세스 및 만들기 {#accessing-reports}

>[!NOTE]
>
>여정을 삭제하면 관련된 모든 보고서를 더 이상 사용할 수 없습니다.

이 섹션에서는 기본 보고서를 만들거나 사용하는 방법을 설명합니다. 패널, 구성 요소 및 시각화를 결합하여 여정의 성공을 더 잘 추적합니다.

여정 보고서에 액세스하고 게재의 성공을 추적하려면 다음을 수행하십시오.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭을 클릭합니다.

1. 보고할 여정을 선택합니다.

   여정 목록의 여정 위로 마우스를 가져가는 동안 **보고서**&#x200B;를 클릭하여 보고서에 액세스할 수도 있습니다.

   ![](../assets/dynamic_report_journey.png)

1. 화면 오른쪽 상단의 **[!UICONTROL Report]** 아이콘을 클릭합니다.

   ![](../assets/dynamic_report_journey_2.png)

1. **[!UICONTROL Journey summary]** 기본 제공 보고서가 화면에 표시됩니다. 사용자 지정 보고서에 액세스하려면 **[!UICONTROL Close]** 단추를 클릭하십시오.

   ![](../assets/dynamic_report_journey_12.png)

1. 보고서를 처음부터 만들려면 **[!UICONTROL Create new project]**&#x200B;을(를) 클릭합니다.

   ![](../assets/dynamic_report_journey_3.png)

1. **[!UICONTROL Panels]** 탭에서 필요에 따라 패널이나 자유 형식 테이블을 끌어서 놓습니다. 자세한 정보는 이 [섹션](#adding-panels)을 참조하세요.

   ![](../assets/dynamic_report_journey_4.png)

1. 그런 다음 **[!UICONTROL Components]** 탭에서 차원 및 지표를 자유 형식 테이블로 끌어서 놓아 데이터 필터링을 시작할 수 있습니다. 자세한 정보는 이 [섹션](#adding-components)을 참조하세요.

   ![](../assets/dynamic_report_journey_5.png)

1. 데이터를 더 명확하게 보기 위해 **[!UICONTROL Visualizations]** 탭에서 시각화를 추가할 수 있습니다. 자세한 정보는 이 [섹션](#adding-visualizations)을 참조하세요.

## 패널 추가{#adding-panels}

### 빈 패널 추가 {#adding-a-blank-panel}

보고서를 시작하려면 기본 제공 보고서 또는 사용자 지정 보고서에 패널 세트를 추가할 수 있습니다. 각 패널에는 다양한 데이터 세트가 포함되어 있으며 자유 형식 테이블 및 시각화로 구성됩니다.

이 패널을 통해 필요에 따라 보고서를 작성할 수 있습니다. 보고서에 원하는 만큼 패널을 추가하여 데이터를 다양한 기간으로 필터링할 수 있습니다.

1. **[!UICONTROL Panels]** 아이콘을 클릭합니다. **[!UICONTROL Insert tab]**&#x200B;을(를) 클릭하고 **[!UICONTROL New Blank Panel]**&#x200B;을(를) 선택하여 패널을 추가할 수도 있습니다.

   ![](../assets/dynamic_report_panel_1.png)

1. **[!UICONTROL Blank Panel]**&#x200B;을(를) 대시보드로 끌어서 놓습니다.

   ![](../assets/dynamic_report_panel.png)

이제 자유 형식 테이블을 패널에 추가하여 데이터 타깃팅을 시작할 수 있습니다.

### 자유 형식 테이블 추가 {#adding-a-freeform-table}

자유 형식 테이블을 사용하면 **[!UICONTROL Component]** 테이블에서 사용할 수 있는 다양한 지표 및 차원을 사용하여 데이터를 분석하는 테이블을 만들 수 있습니다.

각 테이블 및 시각화는 크기가 변경될 수 있으며, 보고서를 더 잘 사용자 지정하기 위해 이동할 수 있습니다.

1. **[!UICONTROL Panels]** 아이콘을 클릭합니다.

   ![](../assets/dynamic_report_panel_1.png)

1. **[!UICONTROL Freeform]** 항목을 드래그하여 대시보드에 놓습니다.

   **[!UICONTROL Insert]** 탭을 클릭하고 **[!UICONTROL New Freeform]**&#x200B;을(를) 선택하거나 빈 패널에서 **[!UICONTROL Add a freeform table]**&#x200B;을(를) 클릭하여 표를 추가할 수도 있습니다.

   ![](../assets/dynamic_report_panel_2.png)

1. **[!UICONTROL Components]** 탭의 항목을 열 및 행으로 끌어다 놓아 표를 작성하십시오.

   ![](../assets/dynamic_report_freeform_3.png)

1. 열에 데이터가 표시되는 방식을 변경하려면 **[!UICONTROL Settings]** 아이콘을 클릭합니다.

   ![](../assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;은(는) 다음으로 구성됩니다.

   * **[!UICONTROL Number]**: 열에서 요약 번호를 표시하거나 숨길 수 있습니다.
   * **[!UICONTROL Percent]**: 열에서 백분율을 표시하거나 숨길 수 있습니다.
   * **[!UICONTROL Interpret zero as no value]**: 값이 0일 때 표시하거나 숨길 수 있습니다.
   * **[!UICONTROL Background]**: 셀에서 가로 진행률 표시줄을 표시하거나 숨길 수 있습니다.
   * **[!UICONTROL Include retries]**: 결과에 다시 시도를 포함할 수 있습니다. **[!UICONTROL Sent]** 및 **[!UICONTROL Bounces + Errors]**&#x200B;에만 사용할 수 있습니다.

1. 하나 이상의 행을 선택하고 **[!UICONTROL Visualize]** 아이콘을 클릭합니다. 선택한 행을 반영하도록 시각화가 추가됩니다.

   ![](../assets/dynamic_report_freeform_5.png)

이제 필요한 만큼 구성 요소를 추가하고 시각화를 추가하여 데이터를 그래픽으로 표시할 수도 있습니다.

## 구성 요소 추가{#adding-components}

구성 요소를 사용하여 다양한 차원, 지표 및 기간을 사용하여 보고서를 사용자 지정할 수 있습니다.

1. 구성 요소 목록에 액세스하려면 **[!UICONTROL Components]** 탭을 클릭하십시오.

   ![](../assets/dynamic_report_components.png)

1. **[!UICONTROL Components]** 탭에 표시되는 각 범주에는 가장 많이 사용되는 5개의 항목이 표시되며, 범주 이름을 클릭하여 전체 구성 요소 목록에 액세스합니다.

   구성 요소 테이블은 다음 세 가지 카테고리로 나뉩니다.

   * **[!UICONTROL Dimensions]**: 게재 로그에서 수신자의 브라우저나 도메인 또는 게재 성공 등 세부 정보를 가져옵니다.
   * **[!UICONTROL Metrics]**: 메시지 상태에 대한 세부 정보를 가져옵니다. 예를 들어 메시지가 게재되고 사용자가 메시지를 연 경우.
   * **[!UICONTROL Time]**: 테이블의 기간을 설정합니다.

1. 패널에 구성 요소를 드래그 앤 드롭하여 데이터 필터링을 시작합니다.

필요한 만큼 구성 요소를 드래그하여 놓고 서로 비교할 수 있습니다.

## 시각화 추가{#adding-visualizations}

**[!UICONTROL Visualizations]** 탭에서는 영역, 도넛 및 그래프와 같은 시각화 항목을 끌어서 놓을 수 있습니다. 시각화는 데이터를 그래픽으로 표시합니다.

1. **[!UICONTROL Visualizations]** 탭에서 시각화 항목을 패널로 끌어서 놓습니다.

   ![](../assets/dynamic_report_visualization_1.png)

1. 패널에 시각화를 추가하면 보고서가 자유 형식 테이블의 데이터를 자동으로 검색합니다. 시각화에 대한 설정을 선택합니다.
1. 자유 형식 테이블이 두 개 이상인 경우 **[!UICONTROL Data Source Settings]** 창에서 그래프에 추가할 사용 가능한 데이터 원본을 선택하십시오. 이 창은 시각화 제목 옆에 있는 색상이 지정된 점을 클릭해도 사용할 수 있습니다.

   ![](../assets/dynamic_report_visualization_2.png)

1. 그래프 유형 또는 그래프 유형에 표시되는 내용을 직접 변경하려면 **[!UICONTROL Visualization]** 설정 단추를 클릭하십시오. 예:

   * **[!UICONTROL Percentages]**: 값을 백분율로 표시합니다.
   * **[!UICONTROL Anchor Y Axis at Zero]**: 값이 0보다 큰 경우에도 y축을 0으로 강제 적용합니다.
   * **[!UICONTROL Legend visible]**: 범례를 숨길 수 있습니다.
   * **[!UICONTROL Normalization]**: 값을 강제로 일치시킵니다.
   * **[!UICONTROL Display Dual Axis]**: 그래프에 다른 축을 추가합니다.
   * **[!UICONTROL Limit Max Items]**: 표시되는 그래프 수를 제한합니다.
   * **[!UICONTROL Threshold]**: 그래프에 임계값을 설정할 수 있습니다. 검은색 점선으로 표시됩니다.

   ![](../assets/dynamic_report_visualization_3.png)

이 시각화를 사용하면 보고서에서 데이터를 더 명확하게 볼 수 있습니다.
