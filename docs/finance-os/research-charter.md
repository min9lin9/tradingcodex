# G0 Research Charter

## 1. 프로그램 명제

Finance OS는 금융 업무 전반을 한 번에 대체하는 소프트웨어가 아니다. 첫 단계에서는 특정 고객이 반복적으로 수행하는 업무 하나를 선택해 다음을 검증한다.

- 실제 문제의 강도와 빈도
- 구매자와 예산 경로
- 데이터 접근·저장·파생·표시·재배포 권리
- 정확도와 검토시간을 측정할 수 있는 기준선
- 관할별 규제·책임·기록보존 경계
- AI가 보조할 부분과 결정론적 통제가 맡을 부분
- 상용 제품, 오픈소스, 자체개발 중 최적 경로

## 2. 90일 연구 질문

1. 어느 회사 유형의 어떤 역할이 가장 반복적이고 비싼 금융 운영 문제를 갖는가?
2. 그 문제는 기존 Excel·이메일·터미널·ERP·BPO·내부 스크립트로 왜 충분히 해결되지 않는가?
3. 누가 사용하고, 누가 검토·승인하며, 누가 예산을 소유하는가?
4. 정답·오류·누락·재작업·마감 실패를 어떻게 측정하는가?
5. P0 데이터는 합법적이고 안정적으로 확보 가능한가?
6. 제품 행동이 Information, Drafting, Decision Support, Recommendation, Order Preparation, Execution 중 어디에 속하는가?
7. 동일 업무를 수행할 OSS·상용·내부개발 후보는 무엇이며, 어떤 Knockout Gate를 통과하는가?
8. 8주 안에 닫힌 Minimum Vertical Slice를 만들 수 있는가?
9. 이 팀이 고객 접근, 한국 금융 데이터, 에이전트 도구화 또는 통제 설계에서 가질 수 있는 Right-to-win은 무엇인가?
10. 첫 워크플로와 두 번째 워크플로에서 반복되는 Capability가 확인되는가?

## 3. 범위

### 포함

- 고객·구매자·승인자 Discovery
- 프론트·미들·백오피스 업무 재구성
- 데이터·OpenAPI·상용 데이터 권리 조사
- 표준·Canonical Domain Model 조사
- OSS·상용 벤더 Landscape와 Bake-off
- AI·모델 위험, 보안, 운영 복원력
- G1–G4 의사결정과 MVS 계획

### 초기 제외

- 무승인 자율 실거래
- 전체 은행 Core Banking
- 포괄적인 KYC 고객 온보딩
- 파생상품 전 자산 가격평가
- 다기관 멀티테넌트 SaaS
- 초저지연·고빈도 매매
- 외부 고객용 투자자문·일임 기능
- 규제 보고, NAV 또는 원장의 무검토 최종 확정

## 4. 활성 탐색 제한

- Week 1 Desk Scan: Wedge 최대 6개
- Week 2부터 활성 고객 세그먼트: 최대 2개
- Week 2부터 깊은 인터뷰 Wedge: 최대 2개
- G3 Shortlist: Capability별 최대 2–3개 후보
- 동시 기술 Spike: 최대 2개
- Wedge가 선택되기 전 제품 코드 개발 금지

## 5. 조사 단위: TACDERT

모든 업무는 다음 필드로 기록한다.

```yaml
task:
trigger:
actor:
reviewer:
approver:
inputs:
data_sources:
systems_used:
steps:
outputs:
state_changes:
controls:
exceptions:
deadlines_and_cutoffs:
evidence_retained:
retention:
pain_points:
baseline_metrics:
automation_candidate:
human_authority_required:
```

## 6. Gate 체계

| Gate | 질문 | 필수 판정 |
|---|---|---|
| G0 | 조사 범위·역할·예산·증거 규칙이 명확한가? | PASS / REVISE |
| G1 | 실제 고객·구매자·업무 증거로 Wedge를 선택할 수 있는가? | SELECT / NARROW / PIVOT / PAUSE / STOP |
| G2 | 데이터·권리·규제·품질·보안상 실현 가능한가? | PASS / BLOCK / PIVOT |
| G3 | 비교 가능한 후보 2–3개가 Hard Gate를 통과했는가? | SHORTLIST / RESEARCH MORE / STOP |
| G4 | Adopt / Buy / Build 결정이 재현 가능한 근거를 갖는가? | APPROVE / REWORK / STOP |
| G5 | MVS가 하나의 업무 생명주기를 닫는가? | PASS / FIX / STOP |
| G6 | Shadow Pilot이 품질·생산성·운영·구매 기준을 만족하는가? | SCALE / NARROW / STOP |

## 7. 역할과 책임

| 역할 | 책임 |
|---|---|
| Program Owner | 최종 우선순위·예산·Gate 결정 |
| Product Research Lead | 고객 인터뷰, Wedge 비교, 기준선 |
| Domain Reviewer | 금융 업무·통제·예외 검증 |
| Data & Rights Lead | 데이터 계약, 권리 증적, 품질 SLO |
| Architecture Lead | 후보 Spike, State Ownership, ADR |
| Security/Risk Reviewer | 위협모델, 권한, 기록, 규제 Trigger |
| Independent Challenger | 반대 가설, 증거 과장, Stop 조건 검토 |

