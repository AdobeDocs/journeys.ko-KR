---
product: adobe campaign
title: 여정 보고서 정보
description: 여정 보고서를 작성하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# 여정 보고서 정보 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>게재 데이터 및 세그먼트 구성 요소는 Adobe Campaign Standard이 있는 경우에만 채워집니다.

이 섹션에서는 보고서에 액세스하고 보고서를 사용하여 여정의 효과를 측정하는 방법을 설명합니다.

## 보고 인터페이스 {#reporting-interface}

예를 들어, 상단 도구 모음을 사용하여 보고서를 수정, 저장 또는 인쇄할 수 있습니다.

![](../assets/dynamic_report_toolbar.png)

사용 **[!UICONTROL Project]** 탭 위치:

* **[!UICONTROL Open]**: 이전에 만든 보고서나 템플릿을 엽니다.
* **[!UICONTROL Save As]**: 템플릿을 복제하여 수정할 수 있습니다.
* **[!UICONTROL Refresh project]**: 새로운 데이터 및 필터 변경 사항을 기반으로 보고서를 업데이트합니다.
* **[!UICONTROL Download CSV]**: 보고서를 CSV 파일로 내보냅니다.
* **[!UICONTROL Print]**: 보고서를 인쇄합니다.

다음 **[!UICONTROL Edit]** 탭에서는 다음 작업을 수행할 수 있습니다.

* **[!UICONTROL Undo]**: 대시보드에서 마지막 작업을 취소합니다.
* **[!UICONTROL Redo]**: 마지막 항목을 취소합니다 **[!UICONTROL Undo]** 작업을 대시보드에서 수행합니다.
* **[!UICONTROL Clear all]**: 대시보드의 모든 패널을 삭제합니다.

다음 **[!UICONTROL Insert]** 테이블을 사용하면 대시보드에 그래프 및 표를 추가하여 보고서를 사용자 정의할 수 있습니다.

* **[!UICONTROL New Blank Panel]**: 대시보드에 새 빈 패널을 추가합니다.
* **[!UICONTROL New Freeform]**: 대시보드에 새 자유 형식 테이블을 추가합니다.
* **[!UICONTROL New Line]**: 대시보드에 새 선 그래프를 추가합니다.
* **[!UICONTROL New Bar]**: 대시보드에 새 막대 그래프를 추가합니다.

왼쪽 탭을 사용하여 보고서를 작성하고 필요에 따라 데이터를 필터링할 수 있습니다.

![](../assets/dynamic_report_interface.png)

이 탭에서는 다음 항목에 액세스할 수 있습니다.

