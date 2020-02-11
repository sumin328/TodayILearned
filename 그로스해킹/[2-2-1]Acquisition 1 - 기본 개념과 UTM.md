# AARRR

# Acquisition 1 - 기본 개념과 UTM

## Acquisition
사용자를 우리 서비스로 데려오기

### 사용자 구분 1
- 자발적으로 우리 서비스를 찾아오는 고객 (Organic)
- 마케팅 활동으로 인해 우리 서비스를 찾아온 고객 (Paid)

### 생각할 문제
- 어떻게 하면 Organic 유입을 늘릴 수 있을까?
- 어떻게 하면 Paid 채널을 효율적으로 사용할 수 있을까?
- Organic은 불명확하기 때문에 위와 같은 구분은 추천하지 않음

### 사용자 구분 2
- Facebook 광고를 보고 들어온 고객
- 친구초대를 통해 들어온 고객
- 제휴 마케팅을 통해 들어온 고객
- ...
- 어떻게 들어왔는지 알 수 없는 고객 (unknown)
- Organic과 Unknown을 혼동하지 말자

### 생각할 문제
- 어떻게 하면 사용자의 유입 채널을 정확하게 추적하고, 
- 각 채널별 성과를 정확히 판단할 수 있을까?

## Acquisition 관련 기본 지표

### 유저 획득 지표
- signup : 가입 회원
- CAC (Customer Acquisition Cost) : 유저 획득 비용

### 광고 집행 관련 지표
- CPC (Cost Per Click) - 클릭 당 과금되는 광고상품
- CPI (Cost Per Install) - 인스톨 당 과금되는 광고상품
- CPA (Cost Per Action) - 액션 당 과금되는 광고상품 (일반적으로는 complete_registration)
- CRM (Cost Per Mille) - 노출 당 과금되는 광고상품
- CPP (Cost Per Period) - 기간 보장형 광고상품
- ROAS (Return on Ads Spending) - 광고로 인한 매출액 / 광고비

## Acquisition 한 줄 요약
- CAC (Customer Acquisition Cost) <<< LTV (Lifetime Value)
- LTV : 사용자 한 명의 누적 가치
- 회사의 생존이 걸려있는 수식
- 정확하게는 CAC*n < LTV
- 같은 비율이라면 LTV을 증가시키는게 CAC를 감소시키는 것보다 효과적임
- 둘 중 어느 지표 CAC가 더 Controllable함

### CAC
- 유저 획득 비용
- 하나의 요약된 숫자라고 보지 말고, 채널/캠페인/날짜에 따라 쪼개서 살펴봐야 함
- 어느 채널에 어느 캠페인으로 어느 기간동안 얼마의 예산을 집행할 것인가?
- 그 효과는 어떠한가?

## UTM parameter
- Urchin Tracking Module 의 약자 
- 어느 경로를 통해서 들어왔는지 (출처를) 확인할 수 있도록 하는 파라미터
- 어느 채널에, 어떤 내용으로 마케팅 비용을 집행하는 게 가장 효과적일까?
- 링크 URL + ?
    - utm_source : 어디에서 왔나?
    - utm_medium : 어떤 유형의 링크인가?
    - utm_campaign : 어떤 캠페인을 통해서 왔나?
    - utm_term : 어떤 키워드로 검색해서 왔나?
    - utm_content : 어떤 내용을 보고 왔나?
- UTM 링크를 만들 수 있는 툴을 google이 제공함
    - Campaign URL Builder
    - Tracking은 google analytics에서 할 수 있음