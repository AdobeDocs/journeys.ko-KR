---
product: adobe campaign
title: 테스트 프로필 만들기
description: 테스트 프로필 만들기에 대해 알아보기
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 3%

---

# 테스트 프로필 만들기 {#create-test-profiles}


>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home)를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer로 대체된 레거시 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer에 대한 액세스에 대해 질문이 있는 경우 계정 팀에 문의하십시오._


여정에서 테스트 모드를 사용할 때 테스트 프로필이 필요합니다. 테스트 모드를 사용하는 방법에 대한 자세한 내용은 이 섹션을[&#128279;](../building-journeys/testing-the-journey.md) 참조하십시오.

Adobe Experience Platform 에서 테스트 프로필을 만드는 방법에는 여러 가지가 있습니다. 이 문서에서는 csv 파일[&#128279;](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) 업로드[와 API 호출](../building-journeys/creating-test-profiles.md#create-test-profiles-api) 사용의 두 가지 방법을 포커스 합니다. 데이터 집합에 json 파일을 업로드할 수도 있습니다. [데이터 수집 설명서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)를 참조하세요.

이러한 가져오기 메서드를 사용하면 프로필 속성을 업데이트할 수도 있습니다. 이렇게 하면 기존 프로필을 테스트 프로필로 만들 수 있습니다. 단순히 유사한 파일 또는 API 호출을 사용하고 값이 &quot;true&quot;인 &quot;testProfile&quot; 필드만 포함하면 됩니다.

테스트 프로필을 만드는 것은 Adobe Experience Platform에서 일반 프로필을 만드는 것과 비슷합니다. 자세한 내용은 [실시간 고객 프로필 설명서](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko)를 참조하세요.

## 전제 조건{#test-profile-prerequisites}

프로필을 만들 수 있으려면 먼저 Adobe Experience Platform에서 스키마와 데이터 세트를 만들어야 합니다.

먼저 **스키마를 만들어야**. 다음 단계를 수행하십시오.

1. Adobe Experience Platform의 왼쪽 메뉴에서 **[!UICONTROL Schemas]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-0.png)
1. 오른쪽 상단에서 **[!UICONTROL Create schema]**&#x200B;을(를) 클릭한 다음 스키마 유형(예: **[!UICONTROL XDM Individual Profile]**)을 선택합니다.
   ![](../assets/test-profiles-1.png)
1. 스키마 이름을 선택합니다.
1. **[!UICONTROL Mixins]** 섹션에서 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-1-bis.png)
1. 적절한 mixin을 선택합니다. **[!UICONTROL Profile test details]** mixin을 추가하세요. **[!UICONTROL Add mixin]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-1-ter.png)
mixin 목록이 스키마 개요 화면에 표시됩니다.
   ![](../assets/test-profiles-2.png)
1. 필드 목록에서 기본 ID로 정의할 필드를 클릭합니다.
   ![](../assets/test-profiles-3.png)
1. **[!UICONTROL Field properties]** 오른쪽 패널에서 **[!UICONTROL Identity]** 및 **[!UICONTROL Primary Identity]** 옵션을 확인하고 네임스페이스를 선택합니다. 기본 자격 증명을 이메일 주소로 사용하려면 네임스페이스를 **[!UICONTROL Email]** 선택합니다. **[!UICONTROL Apply]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-4.png)
1. 스키마를 선택하고 에서 옵션을 활성화 **[!UICONTROL Profile]** 합니다 **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

>[!NOTE]
>
>스키마 생성에 대한 자세한 내용은 XDM 설명서를[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites) 참조하십시오.

**그런 다음 프로필을 가져올 데이터 세트** 세트를 만들어야 합니다. 다음 단계를 수행하십시오.

1. Adobe Experience Platform에서 왼쪽 메뉴에서 **[!UICONTROL Datasets]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Create dataset]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-6.png)
1. **[!UICONTROL Create dataset from schema]**&#x200B;을(를) 선택하십시오.
   ![](../assets/test-profiles-7.png)
1. 이전에 만든 스키마를 선택한 다음 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-8.png)
1. 이름을 선택한 다음 **[!UICONTROL Finish]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-9.png)
1. **[!UICONTROL Profile]** 옵션을 사용하도록 설정합니다.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 데이터 집합 만들기에 대한 자세한 내용은 [카탈로그 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)를 참조하세요.

## csv 파일을 사용하여 테스트 프로필 만들기{#create-test-profiles-csv}

Adobe Experience Platform에서는 다른 프로필 필드가 포함된 csv 파일을 데이터 세트에 업로드하여 프로필을 만들 수 있습니다. 이것이 가장 쉬운 방법입니다.

1. 스프레드시트 소프트웨어를 사용하여 간단한 csv 파일을 만듭니다.
1. 필요한 각 필드에 하나의 열을 추가합니다. 기본 ID 필드(&quot;위의 예에서 &quot;personID&quot;)와 &quot;testProfile&quot; 필드를 &quot;true&quot;로 설정해야 합니다.
   ![](../assets/test-profiles-11.png)
1. 프로필당 한 줄을 추가하고 각 필드의 값을 입력합니다.
   ![](../assets/test-profiles-12.png)
1. 스프레드시트를 csv 파일로 저장. 쉼표가 구분 기호로 사용되는지 확인합니다.
1. Adobe Experience Platform의 왼쪽 메뉴에서 을 클릭합니다 **[!UICONTROL Workflows]**.
   ![](../assets/test-profiles-14.png)
1. 을 선택하고 **[!UICONTROL Map CSV to XDM schema]**&#x200B;을 클릭합니다 **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. 프로필을 가져올 데이터 세트 를 선택합니다. **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-17.png)
1. **[!UICONTROL Choose files]**&#x200B;을(를) 클릭하고 csv 파일을 선택하십시오. 파일이 업로드되면 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-18.png)
1. 소스 csv 필드를 스키마 필드에 매핑한 다음 **[!UICONTROL Finish]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-19.png)
1. 데이터 가져오기가 시작됩니다. 상태가 **[!UICONTROL Processing]**&#x200B;에서 **[!UICONTROL Success]**(으)로 이동합니다. 오른쪽 상단의 **[!UICONTROL Preview data set]**&#x200B;을(를) 클릭합니다.
   ![](../assets/test-profiles-20.png)
1. 테스트 프로필이 올바르게 추가되었는지 확인합니다.
   ![](../assets/test-profiles-21.png)

테스트 프로필이 추가되었으며 이제 여정 테스트 시 사용할 수 있습니다. [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.
>[!NOTE]
>
> csv 가져오기에 대한 자세한 내용은 [데이터 수집 설명서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)를 참조하세요.

## API 호출을 사용하여 테스트 프로필 만들기{#create-test-profiles-api}

API 호출을 통해 테스트 프로필을 만들 수도 있습니다. 이 [페이지](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko)를 참조하십시오.

&quot;프로필 테스트 세부 사항&quot; mixin이 포함된 프로필 스키마를 사용해야 합니다. testProfile 플래그는 이 mixin의 일부입니다.

프로필을 만들 때 다음 값을 전달하십시오. testProfile = true.

기존 프로필을 업데이트하여 testProfile 플래그를 &quot;true&quot;로 변경할 수도 있습니다.

다음은 테스트 프로필을 만들기 위한 API 호출의 예입니다.

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
