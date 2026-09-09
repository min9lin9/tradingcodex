# Finance OS 12-Week Execution Plan

## 단일 목표

90일 안에 Production-ready Finance OS를 만들지 않는다. 한 개의 고객 세그먼트와 한 개의 반복 업무를 선택하고 고객·구매·데이터 권리·규제·품질 기준을 검증한 뒤, 후보 비교와 Adopt / Buy / Build 결정을 완료한다.

## 운영 Cadence

| 주기 | 회의 | 목적 |
|---|---|---|
| 매일 15분 | Evidence Stand-up | 새 증거, Blocker, 다음 관찰 |
| 주 2회 | Research Review | 인터뷰·산출물·Probe 품질 검토 |
| 주 1회 | Risk & Rights Review | 데이터 권리, 보안, 규제 Trigger |
| Gate 전 | Independent Challenge | 반대 가설, 과장, 누락, Stop 검토 |
| Gate Day | Decision Meeting | PASS/NARROW/PIVOT/STOP 기록 |

회의는 결과물을 대체하지 않는다. 모든 결정은 Decision Register와 근거 링크를 남긴다.

## Week 1 — G0와 탐색 설계

### 작업

- [ ] Research Charter 승인
- [ ] Program Owner, Research Lead, Domain Reviewer, Data/Rights, Architecture, Risk, Challenger 지정
- [ ] 예산·Capacity·WIP 상한 확정
- [ ] Assumption·Evidence·Decision Register 시작
- [ ] Wedge 최대 6개 Desk Scan
- [ ] 활성 세그먼트 최대 2개 선정
- [ ] 인터뷰 대상 15명 모집 목록
- [ ] Artifact 요청·보안·익명화 절차 준비

### Exit

- G0 PASS
- 역할·예산·증거 규칙 승인
- 활성 세그먼트 최대 2개

## Week 2–3 — 고객·업무 증거

### 작업

- [ ] 인터뷰 8–12건
- [ ] 실제 업무 샘플 3개 이상
- [ ] 최근 90일 사건 3개 이상 TACDERT 재구성
- [ ] 예외·실패·재작업 10개 수집
- [ ] 처리시간, Reviewer Time, 오류, 마감, 비용 기준선
- [ ] 현재 도구·BPO·내부 스크립트·아무것도 안 함 비교
- [ ] 구매자, 예산, 보안·법무·IT 조달 경로
- [ ] 활성 Wedge 최대 2개로 축소

### Exit

- G1 Pre-read 초안
- 각 Wedge의 부족 증거와 Kill Criteria 명시

## Week 4 — G1 Segment + Wedge

### 작업

- [ ] 정규화 Evidence-adjusted Score 계산
- [ ] 사용자·구매자·승인자 증거 분리
- [ ] 첫 20개 접근 가능 계정 목록
- [ ] Design Partner 후보와 Commitment 단계
- [ ] Right-to-win·전환비용·유통 가설
- [ ] 반대 가설과 Independent Challenge

### 결정

```text
SELECT | NARROW | PIVOT | PAUSE | STOP
```

### Exit

- 고객 세그먼트 1개
- 구매자 역할 1개
- 반복 업무 1개
- P0 데이터와 8주 MVS 범위

## Week 5–6 — G2 Feasibility

### 작업

- [ ] P0 Data Contract
- [ ] 공식 API 2개 이상 E2 Probe
- [ ] 원천 Snapshot과 Content Hash
- [ ] event_time / knowledge_time / ingested_at 분리
- [ ] Data Quality SLO
- [ ] Access·Storage·Derived·Model Input·Display·Redistribution Rights Matrix
- [ ] 약관·계약·Entitlement 증적
- [ ] Regulatory Perimeter
- [ ] Data Flow·Privacy·Security 분류
- [ ] Golden Snapshot 1차
- [ ] Manual Fallback과 Degraded Mode

### Exit

```text
G2 PASS | BLOCK | PIVOT
```

P0 데이터 권리 또는 품질 측정성이 불명확하면 PASS 금지.

## Week 7–8 — G3 Shortlist

### 작업

- [ ] Capability Map 확정
- [ ] 공식·상용·OSS·자체구현 Longlist
- [ ] 유형별 후보 비교
- [ ] K1–K7 Knockout Gate
- [ ] 후보 2–3개 설치·Probe
- [ ] 라이선스·공급망·보안·운영 실사
- [ ] 3년 TCO Range
- [ ] Exit Path
- [ ] Buy 대안 포함

### Exit

- 후보 2–3개
- 각 후보의 E2 증거
- 제외 후보와 근거

## Week 9–11 — E3 Bake-off

### 공통 원칙

