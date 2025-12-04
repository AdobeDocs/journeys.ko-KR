---
product: adobe campaign
title: limit
description: 기능 제한에 대해 알아보기
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 8%

---

# limit {#limit}

목록의 첫 번째 또는 마지막 N 요소를 반환합니다.

## 카테고리

목록

## 함수 구문

`limit(<parameters>)`

## 매개변수

| 매개변수 | 유형 | 설명 |
|-----------|------------------|------------------|
| listToprocess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly 또는 listObject | 정렬할 목록입니다. listObject의 경우 필드 참조여야 합니다. |
| numberOfItems | 정수 | 해당 목록에서 반환할 항목 수. |
| 첫 번째 또는 마지막 항목 | 부울 | 이 매개 변수는 선택 사항입니다(기본값: true). true는 첫 번째 항목을 반환합니다. false는 마지막 항목을 반환합니다. |

## 서명 및 반환된 유형

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

문자열 목록을 반환합니다.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

정수 목록을 반환합니다.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

소수점 목록을 반환합니다.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

부울 목록을 반환합니다.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

날짜 목록을 반환합니다.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

시간대를 고려하지 않고 날짜/시간 목록을 반환합니다.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

날짜/시간 목록을 반환합니다.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

기간 목록을 반환합니다.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

개체 목록을 반환합니다.

## 예

`limit(["A", "B", "C", "D", "E"], 3)`

`["A","B","C"]`을(를) 반환합니다

`limit(["A", "B", "C", "D", "E"], 3, false)`

`["C","D","E"]`을(를) 반환합니다
