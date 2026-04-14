# 02. Job→MVP Feature Map & 기능 우선순위 정리

**작성 목적**: JTBD 인터뷰와 AOS-DOS 분석에서 도출된 고객의 Job을 구체적 MVP 기능 스펙으로 번역하고, 개발 우선순위를 확정함.

---

## A. Job → Feature 변환 테이블

| JTBD Job Statement | 대응 Pain ID (DOS 순위) | MVP Feature 후보 | Feature 유형 |
| :--- | :--- | :--- | :--- |
| 특수 양식을 무결점 정형 데이터로 구조화 | C2 (DOS 3.60, 1위) | 무결점 Table & Form Parser | **Core Engine** |
| AI 오류를 인간이 효율적으로 색출 | CJM-5 (DOS 3.20, 3위) | Confidence Score 에러 하이라이터 UI | **Trust Layer** |
| 기존 툴 변경 없이 흩어진 데이터 통합 | C1 (DOS 2.70, 4위) | One-Click API 백그라운드 커넥터 | **Integration** |
| 클라우드 유출 없는 사내 처리 보장 | CJM-3 (DOS 2.70, 4위) | PII 오토 마스킹 & 하이브리드 배포 | **Compliance** |
| 영수증 등 다중 포맷 일괄 구조화 | A1 (DOS 2.40, 6위) | 멀티 포맷 어댑터 (PDF/Image/Fax) | **Scale Engine** |
| 마이그레이션 노동 제거 | CJM-4 (DOS 1.92, 7위) | 드라이브/워크스페이스 자동 동기화 | **Onboarding** |

---

## B. MVP 스프린트 배치 (Phase 구분)

### Phase 1: "신뢰 획득" (Day 1–90) — PoC 무기 확보
| 순위 | Feature | DOS | 목표 |
| :---: | :--- | :---: | :--- |
| P1 | 무결점 Table & Form Parser | 3.60 | 로펌 PoC에서 기존 OCR 대비 오류율 54%→8% 이하 입증 |
| P2 | Confidence Score 에러 하이라이터 UI | 3.20 | "붉은색만 보면 된다" → 검수 시간 87% 절감 체험 제공 |

### Phase 2: "확산 무기" (Day 91–180) — SOM 45개사 공략 개시
| 순위 | Feature | DOS | 목표 |
| :---: | :--- | :---: | :--- |
| P3 | One-Click API Connector | 2.70 | 스타트업 CTO의 "당장 팀 계정 결제" 전환 달성 |
| P4 | PII 오토 마스킹 & 하이브리드 배포 | 2.70 | B2B 경영진 결재 최종 관문(보안 컴플라이언스) 돌파 |

### Phase 3: "캐시카우 확장" (Day 181+) — Adjacent 시장 진입
| 순위 | Feature | DOS | 목표 |
| :---: | :--- | :---: | :--- |
| P5 | 멀티 포맷 어댑터 | 2.40 | 회계법인 결산 시즌 시장 진입 (반복 매출 확보) |
| P6 | 워크스페이스 자동 동기화 | 1.92 | 온보딩 이탈률 70% 구간 제거 |

### ⛔ Drop Zone: 초기 런웨이 투입 금지
| Feature | AOS | DOS | 보류 사유 |
| :--- | :---: | :---: | :--- |
| Zero-config 카메라/음성 모듈 | 3.2 | 0.96 | 제조업 시장 채택 속도(MR 0.3) 최악. 감동적이나 돈이 안 됨 |

---

## C. Feature 간 의존성 및 기술 시너지 맵

```
[P1: Table Parser] ──────────────────────┐
       │                                 │
       ▼                                 ▼
[P2: Confidence UI] ← 신뢰도 점수 의존    [P5: 멀티포맷 어댑터]
       │                                      │
       ▼                                      ▼
[P4: PII 마스킹] ← 파싱 결과물 후처리     [A1: 회계 시장 진출]
       │
       ▼
[P3: API Connector] ← 마스킹된 데이터의 안전한 연동
```

**핵심 의존성**: P1(파서)이 모든 후속 기능의 기반. P1 없이 P2~P6는 존재할 수 없음.
→ 따라서 P1의 품질 확보가 전체 사업의 성패를 결정하는 단일 병목(Single Point of Failure)임.
