---
product: adobe campaign
solution: Journey Orchestration
title: 여정 디자이너 사용
description: 고객 여정 디자이너 사용에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 5%

---


# 여정 디자이너 사용 {#concept_m1g_5qt_52b}

경로 홈 메뉴를 사용하면 여행 **목록을 볼 수 있습니다**. 새 경로를 만들거나 기존 경로를 클릭하여 **경로 디자이너의 인터페이스를 엽니다**. 디자이너는 다음 영역으로 구성됩니다.팔레트, 캔버스 및 활동 구성 창.

## 여정 목록 {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. 경로 복제, 정지, 삭제도 가능합니다. 특정 작업은 수행할 수 없는 경로도 있습니다. 예를 들어 닫힌 경로는 삭제하거나 재시작할 수 없습니다. 여기에서 새 버전을 만들거나 복제하거나 중지할 수 있습니다. 검색 창에서 경로를 검색할 수도 있습니다.

목록 왼쪽 위의 필터 아이콘을 클릭하면 **[!UICONTROL Filters]**&#x200B;에 액세스할 수 있습니다. 필터 메뉴를 사용하면 다양한 기준(상태, 만든 항목, 지난 30일 동안 수정된 항목, 최신 버전만 등)에 따라 표시되는 이동을 필터링할 수 있습니다. 특정 이벤트, 필드 그룹 또는 동작을 사용하는 여정이다. 목록에 표시된 열을 구성할 수 있습니다. 모든 필터 및 열은 사용자별로 저장됩니다.

![](../assets/journey74.png)

버전 번호와 함께 모든 버전의 내경이 목록에 표시됩니다. [이 페이지](../building-journeys/journey-versions.md)를 참조하십시오.

![](../assets/journey37.png)

>[!NOTE]
>
>다른 브라우저 탭에서 경로의 캔버스를 열려면 **Control** 또는 **Command** 키를 누른 상태에서 해당 여정을 클릭합니다.

## 팔레트 {#palette}

팔레트 **** 는 화면의 왼쪽에 있습니다. 사용 가능한 모든 활동은 여러 카테고리로 정렬됩니다. **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** and **[!UICONTROL Actions]**. 이름을 클릭하여 다른 카테고리를 확장/축소할 수 있습니다. 여정에서 활동을 사용하려면 팔레트에서 캔버스로 드래그하여 놓습니다. 팔레트에서 활동을 두 번 클릭하여 캔버스에 추가할 수도 있습니다(다음 단계). 이동을 게시하기 전에 팔레트에서 추가한 각 활동을 구성해야 합니다. 캔버스에 활동을 놓고 구성을 마치지 않으면 캔버스에 남아 있지만 빨간색 경고는 구성이 이 활동에 대해 완료되지 않았음을 나타냅니다.

>[!NOTE]
>
>여정을 설정할 때는 규칙이 있습니다. 허용되지 않은 구성은 무시됩니다. 예를 들어, 작업을 병렬로 배치하거나, 활동을 이전 단계에 연결하여 루프를 만들거나, 이벤트가 아닌 다른 무엇으로 여정을 시작하는 등의 경우

![](../assets/journey38.png)

The **[!UICONTROL Show disabled items]** icon in the top left corner allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. 기본적으로 사용할 수 없는 항목은 숨겨집니다. 표시하려면 해당 항목이 흐리게 표시됩니다.

필드를 사용할 때 **[!UICONTROL Search]** 각 캔버스 활동 카테고리에 대한 결과 수가 표시됩니다.

![](../assets/palette-filter.png)

## 캔버스 {#canvas}

캔버스 **는** 여정 디자이너의 중앙 영역입니다. 이 영역에서는 활동을 삭제하고 구성할 수 있습니다. 캔버스에서 활동을 클릭하여 구성합니다. 오른쪽에 활동 구성 창이 열립니다. 오른쪽 상단에 있는 &quot;+&quot; 및 &quot;-&quot; 버튼을 사용하여 확대하거나 축소할 수 있습니다. 캔버스에서 모든 활동을 사용하면 활동을 제외한 다음 단계를 그 뒤에 추가할 수 있습니다( **[!UICONTROL End]** 이 페이지 [](../building-journeys/end-activity.md)참조).

![](../assets/journey39.png)

## 활동 구성 창 {#configuration_pane}

팔레트에서 활동을 클릭하면 **활동 구성 창이** 나타납니다. 필수 필드를 입력합니다. 활동을 삭제하려면 **[!UICONTROL Delete]** 아이콘을 클릭합니다. 수정 사항 **[!UICONTROL Cancel]** 을 취소하거나 확인하려면 을 **[!UICONTROL Ok]** 클릭하십시오. 활동을 삭제하려면 하나 또는 여러 개의 활동을 선택하고 백스페이스 키를 누를 수도 있습니다. Esc 키를 누르면 활동 구성 창이 닫힙니다.

캔버스에서 작업 및 이벤트 활동은 아래에 표시되는 이벤트 또는 작업의 이름과 함께 아이콘으로 표시됩니다. 활동 구성 창에서 **[!UICONTROL Label]** 필드를 사용하여 활동 이름에 접미사를 추가할 수 있습니다. 이러한 레이블은 이벤트 및 작업의 사용을 상황에 맞게 만드는 데 도움이 됩니다. 특히 여정에서 동일한 이벤트 또는 작업을 여러 번 사용하는 경우 더욱 그렇습니다. 보고에 추가한 레이블을 볼 수도 [!DNL Journey Orchestration] 있습니다. 조건 활동에 대한 레이블을 정의할 수도 있습니다.

