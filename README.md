# Strategic Mineral Supply Chain Early Warning System (K-EWS)

## Overview
한국 배터리 산업은 핵심 원자재를 특정 국가에 과도하게 의존하고 있으며, 지정학적 충격 발생 시 공급망 전반에 심각한 영향을 받을 수 있다.
본 프로젝트는 관세청 수출입 실거래 데이터(2015~2025)를 활용하여 전략광물 공급망 위험을 정량화하고, 실시간 조기경보체계(K-EWS)를 구축하는 것을 목표로 하였다.

## Research Question
- 한국 배터리 공급망은 얼마나 특정 국가에 집중되어 있는가?
- 지정학적 리스크는 실제 산업 가격에 어떤 경로로 전파되는가?
- 공급망 충격을 조기에 탐지할 수 있는가?
- 정부 위기경보 체계와 연결 가능한 정량 모델을 구축할 수 있는가?

## Dataset
### Data Sources: 
- 관세청 수출입 실적 데이터 (2015~2025)
- GPR (Geopolitical Risk Index)
- GSCPI (Global Supply Chain Pressure Index)
- 한국은행 PPI
- 배터리 수출단가 데이터
### Analysis Period: 2015.01 ~ 2025.12 (132개월)

### My Contributions
1. 전략광물 선정 프레임 설계: 3개 기준을 활용하여 핵심 광물 선정
- HHI 기반 수입 집중도
- 국내 자급률
- 산업 파급력

최종 선정
- 기타흑연
- 인상흑연
- 탄산리튬
- 수산화리튬
- 희토류화합물

2. 공급망 위험 변수 구축
- 생성 변수: 
- HHI
- 수입단가
- 물동량
- 물동량 변화율
- GPR
- GSCPI
- 공급망 구조와 가격 충격을 동시에 반영하는 Feature Engineering 수행.

3. 인과관계 분석
- Granger Causality Test
- 시차 효과 분석
- 지정학 리스크 → 원자재 가격 → 산업 가격으로 이어지는 전파 구조 분석.

4. 한국 전략광물지수(K-SCI) 개발
: 지정학 리스크와 공급망 압력을 통합한 복합 위험지수 구축.

5. 조기경보시스템(K-EWS) 설계
- Green, Yellow, Red
- 3단계 신호등 위험 경보 체계 구축.
- 기존 정부 공급망 위기경보 체계와 연동 가능한 구조로 설계.

### Key Findings
- 기타흑연 대중국 의존도 90% 이상 확인
- 주요 광물 HHI가 모두 5,000~8,000 수준으로 극단적 집중 상태
- 지정학 리스크가 수입단가보다 먼저 반응
- 공급망 충격은 T+1 → T+3 → T+6 구조로 산업 전반에 전파
- K-SCI는 주요 충격 사건을 85.7% 정확도로 탐지
- OOS 검증에서 핵심 사건 Recall 1.000 달성

## Tech Stack
Python · Pandas · Statsmodels · Scikit-Learn · Streamlit · Network Analysis
