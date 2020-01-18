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
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 액세스 관리{#concept_rfj_wpt_52b}

## 액세스 관리 기본 정보 {#about-access-management}

제품 프로필은 조직 내에서 동일한 권한을 공유하는 사용자 집합에 할당됩니다.

관리 콘솔에서 다음 제품 프로필 중 하나를 사용자에게 할당할 수 있습니다.

* **[!UICONTROL Limited Access User]**:사용자 및 보고서에 대한 읽기 전용 액세스 권한이 있습니다. 이 제품 프로필에는 다음 권한이 포함되어 있습니다.
   * 여행 보기
   * 보고서 읽기

* **[!UICONTROL Administrators]**:관리 메뉴에 대한 액세스 권한이 있는 사용자이며 여행, 이벤트 및 보고서를 관리할 수 있습니다. 이 제품 프로필에는 다음 권한이 포함되어 있습니다.
   * 여정 관리 및 실행
   * 이벤트, 데이터 소스 및 작업 관리
   * 보고서 관리
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**는 Adobe Campaign Standard에서 트랜잭션 메시지(또는 메시지 템플릿)를 만들고, 에디션하고, 게시할 수 있는 유일한 제품 프로필입니다. 이 제품 프로필은 Adobe Campaign Standard를 사용하여 여행 중에 메시지를 보내는 경우에 필요합니다.

* **[!UICONTROL Standard User]**:고객 여정 관리와 같은 기본적인 액세스 권한이 있는 사용자 이 제품 프로필에는 다음 권한이 포함되어 있습니다.
   * 여정 관리 및 실행
   * 보고서 관리

권한 [및 고객 여정](../assets/do-not-localize/acs_rights_journeys.pdf) 오케스트레이션의 다양한 기능 간의 호환성을 확인할 수 있습니다.

## 제품 프로필 할당 {#assigning-product-profile}

제품 프로필은 관리 콘솔에서 관리됩니다. 자세한 내용은 Admin Console 설명서를 [참조하십시오](https://helpx.adobe.com/enterprise/managing/user-guide.html).

사용자가 여정 오케스트레이션에 액세스할 수 있도록 제품 프로필을 지정하려면:

1. 관리 콘솔에서 을 **[!UICONTROL Journey orchestration]**선택합니다.

   ![](../assets/user_management.png)

1. 새 사용자가 연결될 제품 프로필을 선택합니다.

   ![](../assets/user_management_2.png)

1. 클릭 **[!UICONTROL Add user]**.

   새 사용자를 사용자 그룹에 추가하여 공유 권한 집합을 세부적으로 조정할 수도 있습니다. 자세한 내용은 이 [페이지를](https://helpx.adobe.com/enterprise/using/user-groups.html)참조하십시오.

   ![](../assets/user_management_3.png)

1. 새 사용자의 이메일 주소를 입력한 다음 을 클릭합니다 **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

그러면 사용자가 여정 오케스트레이션 인스턴스로 리디렉션되는 이메일을 수신하게 됩니다.