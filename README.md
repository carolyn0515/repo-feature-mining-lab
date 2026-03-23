# Repository Feature Mining Pipeline (Practice Project)

본 저장소는 오픈소스 Repository의 건강도(Health)를 정량적으로 분석하기 위한
**Feature Discovery 및 Data Mining 파이프라인을 체계적으로 설계하고 실험하는 프로젝트**이다.

본 프로젝트의 목적은 완성된 평가 시스템을 구축하는 것이 아니라,
Repository 데이터를 기반으로 **논리적이고 단계적인 Feature 탐색 및 선별 과정**을 설계하는 데 있다.

즉, 실제 모델링 이전 단계에서 수행되는
**데이터 이해 → 신호 탐색 → Feature 구조화 → Time-series Signal 확보**까지의 전 과정을 다룬다.

---

## 프로젝트 목적

본 프로젝트는 다음과 같은 활용을 염두에 두고 진행되었다.

* Repository Health Modeling을 위한 Raw Signal Pool 구축
* Feature Engineering 기반 연구 준비
* Repository Behavior 분석을 위한 Time-series Feature Seed 확보
* 데이터 마이닝 파이프라인 설계 역량 강화

특히 다음과 같은 설계 원칙을 중심으로 진행된다.

* Endpoint 기반 데이터 구조 이해
* 정량적 신호 중심 Feature 선별
* Identity / Noise 정보 제거
* 시간 흐름에 따라 변화하는 행동 신호 확보
* 모델링 가능한 Feature Family 구성

---

## 전체 분석 파이프라인 구조

```
Repository 선정
→ API Endpoint 탐색
→ Health Indicator 기반 Endpoint 선별
→ JSON Key 전수 수집
→ 다단계 논리적 Feature Pruning
→ Repository-Level Feature Family 설계
→ Time-Series Signal Filtering
→ 최종 Raw Feature Pool 구축
```

---

## 1. Endpoint 탐색 단계

Repository 분석에 활용 가능한 GitHub API Endpoint를 전수 조사한다.

수행 내용:

* Repository JSON Schema 구조 파악
* Endpoint 후보 목록 수집
* 각 Endpoint가 제공하는 정보의 성격 분석
* 데이터 타입 및 구조 탐색

산출물:

* Endpoint 후보 목록
* Endpoint Schema Preview Table

---

## 2. Health Indicator 기반 Endpoint 선별

Repository 건강도와 관련된 신호를 포함하는 Endpoint만을 선별한다.

Health Indicator 축 예시:

* Community Activity
* Project Sustainability
* Development Productivity
* Governance 및 Reliability
* Project Maturity

수행 내용:

* Endpoint와 Indicator 간 Mapping 수행
* 정량적 측정 가능성 평가
* 중복 정보 여부 판단
* 최종 분석 대상 Endpoint 확정

산출물:

* Indicator–Endpoint Mapping Table
* 최종 Endpoint Selection 결과

---

## 3. Raw Feature Mining 단계

선별된 Endpoint 내부의 모든 JSON Key를 Feature 후보로 수집한다.

수행 내용:

* Recursive JSON Key Extraction 로직 구현
* Endpoint별 Key Inventory 구축
* Feature 후보 테이블 생성
* Indicator Tagging 수행

### 다단계 Feature Pruning 전략

Feature 후보는 다음 기준에 따라 단계적으로 정제된다.

1. URL 및 Hyperlink 정보 제거
2. 자연어 기반 Description / Text 정보 제거
3. 측정 불가능한 식별 문자열 제거
4. Count / Timestamp / Boolean / Numeric Ratio 등 정량 신호 유지
5. Nested Identity Attribute 제거
6. Endpoint 간 중복 Signal 제거

산출물:

* 축소된 Feature Candidate Pool
* Human Review Table

---

## 4. Repository-Level Feature Family 설계

Raw Key 수준의 Feature를 실제 분석 및 모델링이 가능한 구조로 재구성한다.

예시 Feature Family:

* Activity Velocity
* Contributor Concentration
* Release Cadence
* Issue Resolution Dynamics
* Pull Request Throughput
* Maintenance Latency

수행 내용:

* Feature Family Tagging
* Endpoint × Feature Family 요약
* Repository-Level Feature Seed 정의

---

## 5. Time-Series Signal Filtering 단계

최종적으로 **시간 흐름에 따라 변화하는 행동 신호만을 선별**한다.

평가 기준:

* Time-series Feature 생성 가능 여부
* Aggregation 가능성
* 모델링 Signal 강도
* Feature 중복 여부

최종 산출물:

**Repository-Level Time-Series Raw Signal Pool**

이 결과는 이후 다음 단계 연구에 활용될 수 있다.

* Feature Engineering
* Repository Health Score Modeling
* Repository 성장 예측 연구
* Behavior 기반 분석 모델 구축

---

