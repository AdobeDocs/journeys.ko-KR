---
product: adobe campaign
solution: Journey Orchestration
title: 여정 테스트
description: '여정 테스트에 대한 자세한 내용 '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 8c7c7d85d4e7835721b70faa7b3b6166796e79c4
workflow-type: tm+mt
source-wordcount: '1624'
ht-degree: 3%

---


# 여정 테스트{#testing_the_journey}

여정을 테스트하려면 먼저 모든 오류를 해결해야 합니다. [이 섹션](../about/troubleshooting.md#section_h3q_kqk_fhb)을 참조하십시오.

테스트 프로필을 사용하여 여정을 게시하기 전에 테스트할 수 있습니다. 이를 통해 개별 여정의 흐름을 분석하고 게시 전에 문제를 해결할 수 있습니다.

테스트 프로필만 테스트 모드에서 여정에 입력할 수 있습니다. 새 테스트 프로필을 만들거나 기존 프로필을 테스트 프로필로 변환할 수 있습니다. 이 [섹션](../building-journeys/creating-test-profiles.md)을 참조하십시오.

테스트 모드를 사용하려면 다음 단계를 수행합니다.

1. 여정을 테스트하기 전에이 유효한지 그리고 오류가 없는지 확인하십시오. 오류가 있는 여정 테스트를 시작할 수 없습니다. [이 섹션](../about/troubleshooting.md#section_h3q_kqk_fhb)을 참조하십시오. 오류가 있으면 경고 기호가 표시됩니다.

1. 테스트 모드를 활성화하려면 오른쪽 위 모서리에 있는 **[!UICONTROL Test]** 토글을 클릭합니다.

   ![](../assets/journeytest1.png)

1. 왼쪽 아래 모서리의 **[!UICONTROL Wait time]** 매개 변수를 사용하여 각 대기 활동 및 이벤트 시간 초과가 테스트 모드에서 지속될 시간을 정의합니다. 기본 시간은 대기 시간 및 이벤트 시간 초과에 대한 10초입니다. 그러면 테스트 결과가 빠르게 나올 수 있습니다. 이 매개 변수는 여정에서 하나 이상의 대기 활동을 삭제한 경우에만 나타납니다.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >여정에서 반응 이벤트를 사용하면 대기 시간 기본값과 최소값은 40초입니다. [이 섹션](../building-journeys/reaction-events.md)을 참조하십시오.

1. 이벤트를 구성하고 여정으로 보내려면 **[!UICONTROL Trigger an event]**&#x200B;을 클릭합니다.

   ![](../assets/journeyuctest1.png)

1. 필요한 다른 필드를 구성합니다. **프로필 식별자** 필드에 테스트 프로필을 식별하는 데 사용되는 필드의 값을 입력합니다. 예를 들어 이메일 주소일 수 있습니다. 테스트 프로필과 관련된 이벤트를 전송해야 합니다. [이벤트 시작](#firing_events)을 참조하십시오.

   ![](../assets/journeyuctest1-bis.png)

1. 이벤트가 수신되면 **[!UICONTROL Show log]** 단추를 클릭하여 테스트 결과를 보고 확인합니다. [로그 보기](#viewing_logs)를 참조하십시오.

   ![](../assets/journeyuctest2.png)

1. 오류가 있는 경우 테스트 모드를 비활성화하고 여정를 수정한 후 다시 테스트하십시오. 테스트가 완료되면 여정을 게시할 수 있습니다. [이 페이지](../building-journeys/publishing-the-journey.md)를 참조하십시오.

## 중요 정보 {#important_notes}

* 테스트를 거친 여정에 이벤트를 실행하는 인터페이스가 제공되지만 Postman과 같은 제3자 시스템으로도 이벤트를 전송할 수 있습니다.
* 실시간 고객 프로파일 서비스에서 &quot;테스트 프로파일&quot;로 플래그가 지정된 개인만 테스트된 여정에 입력할 수 있습니다. 이 [섹션](../building-journeys/creating-test-profiles.md)을 참조하십시오.
* 테스트 모드는 네임스페이스를 사용하는 초안 여정에서만 사용할 수 있습니다. 테스트 모드는 여정에 입장하는 사람이 테스트 프로필인지 여부를 확인해야 하므로 Adobe Experience Platform에 도달할 수 있어야 합니다.
* 테스트 세션 동안 여정에 입력할 수 있는 최대 테스트 프로필 수는 100개입니다.
* 테스트 모드를 비활성화하면 이전에 테스트 모드를 입력한 사람 또는 현재 테스트 상태에 있는 사람의 여정이 모두 비어 있게 됩니다. 또한 보고서를 지웁니다.
* 필요에 따라 테스트 모드를 활성화/비활성화할 수 있습니다.
* 테스트 모드가 활성화되면 여정을 수정할 수 없습니다. 테스트 모드에서는 여정을 직접 게시할 수 있으며, 이전에 테스트 모드를 비활성화할 필요가 없습니다.

## 프로필을 테스트 프로필로 변환{#turning-profile-into-test}

기존 프로필을 테스트 프로필로 변환할 수 있습니다. Adobe Experience Platform에서는 API 호출을 통해 프로필 속성을 업데이트할 수 있지만 인터페이스를 통해 수행할 수 없습니다.

이렇게 하는 가장 쉬운 방법은 **프로필** 작업 활동을 업데이트하고 테스트 프로필 부울 필드를 false에서 true로 변경하는 것입니다. [이 섹션](../building-journeys/update-profiles.md#using-the-test-mode)을 참조하십시오.

## 테스트 프로필 만들기{#create-test-profile}

새 테스트 프로필을 만들려면 이 절차는 Adobe Experience Platform에서 프로필을 만들 때와 동일합니다. API 호출을 통해 수행됩니다. 이 [페이지](https://docs.adobe.com/content/help/ko-KR/experience-platform/profile/home.html)를 참조하십시오

&quot;프로필 테스트 세부 사항&quot; 믹싱을 포함하는 프로필 스키마를 사용해야 합니다. testProfile 플래그는 이 믹싱의 일부입니다.

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

## 이벤트 {#firing_events} 실행

**[!UICONTROL Trigger an event]** 단추를 사용하면 여정에 입장하도록 하는 이벤트를 구성할 수 있습니다.

>[!NOTE]
>
>테스트 모드에서 이벤트를 트리거하면 실제 이벤트가 생성되며, 이것은 이 이벤트를 수신하는 다른 여정에도 영향을 줍니다.

사전 요구 사항으로, Adobe Experience Platform에서 테스트 프로필로 플래그가 지정된 프로파일을 알고 있어야 합니다. 실제로 테스트 모드에서는 여정에 이러한 프로파일만 사용할 수 있으며 이벤트에는 ID가 포함되어야 합니다. 예상 ID는 이벤트 구성에 따라 다릅니다. 예를 들어 ECID 또는 이메일 주소를 사용할 수 있습니다. 이 키의 값을 **프로필 식별자** 필드에 추가해야 합니다.

여정에 여러 개의 이벤트가 있는 경우 드롭다운 목록을 사용하여 이벤트를 선택합니다. 그런 다음 각 이벤트에 대해 전달된 필드와 이벤트 전송 실행을 구성합니다. 이 인터페이스는 이벤트 페이로드에서 올바른 정보를 전달하고 정보 유형이 올바른지 확인하는 데 도움이 됩니다. 테스트 모드는 나중에 사용하기 위해 테스트 세션에서 사용한 마지막 매개 변수를 저장합니다.

![](../assets/journeytest4.png)

이 인터페이스를 사용하면 간단한 이벤트 매개 변수를 전달할 수 있습니다. 이벤트에서 컬렉션이나 다른 고급 개체를 전달하려면 **[!UICONTROL Code View]**&#x200B;을 클릭하여 페이로드의 전체 코드를 보고 수정할 수 있습니다. 예를 들어 기술 사용자가 준비한 이벤트 정보를 복사하여 붙여넣을 수 있습니다.

![](../assets/journeytest5.png)

또한 기술 사용자는 이 인터페이스를 사용하여 타사 도구를 사용하지 않고도 이벤트 페이로드를 구성하고 이벤트를 트리거할 수 있습니다.

**[!UICONTROL Send]** 단추를 클릭하면 테스트가 시작됩니다. 여정에서 개인의 진행 상태는 시각적 흐름으로 표시됩니다. 여정을 따라 이동하는 트랙은 점점 녹색으로 변합니다. 오류가 발생하면 해당 단계에 경고 기호가 표시됩니다. 커서를 여기에 놓으면 오류에 대한 자세한 정보를 표시하고 전체 세부 사항(사용 가능한 경우)에 액세스할 수 있습니다.

![](../assets/journeytest6.png)

이벤트 구성 화면에서 다른 테스트 프로필을 선택하고 테스트를 다시 실행하면 시각적 흐름이 지워지고 새 개인의 경로가 표시됩니다.

테스트에서 여정을 열 때 표시되는 경로는 마지막으로 실행된 테스트에 해당합니다.

시각적 흐름은 인터페이스를 통해 이벤트가 트리거되는지 외부적으로 트리거되는지(예: Postman 사용) 여부를 확인합니다.

## 규칙 기반 여정 {#test-rule-based} 테스트 모드

규칙 기반 이벤트를 사용하는 여정에서도 테스트 모드를 사용할 수 있습니다. 규칙 기반 이벤트에 대한 자세한 내용은 [이 페이지](../event/about-events.md)를 참조하십시오.

이벤트를 트리거할 때 **이벤트 구성** 화면에서는 테스트에 전달할 이벤트 매개 변수를 정의할 수 있습니다. 오른쪽 상단 모서리의 도구 설명 아이콘을 클릭하여 이벤트 ID 조건을 볼 수 있습니다. 규칙 평가의 일부인 각 필드 옆에 툴팁도 사용할 수 있습니다.

![](../assets/alpha-event8.png)

테스트 모드 사용 방법에 대한 자세한 내용은 [이 페이지](../building-journeys/testing-the-journey.md)를 참조하십시오.

## 로그 {#viewing_logs} 보기

**[!UICONTROL Show log]** 단추를 사용하여 테스트 결과를 볼 수 있습니다. 이 페이지에는 여정의 현재 정보가 JSON 형식으로 표시됩니다. 버튼을 사용하면 전체 노드를 복사할 수 있습니다. 여정의 테스트 결과를 업데이트하려면 페이지를 수동으로 새로 고쳐야 합니다.

![](../assets/journeytest3.png)

>[!NOTE]
>
>테스트 로그에서 제3자 시스템(데이터 소스 또는 작업)을 호출할 때 오류가 발생하는 경우 오류 코드와 오류 응답이 표시됩니다.

현재 여정 내에 있는 개인 수(기술적으로 인스턴스라고 함)가 표시됩니다. 다음은 각 개인에 대해 표시되는 유용한 정보입니다.

* _ID_:여정의 개인 내부 ID. 디버깅용으로 사용할 수 있습니다.
* _currentstep_:개인이 여정에 있는 단계. 보다 쉽게 식별할 수 있도록 활동에 레이블을 추가하는 것이 좋습니다.
* _currentstep_ > 단계:개인 여정 상태(실행 중, 완료, 오류 또는 시간 초과)입니다. 자세한 내용은 아래를 참조하십시오.
* _currentstep_ >  _extraInfo_:오류 및 기타 컨텍스트 정보에 대한 설명입니다.
* _currentstep_ >  _fetchErrors_:이 단계에서 발생한 데이터 가져오기 오류에 대한 정보입니다.
* _externalKeys_:이벤트에 정의된 키 공식에 대한 값입니다.
* _풍부해진 데이터_:여정에서 데이터 소스를 사용하는 경우 여정에서 검색한 데이터입니다.
* _transitionHistory_:개인이 수행한 단계 목록. 이벤트의 경우 페이로드가 표시됩니다.
* _actionExecutionErrors_ :발생한 오류에 대한 정보입니다.

개인 여정의 다른 상태는 다음과 같습니다.

* _실행_:개인이 현재 여정에 있습니다.
* _완료_:개인은 여정 끝에 있다.
* _오류_:오류가 발생하여 개인이 여정에서 정지됩니다.
* _시간 초과_:그 사람은 너무 많은 시간이 걸린 단계 때문에 여정에서 정지된다.

테스트 모드를 사용하여 이벤트가 트리거되면 소스 이름으로 데이터 세트가 자동으로 생성됩니다.

테스트 모드를 사용하여 이벤트가 트리거되면 소스 이름으로 데이터 세트가 자동으로 생성됩니다.

테스트 모드는 자동으로 경험 이벤트를 만들어 Adobe Experience Platform으로 전송합니다. 이 경험 이벤트에 대한 소스의 이름은 &quot;Journey Orchestration 테스트 이벤트&quot;입니다.

여러 여정에서 트리거된 여러 이벤트의 경우

서로 다른 스키마를 갖는 여러 여정에서 전송된 여러 이벤트가 있는 경우 시나리오가 있습니다. 스키마는 1개의 데이터 세트에 매핑할 수 있습니까? 그렇지 않으면 데이터 세트가 여러 개 필요합니다.

대상 데이터 세트가 경험 이벤트에 포함되지 않은 경우 이러한 데이터 세트를 자동으로 만들고 이름을 지정합니다. 그래서 우리는 오늘날 &quot;보이저용 데이터 세트 자동 생성&quot;을 보게 된다.

소스 이름을 지정하면 자동으로 생성됩니다. 여러 이벤트가 있는 경우 &quot;Journey Orchestration 테스트 이벤트 - 스키마 이름&quot;을 연결하여 사용해야 합니다. 이렇게 하면 &quot;Journey Orchestration 테스트 이벤트에 대해 자동으로 생성된 데이터 세트 - 스키마 이름&quot;이 자동으로 생성됩니다.

