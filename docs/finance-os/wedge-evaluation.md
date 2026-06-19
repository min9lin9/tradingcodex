# Wedge Evaluation Framework

## 목적

Finance OS 전체를 제품으로 가정하지 않고, 첫 고객이 비용을 지불할 반복 업무 하나를 선택한다. 후보 간 비교는 기능 수나 기술 선호가 아니라 고객 증거, 데이터 권리, 품질 측정성, 규제 적합성, 8주 MVS 가능성으로 수행한다.

## 후보 Wedge

| ID | Wedge | 구매자 가설 | 핵심 산출물 | 주요 위험 |
|---|---|---|---|---|
| W1 | 공시 변경 인텔리전스 | 애널리스트·PM | 변경 감지, 수치·논지 영향, 노트 초안 | 기존 벤더 대비 차별성 |
| W2 | 투자위원회 Evidence Pack | PM·리스크·IC | 논지, 반대논거, 가치평가, 리스크, 승인기록 | 주관적 품질·책임 |
| W3 | 현금·포지션 대사 | 패밀리오피스·운용지원 | Break 탐지, 원인 분류, 증적·승인 | 계좌·데이터 통합 |
| W4 | GL 대사·월말 마감 | 펀드 관리자·재무팀 | 차이 원인, 분개 초안, 검토 패키지 | 회계 정확성·ERP 연동 |
| W5 | 모의주문 정책·감사 | 소형 운용팀·개발자 | 주문 티켓, 사전검사, 승인, Paper Fill | 실거래 전환 압력 |
| W6 | 정기 투자·운영 보고 | 운용사·패밀리오피스 | 일일·월간 보고서, 출처·변경이력 | 단독 가치·락인 부족 |

## 정규화 점수

각 기준은 1–5점으로 평가한다. 점수에 증거 신뢰도를 곱하며 최대값은 100이다.

```text
Normalized Evidence-adjusted Score
= Σ(weight_i × score_i / 5 × confidence_i)
```

### 증거 Confidence

| Evidence | Confidence |
|---|---:|
| E0 이름·주장만 존재 | 0.20 |
| E1 공식 문서·인터뷰 주장 | 0.40 |
| E2 실제 산출물·직접 API Probe | 0.70 |
| E3+ 측정·파일럿·계약 증거 | 1.00 |

## 평가 항목

| 기준 | 가중치 | 점수 | Confidence | 가중 결과 | 증거 링크 |
|---|---:|---:|---:|---:|---|
| 문제 강도·손실 | 15 |  |  |  |  |
| 빈도·긴급성 | 10 |  |  |  |  |
| 지불의사·예산 | 15 |  |  |  |  |
| 구매·조달 가능성 | 8 |  |  |  |  |
| 데이터·권리 실현성 | 15 |  |  |  |  |
| 품질 기준선 명확성 | 10 |  |  |  |  |
| 규제·책임 적합성 | 10 |  |  |  |  |
| 8주 MVS 실현성 | 10 |  |  |  |  |
| Right-to-win·유통 | 7 |  |  |  |  |
| **합계** | **100** |  |  |  |  |

## 판정 규칙

- `SELECT`: 75 이상, 모든 Hard Gate 통과, 구매자 증거 존재
- `NARROW`: 60–74 또는 세그먼트·범위가 넓음
- `PIVOT`: 60 미만 또는 더 강한 문제가 발견됨
- `PAUSE/STOP`: 데이터 권리·규제·구매 경로 Hard Gate 실패
- 데이터·권리, 규제·책임, 품질 측정성 중 하나가 3점 미만이면 SELECT 금지
- 상위 후보가 5점 차이 이내면 점수가 아니라 추가 증거의 Expected Value로 결정

## Wedge별 기준선 템플릿

### W1 공시 변경 인텔리전스

