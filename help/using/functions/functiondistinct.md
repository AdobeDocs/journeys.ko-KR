---
product: adobe campaign
title: distinct
description: 기능 고유 사항에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 6%

---

# distinct {#distinct}

주어진 목록의 고유 값 또는 개체를 반환합니다. Null 항목은 무시됩니다.

## 카테고리

목록

## 함수 구문

`distinct(<parameters>)`

## 매개 변수

| 매개변수 | 유형 | 설명 |
|-----------|------------------|------------------|
| listToprocess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly 또는 listObject | 처리할 목록. listObject의 경우 필드 참조여야 합니다. |
| keyAttributeName | 문자열 | 이 매개 변수는 선택 사항이며 listObject에만 사용됩니다. 매개변수를 제공하지 않으면 모든 속성의 값이 동일한 경우 객체가 복제된 것으로 간주됩니다. 그렇지 않으면, 지정된 속성에 동일한 값이 있으면 객체가 복제된 것으로 간주됩니다. |

## 서명 및 반환된 유형

`distinct(<listInteger>)`

정수 목록을 반환합니다.

`distinct(<listDecimal>)`

소수점 목록을 반환합니다.

`distinct(<listString>)`

문자열 목록을 반환합니다.

`distinct(<listDateTimeOnly>)`

시간대를 고려하지 않고 날짜/시간 목록을 반환합니다.

`distinct(<listDateTime>)`

날짜/시간 목록을 반환합니다.

`distinct(<listDateOnly>)`

날짜 목록을 반환합니다.

`distinct(<listBoolean>)`

부울 목록을 반환합니다.

`distinct(<listDuration>)`

기간 목록을 반환합니다.

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

개체 목록을 반환합니다.


## 예시

`distinct([10,2,10,null])`

`[10, 2]`을(를) 반환합니다