* **[!UICONTROL Panels]**: 빈 패널 또는 자유 양식을 보고서에 추가하여 데이터 필터링을 시작합니다. 자세한 내용은 [패널 추가](../reporting/creating-your-journey-reports.md#adding-panels) 섹션
* **[!UICONTROL Visualizations]**: 선택한 시각화 항목을 끌어다 놓아 보고서에 그래픽 차원을 제공합니다. 자세한 내용은 [시각화 추가](../reporting/creating-your-journey-reports.md#adding-visualizations) 섹션.
* **[!UICONTROL Components]**: 다양한 차원, 지표, 세그먼트 및 기간을 사용하여 보고서를 사용자 지정합니다. 자세한 내용은 [구성 요소 추가](../reporting/creating-your-journey-reports.md#adding-components) 섹션.

## 여정 요약 템플릿 {#ootb-template}

보고서는 기본 제공 템플릿과 사용자 정의 보고서의 두 가지 범주로 나뉩니다.
기본 제공 템플릿, **[!UICONTROL Journey summary]**&#x200B;를 사용하면 가장 중요한 추적 데이터를 명확하게 볼 수 있습니다.

![](../assets/dynamic_report_journey_8.png)

각 테이블은 요약 번호와 차트로 표시됩니다. 세부 사항이 각각의 시각화 설정에 표시되는 방식을 변경할 수 있습니다.

보고서 맨 위에서 다음 KPI를 사용할 수 있습니다.

* **[!UICONTROL Journey - Entered]**: 여정의 시작 이벤트에 도달한 총 개인 수입니다.
* **[!UICONTROL Journey - Completion rate]**: 여정에 들어간 총 개인 수와 비교하여 여정의 끝에 도달한 개인의 총 수 (또는 조건과 일치하지 않는 개인의 경우).
* **[!UICONTROL Journey - Current]**: 현재 여정에 있는 총 개인 수입니다.
* **[!UICONTROL Journey - Failed rate]**: 실행 여정 수와 비교하여 성공적으로 실행되지 않은 총 여정 수입니다.
* **[!UICONTROL Delivery - Messages sent]**: 전송된 총 메시지 수입니다.
* **[!UICONTROL Delivery rate]**: 전송된 메시지와 비교하여 성공적으로 전달된 총 메시지 수입니다.
* **[!UICONTROL Delivery - Bounce rate]**: 전송된 메시지와 비교하여 반송된 총 메시지 수입니다.
* **[!UICONTROL Delivery - Unsubscribed rate]**: 배달된 메시지와 비교한 수신자의 총 구독 취소 수입니다.
* **[!UICONTROL Delivery - Open rate]**: 배달된 메시지 수와 비교하여 열린 총 메시지 수입니다.
* **[!UICONTROL Delivery - Click rate]**: 게재된 총 클릭 수와 게재된 메시지 수 비교.

여정 흐름 시각화를 사용하면 여정을 통해 타겟팅된 프로필의 경로를 단계별로 볼 수 있습니다. 한 명의 여정을 타겟팅할 때만 사용할 수 있습니다. 자동으로 생성되며 수정할 수 없습니다.

![](../assets/dynamic_report_journey_10.png)

다음 **[!UICONTROL Journey summary]** 테이블에는 여정에 사용할 수 있는 다음과 같은 데이터가 포함되어 있습니다.

* **[!UICONTROL Entered]**: 여정의 시작 이벤트에 도달한 총 개인 수입니다.
* **[!UICONTROL Completion rate]**: 여정에 들어간 총 개인 수와 비교하여 여정의 최종 흐름 제어에 도달한 총 개인 수
* **[!UICONTROL Current]**: 현재 여정에 있는 총 개인 수입니다.
* **[!UICONTROL Failed]**: 성공적으로 실행되지 않은 총 여정 수입니다.
* **[!UICONTROL Failed rate]**: 실행 여정 수와 비교하여 성공적으로 실행되지 않은 총 여정 수입니다.

다음 **[!UICONTROL Top events]** 테이블에는 가장 성공적인 이벤트와 **[!UICONTROL Top action]**: 여정에서 가장 성공적인 작업입니다.

![](../assets/dynamic_report_journey_11.png)

다음 **[!UICONTROL Delivery - Sending summary]** 테이블에는 여정 게재에 사용할 수 있는 다음과 같은 데이터가 포함되어 있습니다.

* **[!UICONTROL Processed/sent]**: 전송된 총 메시지 수입니다.
* **[!UICONTROL Delivered rate]**: 전송된 메시지와 비교하여 성공적으로 전달된 총 메시지 수입니다.
* **[!UICONTROL Delivered]**: 성공적으로 전송된 메시지 수와 총 전송된 메시지 수
* **[!UICONTROL Bounce + error rate]**: 전송된 메시지와 비교하여 반송된 총 메시지 수입니다.
* **[!UICONTROL Bounces + errors]**: 총 보낸 메시지 수와 관련하여 게재 및 자동 반환 처리 중에 누적된 총 오류.

다음 **[!UICONTROL Delivery - Tracking summary]** 테이블에는 다음과 같이 여정 게재의 성공을 추적하는 데 사용할 수 있는 데이터가 포함되어 있습니다.

* **[!UICONTROL Open Rate]**: 열린 메시지의 비율입니다.
* **[!UICONTROL Open]**: 게재 시 메시지가 열린 횟수입니다.
* **[!UICONTROL Click trough rate]**: 게재된 총 클릭 수와 게재된 메시지 수 비교.
* **[!UICONTROL Click]**: 게재 시 콘텐츠를 클릭한 횟수입니다.
* **[!UICONTROL Unsubscribe rate]**: 게재된 메시지와 비교한 수신자의 구독 취소 비율.
* **[!UICONTROL Unsubscribed]**: 배달된 메시지와 비교한 수신자의 총 구독 취소 수입니다.