```yaml
trigger: 신규 또는 정정 공시
baseline:
  detection_latency:
  analyst_update_time:
  reviewer_time:
  missed_material_changes:
  false_positive_rate:
  revision_count:
quality_definition:
  material_change_recall:
  numeric_accuracy:
  citation_completeness:
```

### W2 투자위원회 Evidence Pack

```yaml
trigger: 신규 투자·증액·감액·매각 검토
baseline:
  preparation_time:
  reviewer_time:
  source_count:
  revision_rounds:
  errors_found_after_meeting:
quality_definition:
  claim_support_rate:
  contrary_evidence_coverage:
  valuation_reproducibility:
  decision_trace_completeness:
```

### W3 현금·포지션 대사

```yaml
trigger: 일일·주간 브로커/은행/내부 원장 수신
baseline:
  records_processed:
  breaks_detected:
  time_to_detect:
  time_to_resolve:
  unresolved_at_cutoff:
  false_break_rate:
quality_definition:
  break_recall:
  classification_accuracy:
  evidence_completeness:
  zero_duplicate_adjustment:
```

### W4 GL 대사·월말 마감

```yaml
trigger: 월말 마감 또는 계정 대사
baseline:
  close_duration:
  reviewer_hours:
  manual_journals:
  rework_count:
  material_errors:
  late_close_events:
quality_definition:
  tie_out_accuracy:
  journal_explanation_quality:
  approval_trace_completeness:
```

### W5 모의주문 정책·감사

```yaml
trigger: 전략 또는 사용자 주문 의도
baseline:
  tickets_created:
  policy_blocks:
  false_blocks:
  missed_blocks:
  duplicate_submissions:
  approval_time:
quality_definition:
  policy_determinism:
  idempotency:
  payload_approval_binding:
  audit_trace_completeness:
```

### W6 정기 투자·운영 보고

```yaml
trigger: 일일·주간·월간 Cut-off
baseline:
  preparation_time:
  reviewer_time:
  data_corrections:
  revision_rounds:
  late_delivery:
quality_definition:
  source_traceability:
  numeric_accuracy:
  narrative_consistency:
  change_history_completeness:
```

## 인터뷰 표본 설계

| 역할 | 최소 수 | 조사 초점 |
|---|---:|---|
| 실무 사용자 | 5 | 실제 단계, 파일, 예외, 재작업 |
| 구매·예산 책임자 | 2 | 현재 지출, 예산 단위, 조달 조건 |
| 승인·Risk·IT | 2 | 금지행동, 보안, 기록, 책임 |
| 조직 수 | 3 | 단일 조직 편향 방지 |

## 인터뷰 질문

1. 이 업무를 마지막으로 수행한 날짜는 언제인가?
2. 무엇이 업무를 시작시켰는가?
3. 어떤 파일·시스템·메신저·사람을 거쳤는가?
4. 작성자, 검토자, 승인자는 누구인가?
5. 어디서 오류·지연·재작업이 발생했는가?
6. Cut-off와 SLA는 무엇인가?
7. 결과가 틀렸을 때 금전·규제·평판 영향은 무엇인가?
8. 어떤 증적을 얼마나 보존하는가?
9. 현재 도구·데이터·인력·외주에 얼마를 지출하는가?
10. 구매 결정, 보안 검토, 조달은 누가 담당하는가?
11. 자동화가 절대 해서는 안 되는 행동은 무엇인가?
12. 기존 제품을 바꾸지 못하는 가장 큰 이유는 무엇인가?

## G1 Decision Record

```yaml
decision_date:
selected_segment:
buyer_role:
selected_wedge:
score:
hard_gates:
  customer_evidence:
  buyer_and_budget:
  data_rights_precheck:
  quality_measurability:
  regulatory_precheck:
commitment_level:
baseline_summary:
current_alternatives:
right_to_win:
first_20_accounts:
8_week_mvs:
kill_criteria:
independent_challenge:
decision: SELECT | NARROW | PIVOT | PAUSE | STOP
approvers:
```
