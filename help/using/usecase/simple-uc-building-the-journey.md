---
product: adobe campaign
title: 여정 구축 - 간소화
description: 간단한 사용 사례 여정을 작성하는 방법 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 27%

---

# 여정 구축{#concept_eyw_mcy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home)를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


이제 **비즈니스 사용자**&#x200B;가 여정을 구축할 수 있습니다. 여정은 다음 활동이 있는 하나의 경로만 포함합니다.

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: 사용자가 Spa 비콘 근처에 있으면 시스템에서 이벤트를 수신하고 해당 사용자에 대한 여정이 시작됩니다.
* 대상이 여성인지 확인하기 위한 **[!UICONTROL Condition]** 활동
* **[!UICONTROL Email]** 활동(Adobe Campaign Standard 사용)
* **[!UICONTROL End]** 활동

>[!NOTE]
>
>**[!UICONTROL Push]** 및 **[!UICONTROL Email]** 활동은 Adobe Campaign Standard를 보유한 경우에만 팔레트에서 사용할 수 있습니다.

여정 빌드 방법에 대한 자세한 내용은 [이 페이지](../building-journeys/journey.md)를 참조하세요.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭과 **[!UICONTROL Create]**&#x200B;을(를) 클릭하여 새 여정을 만듭니다.

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 여정의 속성을 편집합니다. 이름을 &quot;Spa 여정&quot;로 지정하고 12월 1일부터 31일까지 한 달 동안 지속되도록 설정합니다.

   ![](../assets/journeyuc1_8.png)

1. 팔레트에서 캔버스로 &quot;SpaBeacon&quot; 이벤트를 끌어서 놓아 여정 디자인을 시작합니다. 팔레트에서 이벤트를 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journeyuc1_9.png)

1. 이제 그 사람이 여성임을 확인하는 조건을 추가해 봅시다. 조건 활동을 여정으로 끌어다 놓습니다.

   ![](../assets/journeyuc1_10.png)

1. **[!UICONTROL Data Source Condition]** 유형을 선택하고 **[!UICONTROL Expression]** 필드를 클릭합니다. 캔버스에서 화살표에 표시될 조건 레이블을 정의할 수도 있습니다.

   ![](../assets/journeyuc1_11.png)

1. 단순 표현식 편집기를 사용하여 성별 필드(_사람 > 성별_)를 찾은 다음 오른쪽에 놓아 다음 조건을 만듭니다. &quot;gender는 &quot;Female&quot;과 같습니다.

   ![](../assets/journeyuc1_12.png)

1. **[!UICONTROL Email]** 활동을 삭제하고 &quot;Spa 할인&quot; 트랜잭션 메시지 템플릿을 선택하십시오. 이 템플릿은 Adobe Campaign을 사용하여 디자인되었습니다. 이 [페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ko)를 참조하세요.

   ![](../assets/journeyuc1_13.png)

1. **[!UICONTROL Email]** 필드 내부를 클릭하고 데이터 원본에서 전자 메일 주소를 선택합니다.

   ![](../assets/journeyuc1_14.png)

1. 동일한 방식으로 데이터 소스에서 이름 및 성 개인화 필드를 정의합니다.

   ![](../assets/journeyuc1_15.png)

1. **[!UICONTROL End]** 활동을 삭제합니다.

   ![](../assets/journeyuc1_17.png)

1. **[!UICONTROL Test]** 토글을 클릭하고 테스트 프로필을 사용하여 여정을 테스트합니다. 오류가 있는 경우 테스트 모드를 비활성화하고 여정를 수정한 후 다시 테스트하십시오. 테스트 모드에 대한 자세한 내용은 [이 페이지](../building-journeys/testing-the-journey.md)를 참조하세요.

   ![](../assets/journeyuc1_18bis.png)

1. 테스트가 확정되면 오른쪽 상단 드롭다운 메뉴에서 여정을 게시할 수 있습니다.

   ![](../assets/journeyuc1_18.png)

다음 번에 여성이 스파 비콘 근처에 걷게 되면 즉시 &quot;스파 할인&quot; 개인화된 이메일을 받게 됩니다.
