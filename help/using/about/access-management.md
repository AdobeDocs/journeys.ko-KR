---
product: adobe campaign
title: 액세스 관리
description: 액세스 관리에 대해 자세히 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: a551efa5-c0d8-4138-96ca-fb407fad8c59
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 95%

---

# 액세스 관리{#concept_rfj_wpt_52b}

## 액세스 관리 기본 정보 {#about-access-management}

[!DNL Journey Orchestration]에서는 사용자에게 권한 집합을 할당함으로써 사용자가 액세스할 수 있는 인터페이스 부분을 정의할 수 있습니다.

권한 집합은 Admin Console에 액세스할 수 있는 관리자가 관리할 수 있습니다. Admin Console에 대한 자세한 내용은 이 [설명서](https://helpx.adobe.com/kr/enterprise/managing/user-guide.html)를 참조하십시오.

[!DNL Journey Orchestration]에 액세스할 수 있는 사용자의 자격은 다음과 같습니다.

* [!DNL Journey Orchestration] 권한과 연관된 [!DNL Journey Orchestration] **[!UICONTROL product profile]**&#x200B;에 속해 있어야 합니다.
* [!DNL Adobe Experience Platform] **[!UICONTROL product profile]**&#x200B;에 속해 있어야 합니다. 갖고 있어야 하는 필수 권한은 없습니다. [!DNL Journey Orchestration] 인터페이스에서 플랫폼 세그먼트를 만들고 편집하려면 사용자에게 **[!UICONTROL profile management]** 권한이 있어야 합니다. 자세한 내용은 이 ](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#adobe-admin-console)페이지[를 참조하십시오.

Admin Console에서 다음의 기본 제품 프로필 중 하나를 사용자에게 할당할 수 있습니다.

* **[!UICONTROL Limited Access User]**: 여정 및 보고서에 대한 읽기 전용 액세스 권한을 가진 사용자. 이 제품 프로필에는 다음과 같은 권한이 포함됩니다.
   * 여정 읽기
   * 보고서 읽기

* **[!UICONTROL Administrators]**: 관리 메뉴에 대한 액세스 권한을 가지고 있으며 여정, 이벤트 및 보고서를 관리할 수 있는 사용자. 이 제품 프로필에는 다음과 같은 권한이 포함됩니다.
   * 여정 관리
   * 여정 게시
   * 이벤트, 데이터 소스 및 작업 관리
   * 보고서 관리

  >[!NOTE]
  >
  >**[!UICONTROL Administrators]**&#x200B;는 Adobe Campaign Standard에서 트랜잭션 메시지(또는 메시지 템플릿)를 작성, 편집, 게시할 수 있는 유일한 제품 프로필입니다. Adobe Campaign Standard을 사용하여 여정에서 메시지를 보내는 경우에 이 제품 프로필이 필요합니다. Admin Console에서 이름을 바꾸면 안 됩니다.

* **[!UICONTROL Standard User]**: 여정 관리와 같은 기본적인 액세스 권한을 가진 사용자. 이 제품 프로필에는 다음과 같은 권한이 포함됩니다.
   * 여정 관리
   * 여정 게시
   * 보고서 관리
   * 이벤트, 데이터 소스 및 작업 읽기

기본 프로필이 사용자를 관리하기에 충분하지 않은 경우 제품 프로필을 직접 만들 수도 있습니다.
다음과 같은 특정 기본 권한을 할당할 수 있도록 사용자는 항상 제품 프로필에 연결되어 있어야 합니다.

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

권한과 여러 [!DNL Journey Orchestration] 기능 간의 호환성은 아래에서 확인할 수 있습니다.

![](../assets/do-not-localize/journey_permission.png)

## 제품 프로필 만들기 {#create-product-profile}

[!DNL Journey Orchestration]에서는 제품 프로필을 직접 만들고 권한 집합 및 샌드박스를 사용자에게 할당할 수 있습니다. 제품 프로필을 사용하면 인터페이스에서 특정 기능 또는 개체에 대한 액세스를 승인하거나 거부할 수 있습니다.

샌드박스를 만들고 관리하는 방법에 대한 자세한 내용은 [Adobe Experience Platform 설명서](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ko-KR)를 참조하십시오.

제품 프로필을 만들고 권한 집합 및 샌드박스를 할당하려면 다음과 같이 하십시오.

1. Admin Console에서 **[!UICONTROL Journey Orchestration]**&#x200B;을 선택합니다. **[!UICONTROL Product profile]** 탭에서 **[!UICONTROL New Profile]**&#x200B;을(를) 클릭합니다.

   ![](../assets/do-not-localize/user_management_5.png)

1. 새 제품 프로필에 **[!UICONTROL Profile Name]** 및 **[!UICONTROL Description]**&#x200B;을 추가합니다. 프로필의 **[!UICONTROL Display name]**&#x200B;을 변경하려면 **[!UICONTROL Same as Profile Name]** 선택을 취소하고 원하는 **[!UICONTROL Display name]**&#x200B;을 입력합니다.

1. 이 제품 프로필에 추가되거나 제거될 때 사용자에게 이메일로 알릴 것인지 여부를 **[!UICONTROL User Notifications]** 카테고리에서 선택합니다.

1. 완료되었으면 **[!UICONTROL Done]**&#x200B;을 클릭합니다. 이제 새 제품 프로필이 생성되었습니다.

   ![](../assets/do-not-localize/user_management_1.png)

1. 새 제품 프로필을 선택하여 권한 관리를 시작합니다. **[!UICONTROL Users]** 탭에서 사용자를 제품 프로필에 추가합니다. 자세한 내용은 이 ](../about/access-management.md#assigning-product-profile)페이지[를 참조하십시오.

1. 위의 설명과 동일한 단계를 수행하여 **[!UICONTROL Admin]**&#x200B;을 제품 프로필에 추가합니다.

1. **[!UICONTROL Permissions]** 탭에서 **[!UICONTROL Sandbox]** 또는 **[!UICONTROL Authoring]** 카테고리 중 하나를 선택하여 **[!UICONTROL Edit Permissions]** 페이지를 열고 제품 프로필에 권한을 추가하거나 제거합니다.

   ![](../assets/do-not-localize/user_management_7.png)

1. **[!UICONTROL Sandboxes]** 권한 카테고리에서 제품 프로필에 할당할 샌드박스를 선택합니다. **[!UICONTROL Available Permissions Items]** 아래에서 더하기(+) 아이콘을 클릭하여 샌드박스를 프로필에 할당합니다. 샌드박스에 대한 자세한 내용은 이 [섹션](../about/access-management.md#sandboxes)을 참조하십시오.

   ![](../assets/do-not-localize/user_management_8.png)

1. 필요한 경우 **[!UICONTROL Included Permission Items]** 아래에서 옆에 있는 X 아이콘을 클릭하여 제품 프로필에서 권한을 제거합니다.

   ![](../assets/do-not-localize/user_management_9.png)

1. **[!UICONTROL Authoring]** 권한 카테고리에서 위와 동일한 단계를 수행하여 제품 프로필에 권한을 추가합니다.
   <br>권한과 여러 [!DNL Journey Orchestration] 기능 간의 호환성에 대한 자세한 내용은 이 [섹션](../about/access-management.md#about-access-management)을 참조하십시오.

   ![](../assets/do-not-localize/user_management_10.png)

1. 완료되었으면 **[!UICONTROL Save]**&#x200B;을 클릭합니다.

이제 제품 프로필이 생성되고 구성되었습니다. 이 프로필에 연결된 사용자가 이제 [!DNL Journey Orchestration]에 연결할 수 있습니다.

## 제품 프로필 할당 {#assigning-product-profile}

제품 프로필은 조직 내에서 동일한 권한을 공유하는 사용자 집합에 할당됩니다.
권한이 할당된 모든 기본 제품 프로필의 목록을 이 섹션에서 확인할 수 있습니다.

사용자가 [!DNL Journey Orchestration]에 액세스할 수 있도록 제품 프로필을 할당하려면 다음과 같이 하십시오.

1. Admin Console에서 **[!UICONTROL Journey Orchestration]**&#x200B;을 선택합니다.

   ![](../assets/do-not-localize/user_management.png)

1. 새 사용자가 연결될 제품 프로필을 선택합니다.

   ![](../assets/do-not-localize/user_management_2.png)

1. **[!UICONTROL Add user]**&#x200B;을(를) 클릭합니다.

   새 사용자를 사용자 그룹에 추가하여 공유 권한 집합을 세부 조정할 수도 있습니다. 자세한 내용은 이 ](https://helpx.adobe.com/kr/enterprise/using/user-groups.html)페이지[를 참조하십시오.

   ![](../assets/do-not-localize/user_management_3.png)

1. 새 사용자의 이메일 주소를 입력한 다음 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](../assets/do-not-localize/user_management_4.png)

그러면 [!DNL Journey Orchestration] 인스턴스로 리디렉션되는 이메일을 사용자가 받게 됩니다.

## 샌드박스 사용 {#sandboxes}

[!DNL Journey Orchestration]에서는 인스턴스를 샌드박스라는 분리된 가상 환경으로 분할할 수 있습니다.
샌드박스는 Admin Console에서 제품 프로필을 통해 할당됩니다. 샌드박스를 할당하는 방법에 대한 자세한 내용은 이 [섹션](../about/access-management.md#create-product-profile)을 참조하십시오.

[!DNL Journey Orchestration] (은)는 해당 조직을 위해 만들어진 Adobe Experience Platform 샌드박스를 반영합니다.
Adobe Experience Platform 인스턴스에서 Adobe Experience Platform 샌드박스를 만들거나 재설정할 수 있습니다. 자세한 단계는 [샌드박스 사용 안내서](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ko)를 참조하십시오.

화면의 왼쪽 상단에 샌드박스 전환기 컨트롤이 있습니다. 한 샌드박스에서 다른 샌드박스로 전환하려면 전환기에서 현재 활성 샌드박스를 클릭하고 드롭다운 목록에서 다른 샌드박스를 선택하십시오.
