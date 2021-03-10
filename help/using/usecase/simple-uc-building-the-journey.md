---
product: adobe campaign
solution: Journey Orchestration
title: 여정 구축
description: 간단한 사용 사례 여정을 구축하는 방법 살펴보기
feature: 여정
role: 비즈니스 전문가
level: 중간
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 36%

---


# 여정 구축{#concept_eyw_mcy_w2b}

이제 **비즈니스 사용자**&#x200B;가 여정을 구축할 수 있습니다. 여정에는 다음 활동이 있는 하나의 경로만 포함됩니다.

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**:스파 봉지 근처를 돌아보면 자동으로 이벤트를 받게 되고 그 사람을 위해 여정이 시작됩니다.
* 사람이 여성인지 확인하는 **[!UICONTROL Condition]** 활동
* **[!UICONTROL Email]** 활동(Adobe Campaign Standard 사용)
* **[!UICONTROL End]** 활동

>[!NOTE]
>
>**[!UICONTROL Push]** 및 **[!UICONTROL Email]** 활동은 Adobe Campaign Standard를 보유한 경우에만 팔레트에서 사용할 수 있습니다.

여정 작성 방법에 대한 자세한 내용은 [이 페이지](../building-journeys/journey.md)를 참조하십시오.

1. 상단 메뉴에서 **[!UICONTROL Home]** 탭과 **[!UICONTROL Create]**&#x200B;을(를) 클릭하여 새 여정을 만듭니다.

   ![](../assets/journey31.png)

1. 오른쪽에 표시되는 구성 창에서 여정의 속성을 편집합니다. &quot;스파 여정&quot;으로 이름을 지정하고 1일부터 12월 31일까지 한 달 동안 유지되도록 설정합니다.

   ![](../assets/journeyuc1_8.png)

1. 팔레트에서 캔버스로 &quot;SpaBeacon&quot; 이벤트를 드래그하여 놓아 여정 디자인을 시작합니다. 팔레트에서 이벤트를 두 번 클릭하여 캔버스에 추가할 수도 있습니다.

   ![](../assets/journeyuc1_9.png)

1. 이제 그 사람이 여성인지 확인하는 조건을 추가합시다. 조건 활동을 여정으로 끌어다 놓습니다.

   ![](../assets/journeyuc1_10.png)

1. **[!UICONTROL Data Source Condition]** 유형을 선택하고 **[!UICONTROL Expression]** 필드를 클릭합니다. 캔버스에서 화살표에 나타날 조건 레이블을 정의할 수도 있습니다.

   ![](../assets/journeyuc1_11.png)

1. 단순 표현식 편집기를 사용하여 성별 필드(_person > 성별_)를 찾은 다음 오른쪽에 놓아 다음 조건을 만듭니다.&quot;성별&quot;은 &quot;여성&quot;과 같다.

   ![](../assets/journeyuc1_12.png)

1. **[!UICONTROL Email]** 활동을 삭제하고 &quot;Spa 할인&quot; 트랜잭션 메시지 템플릿을 선택합니다. 이 템플릿은 Adobe Campaign을 사용하여 디자인되었습니다. 이 [페이지](https://docs.adobe.com/content/help/ko-KR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)를 참조하십시오.

   ![](../assets/journeyuc1_13.png)

1. **[!UICONTROL Email]** 필드 내부를 클릭하고 데이터 소스에서 이메일 주소를 선택합니다.

   ![](../assets/journeyuc1_14.png)

1. 동일한 방식으로 데이터 소스의 이름 및 성 개인화 필드를 정의합니다.

   ![](../assets/journeyuc1_15.png)

1. **[!UICONTROL End]** 활동을 삭제합니다.

   ![](../assets/journeyuc1_17.png)

1. 테스트 프로필을 사용하여 여정을 전환 및 테스트합니다. **[!UICONTROL Test]** 오류가 있는 경우 테스트 모드를 비활성화하고 여정를 수정한 후 다시 테스트하십시오. 테스트 모드에 대한 자세한 내용은 [이 페이지](../building-journeys/testing-the-journey.md)를 참조하십시오.

   ![](../assets/journeyuc1_18bis.png)

1. 테스트가 확정되면 오른쪽 상단 드롭다운 메뉴에서 여정을 게시할 수 있습니다.

   ![](../assets/journeyuc1_18.png)

다음번엔 스파 비콘 근처에서 오면 즉시 맞춤 이메일을 받는다.
