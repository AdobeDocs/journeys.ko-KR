---
title: 액세스 관리
description: 액세스 관리에 대한 자세한 내용
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: a3114ffe7c087645e97caf3a77e7649d922945eb
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---


# 액세스 관리{#concept_rfj_wpt_52b}

## 액세스 관리 기본 정보 {#about-access-management}

[!DNL Journey Orchestration] 사용자가 액세스할 수 있는 인터페이스의 일부를 정의하는 권한을 사용자에게 할당할 수 있습니다.

관리 콘솔에 액세스할 수 있는 관리자가 관리할 수 있습니다. 관리 콘솔에 대한 자세한 내용은 이 [설명서를 참조하십시오](https://helpx.adobe.com/enterprise/managing/user-guide.html).

관리 콘솔에서 다음 제품 프로필 중 하나를 사용자에게 할당할 수 있습니다.

* **[!UICONTROL Limited Access User]**: 읽기 전용 액세스 권한을 가진 사용자. 이 제품 프로필에는 다음 권한이 포함됩니다.
   * 여정 읽기
   * 보고서 읽기

* **[!UICONTROL Administrators]**: 관리 메뉴에 대한 액세스 권한이 있는 사용자이며, 여기에는 여행, 이벤트 및 보고서가 관리됩니다. 이 제품 프로필에는 다음 권한이 포함됩니다.
   * 여정 관리
   * 게시 여정
   * 이벤트, 데이터 소스 및 작업 관리
   * 보고서 관리
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]** 는 Adobe Campaign Standard에서 트랜잭션 메시지(또는 메시지 템플릿)를 작성, 에디션 및 게시할 수 있는 유일한 제품 프로필입니다. 이 제품 프로필은 Adobe Campaign Standard를 사용하여 여행 중에 메시지를 전송하는 경우에 필요합니다.

* **[!UICONTROL Standard User]**: 경로 관리와 같은 기본적인 액세스 권한이 있는 사용자 이 제품 프로필에는 다음 권한이 포함됩니다.
   * 여정 관리
   * 게시 여정
   * 보고서 관리

또한 기본 프로필이 사용자를 관리하기에 충분하지 않은 경우 자체 제품 프로필을 만들 수도 있습니다.
사용자는 항상 제품 프로필에 연결되어 있어야 하며 다음과 같은 특정 빌드 권한을 할당할 수 있습니다.

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

권한 간의 호환성 및 다양한 기능 [!DNL Journey Orchestration]을 확인할 수 있습니다.

![](../assets/journey_permission.png)

## 제품 프로필 만들기 {#create-product-profile}

[!DNL Journey Orchestration] 고유한 제품 프로필을 만들고 사용자에게 일련의 권한 및 샌드박스를 할당할 수 있도록 해줍니다. 제품 프로필을 사용하면 인터페이스에서 특정 기능 또는 개체에 대한 액세스를 승인하거나 거부할 수 있습니다.

샌드박스를 만들고 관리하는 방법에 대한 자세한 내용은 [Adobe Experience Platform 설명서를 참조하십시오](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html).

제품 프로필을 만들고 권한 및 샌드박스 세트를 지정하려면:

1. 관리 콘솔에서 선택합니다 **[!UICONTROL Journey Orchestration]**. 탭에서 **[!UICONTROL Product profile]** 을 클릭합니다 **[!UICONTROL New Profile]**.

1. 새 제품 프로필 **[!UICONTROL Profile Name]** 에 **[!UICONTROL Description]** 및 을 추가합니다. 프로필을 **[!UICONTROL Display name]** 변경하려면 선택을 취소하고 **[!UICONTROL Same as Profile Name]** 을 입력합니다 **[!UICONTROL Display name]**.

1. 이 제품 프로필에서 추가 또는 제거될 때 사용자가 이메일을 통해 알림을 받을지 여부를 **[!UICONTROL User Notifications]** 선택합니다.

1. 완료되면 을 클릭합니다 **[!UICONTROL Done]**. 이제 새 제품 프로필이 만들어집니다.

