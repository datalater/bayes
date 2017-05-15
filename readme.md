ⓒ JMC 2017

**주요 소스**  
세상에서 가장 쉬운 베이즈통계학 입문, 고지마 히로유키

---

# 제 1강 정보를 얻으면 확률이 바뀐다

## 용어 정리

+ `사전확률` : 타입에 대한 확률
+ `정규화 조건` : 각 타입의 사전확률의 합이 1이 되도록 함
+ `조건부 확률` : 특정 타입이 특정 행동을 할 확률
    + 타입(원인)을 알고 있을 때의 결과의 확률

## Summary

베이즈 추정은 직감적인 판단을 수치화하여 계산할 수 있게 만들며, 이를 AI에 활용할 수도 있다.

## 베이즈 추정의 기본적인 사용 방법

### 스토리

+ 상품 판매점 점원은 손님이 '`쇼핑족`인가 아니면 `아이쇼핑족`인가'를 판별하고 싶다.
+ `쇼핑족`에게는 원하는 상품을 소개하여 실제로 구매하도록 유도해야 한다.
+ `아이쇼핑족`에게는 시간을 들여 설명해도 구매하지 않을 뿐더러 손님 입장에서 귀찮게 느끼므로 역효과이다.

### 1단계 : 경험에서 '사전확률'을 설정한다

+ 손님의 두 가지 타입을 나눈다
    + `쇼핑족`과 `아이쇼핑족`
+ 타입을 나누고 그 비율이 각각 몇인지 **경험에 비추어** 수치를 배정한다.
    + `쇼핑족` : 0.2
    + `아이쇼핑족` : 0.8
+ 단, 사전확률은 전부 더해서 1이 되도록 설정한다.

> **Note:** 사전확률은 보통 경험에 근거해 할당하지만, 경험이 없는 경우도 할당할 수도 있다. 추후 언급할 것이다.

### 2단계 : 타입별로 특정 행동에 대한 '조건부 확률'을 설정한다

+ 특정 행동은 반드시 상호배타적이어야 하며, 정규화 조건을 만족해야 한다.
+ `쇼핑족` 손님과 `아이쇼핑족` 손님이 각각 점원에게 '말 걸기' 행동을 할 확률을 **반드시 근거가 있는 경험에 비추어** 정한다.

| 타입 | 말을 걸 확률 | 말을 걸지 않을 확률 |
| :--- | :--- | :--- |
| 쇼핑족 (0.2) | 0.9 | 0.1 |
| 아이쇼핑족 0.8) | 0.3 | 0.7 |

+ 각 타입의 '말을 걸 확률'과 '말을 걸지 않을 확률'의 합은 1이다.
+ 위 표에 제시된 확률은 '조건부 확률'이다.

| 타입 | 쇼핑족 (0.2) | 아이쇼핑족 (0.8) |
| :--- | :--- | :--- |
| 말을 건다 (0.9, 0.3) | 0.18 | 0.24 |
| 말을 걸지 않는다 (0.1, 0.7) | 0.02 | 0.56 |

+ 전체 세계의 관점에서 각 타입이 특정 행동을 할 최종 확률은 위 표와 같다.

### 3단계 : 관측한 행동에서 '가능성이 사라진 세계'를 제거한다

+ 지금 손님이 말을 걸었다.
+ 손님의 행동을 한 가지 관측했으므로 가능성이 사라진 '말을 걸지 않는' 행동을 제거한다.

| 타입 | 쇼핑족 (0.2) | 아이쇼핑족 (0.8) |
| :--- | :--- | :--- |
| 말을 건다 (0.9, 0.3) | 0.18 | 0.24 |




---
