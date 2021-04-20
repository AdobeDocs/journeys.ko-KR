---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration으로 이벤트를 전송하는 추가 단계
description: Journey Orchestration으로 이벤트를 전송하는 추가 단계에 대해 알아봅니다.
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 7%

---



# 이벤트를 [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}에 전송하는 추가 단계

>[!NOTE]
>
>이벤트를 만들 때 [!DNL Journey Orchestration]은(는) 이 이벤트의 ID를 자동으로 생성합니다. 이벤트를 실행하는 시스템은 ID를 생성하지 않아야 합니다. 페이로드 미리 보기에서 사용할 수 있는 ID를 사용해야 합니다. [이 페이지](../event/previewing-the-payload.md)를 참조하십시오.

**[!UICONTROL Streaming Ingestion APIs]**&#x200B;에 전송되고 [!DNL Journey Orchestration]에 사용할 이벤트를 구성하려면 다음 단계를 따라야 합니다.

1. Adobe Experience Platform API에서 입력 URL을 가져옵니다([스트리밍 통합 API](https://docs.adobe.com/content/help/ko-KR/experience-platform/ingestion/streaming/overview.html) 참조).
1. **[!UICONTROL Event]** 메뉴의 페이로드 미리 보기에서 페이로드를 복사합니다. [이 페이지](../event/defining-the-payload-fields.md)를 참조하십시오.

그런 다음 복사한 페이로드를 사용하여 이벤트를 스트리밍 통합 API로 푸시하는 데이터 시스템을 구성해야 합니다.

1. 스트리밍 통합 API URL(입구라고 함)에 대한 POST API 호출을 설정합니다.
1. 스트리밍 통합 API에 대한 API 호출의 본문(&quot;데이터 섹션&quot;)에 [!DNL Journey Orchestration]에서 복사한 페이로드를 사용합니다. 예를 보려면 아래를 참조하십시오.
1. 페이로드에 있는 모든 변수를 가져올 위치를 결정합니다. 예:이벤트가 주소를 전달해야 하는 경우 붙여넣은 페이로드에는 &quot;주소&quot;가 표시됩니다.&quot;string&quot;을 참조하십시오. &quot;string&quot;은 메시지를 보낼 사람의 이메일인 올바른 값을 자동으로 채우는 변수로 대체되어야 합니다. 페이로드 미리 보기의 **[!UICONTROL Header]** 섹션에서 작업을 용이하게 하는 데 필요한 많은 값을 자동으로 채웁니다.
1. 본문 유형으로 &quot;application/json&quot;을 선택합니다.
1. 키 &quot;x-gw-ims-org-id&quot;를 사용하여 헤더에 IMS 조직 ID를 전달합니다. 이 값에 대해 IMS 조직 ID(&quot;XXX@AdobeOrg&quot;)를 사용하십시오.

다음은 스트리밍 통합 API 이벤트의 예입니다.

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

&quot;데이터&quot; 부분을 붙여넣을 위치를 쉽게 식별하기 위해 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)과 같은 JSON 시각화 도구를 사용할 수 있습니다.

스트리밍 통합 API 문제를 해결하려면 이 [페이지](https://docs.adobe.com/content/help/ko-KR/experience-platform/ingestion/streaming/troubleshooting.html)를 참조하십시오.
