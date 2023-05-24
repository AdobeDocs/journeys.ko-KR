---
product: adobe campaign
title: filter
description: 함수 필터에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

지정된 키 값 중 하나와 일치하는 키 특성을 가진 개체와 함께 listObject를 반환합니다.

## 카테고리

목록

## 함수 구문

`filter(<parameters>)`

## 매개 변수

| 매개변수 | 유형 | 설명 |
|-----------|------------------|------------------|
| listTofilter | listObject | 필터링할 객체 목록입니다. 필드 참조여야 합니다. |
| keyAttributeName | 문자열 | 해당 목록의 개체에서 필터링용 키로 사용되는 속성 이름 |
| 키 값 목록 | list | 필터링에 사용할 키 값 배열 |

## 서명 및 반환된 유형

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

listObject를 반환합니다.

## 예시

다음은 수신 이벤트 &quot;myevent&quot;에서 전달된 페이로드의 예입니다.

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

다음 표현식을 사용할 수 있습니다.

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

id로 &quot;product2&quot; 및 &quot;product3&quot;을 사용하는 두 개체가 포함된 listObject를 반환합니다.