1. 새 제품 프로필을 선택하여 권한 관리를 시작합니다. 탭에서 **[!UICONTROL Users]** 제품 프로필에 사용자를 추가합니다. For more on this, refer to this [page](../about/access-management.md#assigning-product-profile).

1. 위의 설명과 동일한 단계를 수행하여 제품 프로필 **[!UICONTROL Admin]** 에 추가합니다.

1. 탭에서 **[!UICONTROL Permissions]** 두 카테고리 중 하나를 **[!UICONTROL Sandbox]** 선택하거나 **[!UICONTROL Authoring]** 페이지를 열고 제품 프로필에 대한 권한을 추가 **[!UICONTROL Edit Permissions]** 또는 제거합니다.

1. 권한 카테고리에서 **[!UICONTROL Sandbox]** 제품 프로필에 할당할 샌드박스를 선택합니다. 프로필 **[!UICONTROL Available Permissions Items]**&#x200B;에 샌드박스를 지정하려면 아래에서 더하기(+) 아이콘을 클릭합니다.

   >[!NOTE]
   >
   >플랫폼 샌드박스는 베타 기능입니다.
   <br>샌드박스에 대한 자세한 내용은 이 [섹션을 참조하십시오](../about/access-management.md#sandboxes).

1. 필요한 경우 아래 **[!UICONTROL Included Permission Items]**&#x200B;에서 제품 프로필에 대한 권한을 제거하려면 X 아이콘을 클릭합니다.

1. 권한 카테고리에서 **[!UICONTROL Authoring]** 위와 동일한 단계를 수행하여 제품 프로필에 권한을 추가합니다.
   <br>권한 간의 권한 및 호환성 [!DNL Journey Orchestration]에 대한 자세한 내용은 이 [섹션을 참조하십시오](../about/access-management.md#about-access-management).

1. 완료되면 을 클릭합니다 **[!UICONTROL Save]**.

이제 제품 프로필이 만들어지고 구성됩니다. 이제 이 프로필에 연결된 사용자가 연결할 수 있습니다 [!DNL Journey Orchestration].

## 제품 프로필 할당 {#assigning-product-profile}

제품 프로필은 조직 내에서 동일한 권한을 공유하는 사용자 집합에 할당됩니다.
권한이 할당된 모든 기본 제품 프로필 목록은 이 섹션에서 찾을 수 있습니다.

사용자가 액세스할 제품 프로필을 지정하려면 다음을 수행합니다 [!DNL Journey Orchestration].

1. 관리 콘솔에서 선택합니다 **[!UICONTROL Journey Orchestration]**.

   ![](../assets/user_management.png)

1. 새 사용자가 연결될 제품 프로필을 선택합니다.

   ![](../assets/user_management_2.png)

1. **[!UICONTROL Add user]**&#x200B;을 클릭합니다.

   또한 새 사용자를 사용자 그룹에 추가하여 공유 권한 집합을 세부적으로 조정할 수도 있습니다. For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. 새 사용자의 이메일 주소를 입력한 다음 을 클릭합니다 **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

그러면 사용자가 인스턴스로 리디렉션되는 이메일을 [!DNL Journey Orchestration] 수신하게 됩니다.

## 샌드박스 사용 {#sandboxes}

>[!NOTE]
>
>플랫폼 샌드박스는 베타 기능입니다.

[!DNL Journey Orchestration] 인스턴스를 샌드박스라는 분리된 가상 환경으로 분할할 수 있습니다.
샌드박스는 관리 콘솔에서 제품 프로필을 통해 할당됩니다. 샌드박스를 할당하는 방법에 대한 자세한 내용은 이 [섹션을 참조하십시오](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] 는 지정된 조직에 대해 만들어진 플랫폼 샌드박스를 반영합니다.
Adobe Experience Platform 인스턴스에서 플랫폼 샌드박스를 생성하거나 재설정할 수 있습니다. 자세한 단계는 [샌드박스 사용자 안내서를](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) 참조하십시오.

화면의 왼쪽 상단에 샌드박스 전환기 컨트롤이 있습니다. 샌드박스에서 다른 샌드박스로 전환하려면 전환기에서 현재 활성 샌드박스를 클릭하고 드롭다운 목록에서 다른 샌드박스를 선택합니다.