한 사람이 여러 역할을 수행할 수 있으나, Wedge 제안자와 최종 Challenger는 가능하면 분리한다.

## 8. 증거 규칙

- 주장과 관찰을 분리 기록한다.
- 인터뷰는 최근 실제 사건을 중심으로 진행한다.
- 솔루션을 설명하기 전에 현재 업무를 재구성한다.
- 실제 파일·로그·화면과 인터뷰 진술을 별도 증거로 보존한다.
- 모든 증거에는 출처, 수집일, 소유자, 민감도, 사용 허가, 관련 가설을 붙인다.
- 데이터·법률·보안 결론이 불명확하면 통과가 아니라 `BLOCKED`다.
- Score는 Gate를 대체하지 않는다.

## 9. Wedge 선택 최소 증거

- 인터뷰 10–15건
- 최소 3개 조직
- 사용자 5명 이상
- 구매·예산 책임자 2명 이상
- Risk·IT·승인자 2명 이상
- 실제 또는 익명화 산출물 5개 이상
- 최근 90일 내 End-to-End 사건 3개
- 예외·실패 사례 10개 이상
- 처리시간·Reviewer Time·오류·재작업·마감·비용 기준선
- 최소 2개 조직 C2와 그중 1개 구매자 확인, 또는 1개 조직 C3
- 현재 대안 3개 이상

### Commitment 단계

```text
C0 관심 표현
C1 후속 인터뷰·자료 제공
C2 구체적 파일럿 범위·담당자·일정 논의
C3 LOI, 유료 파일럿 또는 조달 절차 개시
C4 계약·지불
```

## 10. 고객 증거 Hard Stop

- 실제 파일·로그·화면 없이 의견만 존재
- 사용자는 원하지만 구매자·예산경로가 없음
- 한 조직·한 Champion 증거만 존재
- 문제 빈도가 낮고 단가·위험도 낮음
- 기존 도구의 작은 설정 변경으로 해결 가능
- 정확도 또는 검토시간의 기준선을 만들 수 없음
- P0 데이터 권리를 확인할 수 없음

## 11. 후보 기술 Hard Gate

| ID | Gate |
|---|---|
| K1 | P0 업무 입력·산출물·예외·통제를 지원하는가? |
| K2 | 코드·데이터의 내부·상업 사용 조건이 충족되는가? |
| K3 | 비밀정보·권한·실행을 분리하고 감사할 수 있는가? |
| K4 | 입력·버전·결과를 재생하고 차이를 설명할 수 있는가? |
| K5 | 장애·지연·수정·중복 요청에서 안전하게 실패하는가? |
| K6 | 중단·가격·라이선스 변경 시 이관 가능한가? |
| K7 | 내부 사용 맥락에서 독립 검증 가능한가? |

하나라도 실패하면 `DEFER` 또는 `REJECT`한다.

## 12. 예산 Guardrail

G0에서 다음 상한을 명시하고 초과 시 Gate 재승인을 요구한다.

- 데이터·API Probe 비용
- 외부 전문가·법률 검토 비용
- 클라우드·모델 사용료
- 후보 설치·운영 인프라 비용
- 인터뷰·Design Partner 지원 비용
- 팀 주간 Capacity

무료 API·오픈소스도 통합·운영·보안·Exit 비용을 포함한 3년 TCO로 비교한다.

## 13. G0 통과 조건

- [ ] 90일 목표와 비목표 승인
- [ ] 역할과 Gate RACI 지정
- [ ] 활성 세그먼트·Wedge·Spike WIP 제한 승인
- [ ] 증거 수준·Decision 상태·Commitment 정의 승인
- [ ] 인터뷰·산출물 요청 템플릿 준비
- [ ] Assumption, Evidence, Decision Register 생성
- [ ] 예산과 팀 Capacity 상한 승인
- [ ] 데이터·보안·법률 검토 Trigger 승인
- [ ] Day 10 G1 Pre-read 일정 지정

## 14. 첫 10 Business Days

### Day 1

- Charter와 RACI 확정
- Evidence/Decision/Assumption Register 시작
- 예산·Capacity·WIP 확정

### Day 2

- Desk Scan으로 세그먼트 최대 2개
- 인터뷰 대상 15명 구성: 사용자 8, 구매자 3, 승인·IT·Risk 4
- Wedge 가설 최대 3개

### Day 3–5

- 인터뷰 5–6건
- 실제 업무 샘플 2개 이상
- 최근 실패·예외 사건 3개
- 경쟁대안·현재 지출 기록

### Day 6

- 활성 Wedge 최대 2개
- 공식 데이터 Probe 범위
- Rights Evidence와 Data Flow 초안

### Day 7–8

- 공식 데이터 2개 E2 Probe
- 후보 1개 설치는 선정이 아닌 Harness 검증용
- Golden Snapshot과 Baseline Task 생성

### Day 9

- 정규화 Wedge Score
- Buyer/Commitment·Right-to-win 업데이트
- 독립 반증 Review

### Day 10

- G1 Pre-read
- 부족 증거와 다음 10일 결정
- STOP/PIVOT 조건 확정
