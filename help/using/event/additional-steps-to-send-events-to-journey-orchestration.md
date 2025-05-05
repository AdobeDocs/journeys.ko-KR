---
product: adobe campaign
title: Journey Orchestration에 이벤트를 보내는 추가 단계
description: Journey Orchestration에 이벤트를 전송하는 추가 단계에 대해 알아보기
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# [!DNL Journey Orchestration]에 이벤트를 보내는 추가 단계 {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Adobe Journey Optimizer을 찾고 계십니까**? Journey Optimizer 설명서를 보려면 [여기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/ajo-home){target="_blank"}를 클릭하십시오.
>
>
>_이 설명서는 Journey Optimizer으로 대체된 기존 Journey Orchestration 자료를 참조합니다. Journey Orchestration 또는 Journey Optimizer 액세스에 대한 질문이 있는 경우 계정 팀에 문의하십시오._


>[!NOTE]
>
>이벤트를 만들 때 [!DNL Journey Orchestration]에서 이 이벤트에 대한 ID를 자동으로 생성합니다. 이벤트를 푸시하는 시스템은 ID를 생성하지 않아야 하며 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

**[!UICONTROL Streaming Ingestion APIs]**&#x200B;에 보내고 [!DNL Journey Orchestration]에서 사용할 이벤트를 구성하려면 다음 단계를 수행해야 합니다.

1. Adobe Experience Platform API에서 인렛 URL을 가져옵니다([수집 API 스트리밍](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ko) 참조).
1. **[!UICONTROL Event]** 메뉴의 페이로드 미리 보기에서 페이로드를 복사합니다. [이 페이지](../event/defining-the-payload-fields.md)를 참조하십시오.

그런 다음 복사한 페이로드를 사용하여 이벤트를 스트리밍 수집 API로 푸시하는 데이터 시스템을 구성해야 합니다.

1. 스트리밍 수집 API URL(인렛이라고 함)에 대한 POST API 호출을 설정합니다.
1. 스트리밍 수집 API에 대한 API 호출의 본문(&quot;데이터 섹션&quot;)에 있는 [!DNL Journey Orchestration]에서 복사한 페이로드를 사용합니다. 예제는 아래를 참조하십시오
1. 페이로드에 있는 모든 변수를 가져올 위치를 결정합니다. 예: 이벤트가 주소를 전달해야 하는 경우 붙여넣은 페이로드에 &quot;address&quot;: &quot;string&quot;이 표시됩니다. &quot;string&quot;은 올바른 값(메시지를 보낼 사람의 이메일)을 자동으로 채우는 변수로 대체해야 합니다. 페이로드 미리 보기의 **[!UICONTROL Header]** 섹션에서 작업을 용이하게 하기 위해 필요한 많은 값을 자동으로 채웁니다.
1. 본문 유형으로 &quot;application/json&quot;을 선택합니다.
1. &quot;x-gw-ims-org-id&quot; 키를 사용하여 IMS 조직 ID를 헤더에 전달합니다. 값은 IMS 조직 ID(&quot;XXX@AdobeOrg&quot;)를 사용하십시오.

다음은 스트리밍 수집 API 이벤트의 예입니다.

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

&quot;데이터&quot; 부분을 붙여넣을 위치를 쉽게 확인하려면 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)과(와) 같은 JSON 시각화 도구를 사용할 수 있습니다.

스트리밍 수집 API의 문제를 해결하려면 이 [페이지](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=ko)를 참조하세요.
