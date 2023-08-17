---
product: adobe campaign
title: 테스트 프로필 만들기
description: 테스트 프로필 만들기에 대해 알아보기
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 5%

---

# 테스트 프로필 만들기 {#create-test-profiles}

여정에서 테스트 모드를 사용할 때 테스트 프로필이 필요합니다. 테스트 모드를 사용하는 방법에 대해 알아보려면 다음을 참조하십시오. [이 섹션](../building-journeys/testing-the-journey.md).

Adobe Experience Platform에서 테스트 프로필을 만드는 방법에는 여러 가지가 있습니다. 이 설명서에서는 두 가지 방법에 중점을 둡니다. [csv 파일](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) 및 사용 [API 호출](../building-journeys/creating-test-profiles.md#create-test-profiles-api). 데이터 세트에 json 파일을 업로드할 수도 있습니다. 다음을 참조하십시오. [데이터 수집 설명서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

이러한 가져오기 메서드를 사용하면 프로필 속성을 업데이트할 수도 있습니다. 이렇게 하면 기존 프로필을 테스트 프로필로 만들 수 있습니다. 단순히 유사한 파일 또는 API 호출을 사용하고 값이 &quot;true&quot;인 &quot;testProfile&quot; 필드만 포함하면 됩니다.

테스트 프로필을 만드는 것은 Adobe Experience Platform에서 일반 프로필을 만드는 것과 비슷합니다. 자세한 내용은 [실시간 고객 프로필 설명서](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko).

## 전제 조건{#test-profile-prerequisites}

프로필을 만들 수 있으려면 먼저 Adobe Experience Platform에서 스키마와 데이터 세트를 만들어야 합니다.

먼저 다음을 수행해야 합니다. **스키마 만들기**. 다음 단계를 수행하십시오.

1. Adobe Experience Platform에서 **[!UICONTROL Schemas]**왼쪽 메뉴에서 을 클릭합니다.
   ![](../assets/test-profiles-0.png)
1. 클릭 **[!UICONTROL Create schema]**&#x200B;오른쪽 상단에서 스키마 유형(예: )을 선택합니다 **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. 스키마 이름을 선택합니다.
1. **[!UICONTROL Mixins]** 섹션에서 **[!UICONTROL Add]**을(를) 클릭합니다.
   ![](../assets/test-profiles-1-bis.png)
1. 적절한 mixin을 선택합니다. 다음을 추가해야 합니다. **[!UICONTROL Profile test details]** mixin. **[!UICONTROL Add mixin]**을(를) 클릭합니다.
   ![](../assets/test-profiles-1-ter.png)
mixin 목록이 스키마 개요 화면에 표시됩니다.
   ![](../assets/test-profiles-2.png)
1. 필드 목록에서 기본 ID로 정의할 필드를 클릭합니다.
   ![](../assets/test-profiles-3.png)
1. 다음에서 **[!UICONTROL Field properties]** 오른쪽 패널에서 **[!UICONTROL Identity]** 및 **[!UICONTROL Primary Identity]** 옵션을 선택하고 네임스페이스를 선택합니다. 기본 ID를 이메일 주소로 설정하려면 **[!UICONTROL Email]** 네임스페이스입니다. **[!UICONTROL Apply]**을(를) 클릭합니다.
   ![](../assets/test-profiles-4.png)
1. 스키마를 선택하고 **[!UICONTROL Profile]** 의 옵션 **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

>[!NOTE]
>
>스키마 만들기에 대한 자세한 내용은 [XDM 설명서](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

그러면 다음을 수행해야 합니다. **데이터 세트 만들기** 프로필을 가져올 위치입니다. 다음 단계를 수행하십시오.

1. Adobe Experience Platform에서 **[!UICONTROL Datasets]**&#x200B;왼쪽 메뉴에서 을(를) 클릭한 다음 을(를) 클릭합니다 **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. 선택 **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. 이전에 만든 스키마를 선택하고 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. 이름을 선택한 다음 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. 활성화 **[!UICONTROL Profile]** 옵션을 선택합니다.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 데이터 세트 만들기에 대한 자세한 내용은 [카탈로그 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## csv 파일을 사용하여 테스트 프로필 만들기{#create-test-profiles-csv}

Adobe Experience Platform에서는 다른 프로필 필드가 포함된 csv 파일을 데이터 세트에 업로드하여 프로필을 만들 수 있습니다. 이것이 가장 쉬운 방법입니다.

1. 스프레드시트 소프트웨어를 사용하여 간단한 csv 파일을 만듭니다.
1. 필요한 각 필드에 하나의 열을 추가합니다. 기본 ID 필드(&quot;위의 예에서 &quot;personID&quot;)와 &quot;testProfile&quot; 필드를 &quot;true&quot;로 설정해야 합니다.
   ![](../assets/test-profiles-11.png)
1. 프로필당 한 줄을 추가하고 각 필드의 값을 입력합니다.
   ![](../assets/test-profiles-12.png)
1. 스프레드시트를 csv 파일로 저장합니다. 쉼표를 구분 기호로 사용해야 합니다.
1. Adobe Experience Platform에서 **[!UICONTROL Workflows]**왼쪽 메뉴에서 을 클릭합니다.
   ![](../assets/test-profiles-14.png)
1. 선택 **[!UICONTROL Map CSV to XDM schema]**&#x200B;을 클릭한 다음 을 클릭합니다 **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. 프로필을 가져올 데이터 세트를 선택합니다. **[!UICONTROL Next]**을(를) 클릭합니다.
   ![](../assets/test-profiles-17.png)
1. 클릭 **[!UICONTROL Choose files]** csv 파일을 선택합니다. 파일이 업로드되면 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. 소스 csv 필드를 스키마 필드에 매핑한 다음 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. 데이터 가져오기가 시작됩니다. 다음에서 상태가 이동합니다. **[!UICONTROL Processing]** 끝 **[!UICONTROL Success]**. 클릭 **[!UICONTROL Preview data set]**을 클릭합니다.
   ![](../assets/test-profiles-20.png)
1. 테스트 프로필이 올바르게 추가되었는지 확인합니다.
   ![](../assets/test-profiles-21.png)

테스트 프로필이 추가되었으며 이제 여정 테스트 시 사용할 수 있습니다. [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.
>[!NOTE]
>
> csv 가져오기에 대한 자세한 내용은 [데이터 수집 설명서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

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
