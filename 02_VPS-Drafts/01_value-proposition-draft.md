# 01. VPS 교차 분석 워크시트 (Cross-Reference Analysis)

**작성 목적**: 6개 선행 분석 문서의 핵심 데이터를 '가치 제안' 관점에서 교차 매핑하여 VPS 본문 작성의 논리적 토대를 구축함.

---

## A. 데이터 원천 → VPS 항목 매핑 테이블

| VPS 항목 | 1차 데이터 원천 | 2차 보강 원천 | 교차 검증 포인트 |
| :--- | :--- | :--- | :--- |
| **고객별 핵심 문제 (Pain/Needs)** | `7_Persona-spectrum-map.md` (Zone 정의) | `8_customer-journey-map.md` (Pain Point 열) | 여정 지도의 '감정' 열이 페르소나 고통의 실제 강도를 뒷받침하는가? |
| **JTBD 관점 고객 목표 (Goal/Job)** | `10_jtbd-interview-report.md` (JTBD 요약 카드) | `9_aos-dos-analysis.md` (AOS 점수) | JTBD 선언의 긴급성이 AOS 상위권(≥3.0)과 일치하는가? |
| **고객이 원하는 Outcome** | `10_jtbd-interview-report.md` (Outcome 목록) | `8_customer-journey-map.md` ('유지' 단계 감정) | Outcome이 측정 가능한 수치(시간, 비율)로 표현되었는가? |
| **핵심 가치 제안 (VP)** | `9_aos-dos-analysis.md` (DOS 1~4위) | `10_jtbd-interview-report.md` (Pull Force) | DOS 최상위 항목이 JTBD의 Pull과 정합하는가? |
| **기존 대안 (Competitor)** | `2_competents-analysis.md` (5개사 브리핑) | `10_jtbd-interview-report.md` (Current Solutions) | 경쟁사가 커버하지 못하는 SME 영역이 명확한가? |
| **차별적 가치** | `6_TAM-SAM-SOM.md` (SOM 진입 논리) | `7_Persona-spectrum-map.md` (상호작용 분석) | SOM 타겟의 '지불 트리거'가 차별적 가치와 직결되는가? |
| **Proof (근거)** | `9_aos-dos-analysis.md` (정량 지표) | `10_jtbd-interview-report.md` (인터뷰 인용문) | 정량 + 정성 증거가 모두 확보되었는가? |

---

## B. 핵심 발견: 교차 분석에서 드러난 3가지 구조적 일관성

### 발견 1: "환각 공포"는 모든 분석에서 반복 등장하는 최상위 키워드
- **경쟁사 분석**: 범용 OCR은 표/양식 파괴 → CorpBrain의 진입 틈새
- **AOS-DOS**: C2(표 파싱 실패) DOS 3.60 → 전항목 중 1위
- **CJM**: 이지언 '문제 인식' 단계 감정 = 분노, 공포
- **JTBD**: "숫자 한 번 밀리면 실사 보고서 하나로 로펌 문 닫습니다"
- **결론**: 환각 리스크 제거는 단순 기능이 아니라 '생존 보험'으로 포지셔닝해야 함

### 발견 2: "무마찰 도입"은 CTO와 로펌 모두의 공통 Anxiety 해소 키
- **페르소나 맵**: 김동현(CTO) '진입 마찰 낮음' 축 좌측 배치 (0.25)
- **CJM**: 김동현 '의사결정' 단계 = "보안 문제 없이 하루 만에 도입 가능?"
- **JTBD 4 Forces**: 양쪽 모두 Anxiety의 핵심이 '기존 환경 파괴 우려'
- **결론**: 'Zero-Friction 원칙'은 VP Sheet 전체를 관통하는 설계 철학이 되어야 함

### 발견 3: "시간 단축" Outcome은 정량화가 가능하며, 세일즈 무기로 전환 가능
- **로펌**: 수작업 검수 4h → 30min (87.5% 감소)
- **스타트업**: 온보딩 1주일 → 수시간 (약 85% 감소)
- **회계법인**: 결산 마감 기간 50% 단축
- **결론**: "시간 절감"을 단순 편의가 아닌 '인건비 ROI'로 환산하여 경영진 설득 도구화

---

## C. 비타겟 경계선 확인 (Anti-Target Validation)

| 비타겟 ID | 왜 배제하는가 (근거 문서) | 혼동 위험 시나리오 |
| :--- | :--- | :--- |
| N4-1 최재벌 (금융권) | DOS = 0.00, MR = 0.0 (`9_aos-dos`) / 영업 6개월 소진 후 드랍 (`7_Persona`) | "대형 레퍼런스" 유혹에 빠져 SI 외주화 |
| N4-2 차지연 (B2C) | DOS = 0.04, WTP 부재 (`9_aos-dos`) / 챗GPT 월 2만원으로 충분 (`8_CJM`) | 무료 트라이얼 남용으로 서버 비용만 증가 |
| E3-1 오석동 (제조업) | AOS 3.2이나 DOS 0.96 (`9_aos-dos`) / 채택 속도 최악 MR 0.3 | "감동적 스토리"에 현혹되어 MVP 스펙이 비대해짐 |