- [ ] 성공 지표·실패 조건 사전등록
- [ ] 동일 입력 Snapshot과 동일 Cut-off
- [ ] Human Baseline
- [ ] Deterministic Baseline
- [ ] Single Agent Baseline
- [ ] External Candidate Baseline
- [ ] Holdout과 Blind Review
- [ ] Raw Result, Log, Version, Cost 보존

### Suite A — 데이터·공시

- 정정공시 전후 차이 탐지
- XBRL 계정 정규화
- Point-in-time 재현
- 지연·중복·누락·Provider 불일치

### Suite B — 리서치·에이전트

- Claim Support Rate
- Citation Completeness
- Material Numeric Error
- Contrary Evidence Coverage
- Reviewer Time
- Tool Selection·Loop·Unsupported Claim

### Suite C — 정책·주문·실행

- 정책 차단 정확도
- 승인 Payload Binding
- 중복 제출 방지
- 부분체결·취소·재시도
- 권한 우회와 비밀정보 노출

### Suite D — 대사·원장

- 현금·포지션 Break 탐지
- 원인 분류
- Corporate Action
- Fee·FX·Settlement Date
- 수정분개·이중분개 방지

### Suite E — 보안·복원력

- Prompt Injection
- 권한 상승
- Secret Leakage
- 외부 Egress 차단
- Provider 장애·Rate Limit
- Backup·Restore·Replay

### Suite F — 보고·UX

- 수치·출처 정확성
- 변경이력
- 접근성·가독성
- PDF·Excel·Markdown Export
- Reviewer 수정량

## Week 12 — G4 Adopt / Buy / Build

### 산출물

- [ ] Adopt / Buy / Build ADR
- [ ] State Ownership
- [ ] MVS Architecture
- [ ] 계약·Interface 초안
- [ ] 8주 Build Plan
- [ ] Acceptance Test
- [ ] Design Partner 합의 초안
- [ ] Pilot Success·Kill Criteria
- [ ] Budget·Capacity 승인

### 결정

```text
APPROVE | REWORK | STOP
```

## Month 4–5 — G5 Minimum Vertical Slice

MVS는 하나의 업무 생명주기를 닫아야 한다.

```text
Trigger
→ Authorized Data Ingestion
→ Source Snapshot
→ Deterministic / AI Processing
→ Review
→ Approval
→ State Change or Final Artifact
→ Reconciliation / Validation
→ Audit Export
```

### G5 Acceptance

- P0 입력과 출력 100% Lineage
- Material Numeric Error 0
- 승인 우회 불가
- 재시도 시 중복 상태변경 0
- Degraded Mode 동작
- 모든 상태 변경 Audit Event
- 비밀정보가 Prompt·Report·Log에 노출되지 않음

## Month 5–6 — G6 Shadow Pilot

- 실제 업무와 병행하되 시스템 출력은 최종 행동을 직접 확정하지 않음
- Blind Review와 Reviewer Time 측정
- 오류·누락·지연·복구·사용자 수정 기록
- 유료 파일럿 또는 조달 절차 검증

### Pilot 판정

```text
SCALE | NARROW | STOP
```

## 10-Day Starter Board

### Day 1
- [ ] G0 Charter 승인
- [ ] 역할·RACI
- [ ] 예산·Capacity·WIP
- [ ] Register 생성

### Day 2
- [ ] 세그먼트 최대 2개
- [ ] 인터뷰 대상 15명
- [ ] Wedge 최대 3개

### Day 3–5
- [ ] 인터뷰 5–6건
- [ ] 업무 샘플 2개
- [ ] 실패·예외 사건 3개
- [ ] 경쟁대안·현재 지출

### Day 6
- [ ] 활성 Wedge 최대 2개
- [ ] 공식 데이터 Probe 범위
- [ ] Rights Evidence·Data Flow 초안

### Day 7–8
- [ ] 공식 데이터 2개 E2 Probe
- [ ] 후보 1개 Harness 설치
- [ ] Golden Snapshot·Baseline Task

### Day 9
- [ ] Wedge Score
- [ ] Buyer·Commitment·Right-to-win
- [ ] 반증 Review

### Day 10
- [ ] G1 Pre-read
- [ ] 부족 증거와 다음 10일
- [ ] STOP/PIVOT 조건

## 프로젝트 Kill Criteria

- 구매자·예산 경로가 반복 확인되지 않음
- P0 데이터 권리를 확보할 수 없음
- 정답·오류·검토시간 기준선을 만들 수 없음
- 기존 대안 대비 생산성·품질 개선 가능성이 낮음
- 필요한 책임·규제 범위가 팀 역량을 초과함
- 8주 MVS로 하나의 생명주기를 닫을 수 없음
- 고객이 자료·시간·파일럿 Commitment를 제공하지 않음

Kill은 실패가 아니라 잘못된 범용 플랫폼 개발을 막는 성공적인 의사결정이다.
