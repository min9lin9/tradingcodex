# Candidate Assessment Card

## 1. 기본 정보

```yaml
candidate_id:
name:
url:
type: data | disclosure | research_agent | broker_execution | workflow_policy | model_quant | ledger_reconciliation | reporting_ux | standard | commercial_vendor
capability:
official_or_unofficial:
owner_or_vendor:
reviewed_at:
reviewers:
access_status: DISCOVERED | ACCESSIBLE | INSTALLED | PROBED | BLOCKED
```

## 2. 사용 가설

```yaml
selected_wedge:
role_in_workflow:
inputs:
outputs:
state_owned:
controls_supported:
exceptions_supported:
what_it_does_not_own:
replacement_boundary:
```

후보가 전체 Finance OS를 제공한다고 가정하지 않는다. 선택 Wedge의 특정 Capability만 평가한다.

## 3. 증거와 결정 상태

```yaml
evidence_level: E0 | E1 | E2 | E3 | E4 | E5
decision_status: DISCOVERED | RESEARCHING | PROBED | SHORTLISTED | ADOPT | ADAPT | FORK | BUY | BUILD | REFERENCE | DEFER | REJECT
next_action:
evidence_links:
```

## 4. Knockout Gate

| Gate | PASS/FAIL/BLOCKED | 근거 | 치명적 Gap | 보완 가능 여부 |
|---|---|---|---|---|
| K1 P0 업무 적합성 |  |  |  |  |
| K2 코드·데이터 권리 |  |  |  |  |
| K3 보안·권한·감사 |  |  |  |  |
| K4 재현성 |  |  |  |  |
| K5 운영성·안전한 실패 |  |  |  |  |
| K6 교체성 |  |  |  |  |
| K7 독립 검증 가능성 |  |  |  |  |

하나라도 FAIL 또는 해결되지 않은 BLOCKED이면 가중점수를 계산하지 않는다.

## 5. 라이선스·데이터 권리

```yaml
code_license:
license_version:
notice_requirements:
patent_terms:
copyleft_trigger:
transitive_license_review:
data_source:
data_terms_url:
data_terms_version:
internal_storage:
derived_data:
model_input:
customer_display:
redistribution:
retention_after_termination:
audit_retention:
legal_review_status:
```

## 6. 보안·배포

```yaml
deployment_model:
network_egress:
telemetry:
secret_handling:
authentication:
authorization:
role_scoping:
audit_log:
encryption:
data_residency:
subprocessors:
sbom:
signed_releases:
security_policy:
vulnerability_history:
```

## 7. 유지보수·공급망

```yaml
latest_release:
release_frequency:
maintainer_count:
bus_factor:
issue_response:
api_stability:
migration_policy:
deprecation_policy:
ci_status:
test_coverage:
dependency_pinning:
reproducible_build:
source_binary_gap:
```

## 8. 운영·복원력

```yaml
rate_limits:
latency:
throughput:
retry_semantics:
idempotency:
revision_handling:
outage_behavior:
fallback:
degraded_mode:
backup_restore:
replay:
observability:
support_channel:
sla:
```

## 9. Hard Gate 통과 후 점수

| 항목 | 가중치 | 점수 1–5 | 가중 결과 | 증거 |
|---|---:|---:|---:|---|
| P0 업무 적합성 | 25 |  |  |  |
| 정확성·재현성·시점성 | 20 |  |  |  |
| 통제·권한·감사 | 15 |  |  |  |
| 통합성과 교체 가능성 | 10 |  |  |  |
| 유지보수·개발성 | 10 |  |  |  |
| 보안·복원력 | 10 |  |  |  |
| 3년 TCO | 10 |  |  |  |
| **합계** | **100** |  |  |  |

## 10. 3년 TCO

```yaml
initial_integration:
license_subscription:
data_cost:
infrastructure:
model_cost:
security_legal_audit:
operations_oncall:
support:
upgrade_or_fork_maintenance:
training_documentation:
expected_failure_cost:
exit_and_export:
assumptions:
sensitivity_cases:
```

## 11. Exit Plan

- 데이터 Export 형식과 소요시간:
- 최소 Adapter 계약:
- 대체 후보:
- Schema·Prompt·Model·Source 버전 보존:
- 계약 종료 후 Retention·삭제:
- 서비스 중단 Degraded Mode:
- 내부에 유지할 문서·테스트·지식:
- 포크 또는 Build 전환 Trigger:

## 12. Bake-off

```yaml
suite:
pre_registered_metrics:
golden_dataset:
holdout:
baselines:
  human:
  deterministic:
  single_agent:
  external_candidate:
environment:
version:
raw_results:
cost:
reviewer_blinding:
failures:
```

## 13. 최종 권고

```yaml
recommended_decision: ADOPT | ADAPT | FORK | BUY | BUILD | REFERENCE | DEFER | REJECT
scope:
conditions:
known_gaps:
residual_risks:
independent_challenge:
approvers:
review_trigger:
```
