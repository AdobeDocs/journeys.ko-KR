---
product: adobe campaign
solution: Journey Orchestration
title: 테스트 프로필 만들기
description: '테스트 프로필 생성에 대한 자세한 내용 '
translation-type: tm+mt
source-git-commit: 8c7c7d85d4e7835721b70faa7b3b6166796e79c4
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 2%

---


# 테스트 프로필 {#create-test-profiles} 만들기

![](../assets/do-not-localize/badge.png)

여정에서 테스트 모드를 사용할 때는 테스트 프로필이 필요합니다. [기존 프로필](../building-journeys/creating-test-profiles.md#turning-profile-into-test)을 테스트 프로필로 변환하거나 [테스트 프로필](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)을 만들 수 있습니다. 테스트 모드 사용 방법에 대해 알아보려면 [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.

Adobe Experience Platform에서 테스트 프로필을 만드는 방법은 다양합니다. 이 문서에서는 다음 두 가지 방법에 중점을 둡니다.[csv 파일](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)을 업로드하고 [API 호출](../building-journeys/creating-test-profiles.md#create-test-profiles-api)을 사용합니다. 데이터 세트에 json 파일을 업로드할 수도 있습니다. [데이터 통합 문서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)

테스트 프로필을 만드는 것은 Adobe Experience Platform에서 일반 프로필을 만드는 것과 비슷합니다. 자세한 내용은 [실시간 고객 프로필 설명서](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)를 참조하십시오.

## 사전 요구 사항{#test-profile-prerequisites}

프로파일을 만들려면 먼저 Adobe Experience Platform에서 스키마와 데이터 세트를 만들어야 합니다.

먼저 **스키마**&#x200B;를 만들어야 합니다. 다음 단계를 수행합니다.

1. Adobe Experience Platform의 왼쪽 메뉴에서 **스키마**를 클릭합니다.
   ![](../assets/test-profiles-0.png)
1. 오른쪽 상단에서 **스키마 만들기**&#x200B;를 클릭한 다음 스키마 유형을 선택합니다(예: **XDM 개별 프로필**).
   ![](../assets/test-profiles-1.png)
1. 스키마 이름을 선택합니다.
1. **혼합** 섹션에서 **추가**를 클릭합니다.
   ![](../assets/test-profiles-1-bis.png)
1. 적절한 믹스를 선택합니다. **프로필 테스트 세부 사항** 혼합을 추가해야 합니다. **혼합 추가**를 클릭합니다.
   ![](../assets/test-profiles-1-ter.png)
혼합 목록은 스키마 개요 화면에 표시됩니다.

   ![](../assets/test-profiles-2.png)
1. 필드 목록에서 기본 ID로 정의할 필드를 클릭합니다.
   ![](../assets/test-profiles-3.png)
1. **필드 속성** 오른쪽 패널에서 **ID** 및 **기본 ID** 옵션을 선택하고 네임스페이스를 선택합니다. 기본 ID를 이메일 주소로 지정하려면 **이메일** 네임스페이스를 선택합니다. **적용**을 클릭합니다.
   ![](../assets/test-profiles-4.png)
1. 스키마를 선택하고 **스키마 속성**&#x200B;에서 **프로필** 옵션을 활성화합니다.
   ![](../assets/test-profiles-5.png)
1. **저장**&#x200B;을 클릭합니다.

>[!NOTE]
>
>스키마 만들기에 대한 자세한 내용은 [XDM 설명서](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)를 참조하십시오.

그런 다음 프로파일을 가져올 데이터 세트&#x200B;**를 만들어야 합니다.** 다음 단계를 수행합니다.

1. Adobe Experience Platform에서 왼쪽 메뉴에서 **데이터 집합**&#x200B;을 클릭한 다음 **데이터 집합 만들기**를 클릭합니다.
   ![](../assets/test-profiles-6.png)
1. **스키마**에서 데이터 집합 만들기를 선택합니다.
   ![](../assets/test-profiles-7.png)
1. 이전에 만든 스키마를 선택한 다음 **다음**을 클릭합니다.
   ![](../assets/test-profiles-8.png)
1. 이름을 선택한 다음 **마침**을 클릭합니다.
   ![](../assets/test-profiles-9.png)
1. **프로필** 옵션을 활성화합니다.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 데이터 세트 생성에 대한 자세한 내용은 [카탈로그 서비스 설명서](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)를 참조하십시오.

## 프로필을 테스트 프로필로 변환{#turning-profile-into-test}

기존 프로필을 테스트 프로필로 변환할 수 있습니다. Adobe Experience Platform에서는 프로파일을 만들 때와 같은 방법으로 프로파일 속성을 업데이트할 수 있습니다.

보다 간단한 방법은 여정에서 **프로필** 작업 활동을 업데이트하고 testProfile 부울 필드를 false에서 true로 변경하는 것입니다.

여정은 **세그먼트 읽기** 및 **프로필 업데이트** 활동으로 구성됩니다. 먼저 테스트 프로필로 전환할 프로필을 대상으로 하는 세그먼트를 만들어야 합니다.

>[!NOTE]
>
> **testProfile** 필드를 업데이트하므로 선택한 프로필에 이 필드가 포함되어야 합니다. 관련 스키마에는 **프로필 테스트 세부 사항** 믹신이 있어야 합니다. [이 섹션](../building-journeys/creating-test-profiles.md#test-profiles-prerequisites)을 참조하십시오.

1. 고객 여정 관리의 왼쪽 메뉴에서 **세그먼트**&#x200B;를 클릭한 다음 오른쪽 상단에서 **세그먼트 만들기**를 클릭합니다.
   ![](../assets/test-profiles-22.png)
1. 세그먼트의 이름을 정의하고 세그먼트를 만듭니다.원하는 프로파일을 대상으로 할 필드와 값을 선택합니다.
   ![](../assets/test-profiles-23.png)
1. **저장**을 클릭하고 프로파일이 세그먼트에서 올바르게 타깃팅되었는지 확인합니다.
   ![](../assets/test-profiles-24.png)

   >[!NOTE]
   >
   > 세그먼트 계산에 시간이 걸릴 수 있습니다. [이 섹션](../segment/about-segments.md)의 세그먼트에 대해 자세히 알아보십시오.

1. 이제 새 여정을 만들고 **세그먼트 읽기** 오케스트레이션 활동으로 시작합니다.
1. 이전에 만든 세그먼트와 프로필에서 사용하는 네임스페이스를 선택합니다.
   ![](../assets/test-profiles-25.png)
1. **프로필** 작업 활동을 업데이트합니다.
1. 스키마, **testProfiles** 필드, 데이터 집합을 선택하고 값을 &quot;true&quot;로 설정합니다.
   ![](../assets/test-profiles-26.png)
1. **종료** 활동을 추가하고 **게시**를 클릭합니다.
   ![](../assets/test-profiles-27.png)
1. Adobe Experience Platform에서 프로필이 올바르게 업데이트되었는지 확인합니다.
   ![](../assets/test-profiles-28.png)

   >[!NOTE]
   >
   > **프로필** 활동에 대한 자세한 내용은 [이 섹션](../building-journeys/update-profiles.md)을 참조하십시오.

## csv 파일{#create-test-profiles-csv}을(를) 사용하여 테스트 프로필 만들기

Adobe Experience Platform에서는 서로 다른 프로필 필드를 포함하는 csv 파일을 데이터 세트에 업로드하여 프로필을 만들 수 있습니다. 이것이 가장 쉬운 방법입니다.

1. 스프레드시트 소프트웨어를 사용하여 간단한 csv 파일을 만듭니다.
1. 필요한 각 필드에 하나의 열을 추가합니다. 기본 ID 필드(위의 예에서 &quot;personID&quot;)와 &quot;testProfile&quot; 필드를 &quot;true&quot;로 설정해야 합니다.
   ![](../assets/test-profiles-11.png)
1. 프로필당 한 줄을 추가하고 각 필드의 값을 채웁니다.
   ![](../assets/test-profiles-12.png)
1. 스프레드시트를 csv 파일로 저장합니다. 쉼표를 구분 기호로 사용해야 합니다.
1. Adobe Experience Platform의 왼쪽 메뉴에서 **워크플로**를 클릭합니다.
   ![](../assets/test-profiles-14.png)
1. **CSV를 XDM 스키마**&#x200B;에 매핑한 다음 **실행**을 클릭합니다.
   ![](../assets/test-profiles-16.png)
1. 프로필을 가져올 데이터 세트를 선택합니다. **다음**을 클릭합니다.
   ![](../assets/test-profiles-17.png)
1. **파일 선택**&#x200B;을 클릭하고 csv 파일을 선택합니다. 파일이 업로드되면 **다음**을 클릭합니다.
   ![](../assets/test-profiles-18.png)
1. 소스 csv 필드를 스키마 필드에 매핑한 다음 **완료**를 클릭합니다.
   ![](../assets/test-profiles-19.png)
1. 데이터 가져오기가 시작됩니다. 상태는 **처리**&#x200B;에서 **성공**&#x200B;으로 이동합니다. 오른쪽 상단에서 **데이터 세트 미리 보기**를 클릭합니다.
   ![](../assets/test-profiles-20.png)
1. 테스트 프로필이 올바르게 추가되었는지 확인합니다.
   ![](../assets/test-profiles-21.png)

테스트 프로필이 추가되고 이제 여정을 테스트할 때 사용할 수 있습니다. [이 섹션](../building-journeys/testing-the-journey.md)을 참조하십시오.
>[!NOTE]
>
> csv 가져오기에 대한 자세한 내용은 [데이터 통합 문서](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)를 참조하십시오.

## API 호출을 사용하여 테스트 프로필 만들기{#create-test-profiles-api}

API 호출을 통해 테스트 프로필을 만들 수도 있습니다. 이 [페이지](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html)를 참조하십시오.

&quot;프로필 테스트 세부 사항&quot; 혼합을 포함하는 프로필 스키마를 사용해야 합니다. testProfile 플래그는 이 믹싱의 일부입니다.

프로파일을 만들 때 값을 전달해야 합니다.testProfile = true.

기존 프로파일을 업데이트하여 testProfile 플래그를 &quot;true&quot;로 변경할 수도 있습니다.

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

