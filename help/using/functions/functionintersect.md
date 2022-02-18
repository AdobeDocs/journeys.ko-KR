---
product: adobe campaign
title: intersect
description: 함수 교차에 대해 알아보기
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# 교차{#intersect}

두 입력 목록의 공통 값을 반환합니다. 두 목록 중 하나가 null이면 는 빈 목록을 반환합니다.

## 카테고리

목록

## 함수 구문

`intersect(<parameters>)`

## 매개 변수

| 매개 변수 | 유형 |
|-----------|------------------|
| 목록 1 | 목록에 있는 참조 페이지를 나타냅니다 |
| 목록 2 | 목록에 있는 참조 페이지를 나타냅니다 |

## 서명 및 반환된 형식

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

목록을 반환합니다.

## 예시

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

반환 [&quot;sports&quot;, &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

프로필 속성과 지정된 카테고리 목록 사이의 공통 항목을 반환합니다.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

프로필 속성과 주어진 이벤트 필드 사이의 공통 항목을 반환합니다.