![](../assets/journey59bis.png)

## 상단 막대 작업 {#top_actions}

경로 상태에 따라 오른쪽 상단 모서리에 있는 단추를 사용하여 여정에 대해 다른 작업을 수행할 수 있습니다. **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]** 이러한 단추는 활동이 선택되지 않은 경우에 나타납니다. 일부 단추는 상황에 따라 표시됩니다. 테스트 모드를 활성화하면 테스트 모드 로그 버튼이 나타납니다( [이 페이지](../building-journeys/testing-the-journey.md)참조). 여행이 라이브, 중지 또는 종료되면 보고 단추가 표시됩니다.

![](../assets/journey41.png)

## 캔버스에서 패스 사용 {#paths}

몇 가지 활동(**[!UICONTROL Condition]**, 활동 **[!UICONTROL Action]** )을 사용하면 오류나 시간 초과에 대한 대체 작업을 정의할 수 있습니다. 활동 구성 창에서 다음 상자를 선택합니다. **[!UICONTROL Add an alternative path in case of a timeout or an error]**. 활동 후에 다른 경로가 추가됩니다. 시간 초과 기간은 경로 속성에 정의됩니다(관리자 [가 이 페이지](../building-journeys/changing-properties.md) 참조). 예를 들어 이메일을 보내는 데 시간이 너무 오래 걸리거나 오류가 발생하면 SMS를 전송하기로 결정할 수 있습니다.

![](../assets/journey42.png)

다양한 활동(이벤트, 작업, 대기)을 통해 여러 경로를 그 뒤에 추가할 수 있습니다. 이렇게 하려면 활동 위에 커서를 놓고 &quot;+&quot; 기호를 클릭합니다. 이벤트와 대기 활동만 동시에 설정할 수 있습니다. 여러 이벤트가 동시에 설정되면 선택한 경로가 첫 번째 이벤트 중 하나가 됩니다.

이벤트를 들을 때는 이벤트를 무한히 기다리지 않는 것이 좋습니다. 이것은 의무적인 것이 아니라 단지 좋은 연습일 뿐이다. 특정 시간 동안에만 하나 또는 여러 개의 이벤트를 수신하려면 하나 또는 여러 개의 이벤트를 동시에 배치합니다. [이 섹션](../building-journeys/event-activities.md#section_vxv_h25_pgb)을 참조하십시오.

패스를 삭제하려면 해당 패스 위에 커서를 놓고 아이콘을 **[!UICONTROL Delete arrow]** 클릭합니다.

![](../assets/journey42ter.png)

캔버스에서 두 활동의 연결이 끊어지면 경고가 표시됩니다. 경고 아이콘 위에 커서를 두면 오류 메시지가 표시됩니다. 문제를 해결하려면 연결이 끊긴 활동을 이동하고 이전 활동에 연결하기만 하면 됩니다.

![](../assets/canvas-disconnected.png)

## 활동 복사 및 붙여넣기 {#copy-paste}

한 개 또는 여러 개의 여행 활동을 복사하고 동일한 여정 또는 다른 여정에 붙여넣을 수 있습니다. 이전 여정에서 이미 구성된 다양한 활동을 재사용하려는 경우 시간을 절약할 수 있습니다.

**중요 정보**

* 다양한 탭 및 브라우저에 복사/붙여넣을 수 있습니다. 동일한 인스턴스 내에서만 활동을 복사/붙여넣을 수 있습니다.
* 대상 경로에 다른 네임스페이스를 사용하는 이벤트가 있는 경우에는 이벤트를 복사/붙여 넣을 수 없습니다.
* 붙여넣은 활동은 대상 여정에 존재하지 않는 데이터를 참조할 수 있습니다. 예를 들어 다른 샌드박스에 복사/붙여넣기를 수행하면 됩니다. 항상 오류를 확인하고 필요한 사항을 조정합니다.
* 작업을 실행 취소할 수 없습니다. 붙여넣은 활동을 삭제하려면 해당 활동을 선택하고 삭제해야 합니다. 따라서 필요한 활동만 복사하기 전에 선택해야 합니다.
* 모든 여정에서 활동을 복사할 수 있으며, 읽기 전용 활동도 복사할 수 있습니다.
* 연결되어 있지 않은 활동이라도 선택할 수 있습니다. 연결된 활동은 붙여넣은 후에도 계속 연결됩니다.

다음은 활동을 복사/붙여넣는 단계입니다.

1. 여정 열어
1. 클릭하는 동안 마우스를 이동하여 복사할 활동을 선택합니다. Ctrl/Command **키를 누른 상태에서 각 활동을 클릭할 수도** 있습니다. 모든 활동을 **선택하려면 Ctrl/Command** + A를 사용합니다.
   ![](../assets/copy-paste1.png)
1. Ctrl/ **Command + C를 누릅니다**.
활동을 하나만 복사하려는 경우 해당 활동을 클릭하고 활동 구성 창 왼쪽 상단에 있는 **복사** 아이콘을 사용할 수 있습니다.
   ![](../assets/copy-paste2.png)
1. 여정에서 Ctrl/ **Command + V** 를 눌러 기존 노드에 연결하지 않고 활동을 붙여넣습니다. 붙여넣은 활동은 같은 순서로 배치됩니다. 붙여넣은 후에는 활동이 선택된 상태로 유지되므로 쉽게 이동할 수 있습니다. 빈 자리 표시자에 커서를 놓고 **Ctrl/Command + V를 누를 수도 있습니다**. 붙여넣은 활동은 노드에 연결됩니다.
   ![](../assets/copy-paste3.png)

