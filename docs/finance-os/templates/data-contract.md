# Data Contract Template

## 1. 데이터셋 식별

```yaml
data_contract_id:
name:
provider:
dataset_or_endpoint:
source_tier: 1 | 2 | 3 | 4
official_or_unofficial:
owner:
reviewers:
created_at:
last_reviewed_at:
contract_version:
```

### Source Tier

```text
Tier 1  규제기관·거래소·중앙은행·브로커 공식 API
Tier 2  계약된 상용 데이터 공급자
Tier 3  검증된 오픈소스 정규화·접속 계층
Tier 4  비공식 API·스크래핑·커뮤니티 데이터
```

Tier 3·4는 운영상 사실 원천으로 자동 승격하지 않는다.

## 2. 업무 사용 범위

```yaml
selected_wedge:
capabilities:
consumers:
criticality: P0 | P1 | P2
permitted_purpose:
tenant_or_customer_scope:
prohibited_uses:
```

## 3. Schema와 의미

```yaml
format:
schema_location:
primary_keys:
identifiers:
units:
currency:
timezone:
frequency:
expected_volume:
required_fields:
nullable_fields:
enumerations:
```

| 필드 | 자료형 | 의미 | 단위·통화 | 필수 | 검증 규칙 | 원천 필드 |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## 4. 시간·버전·계보

각 레코드 또는 Snapshot에 다음 메타데이터를 보존한다.

```yaml
provider:
dataset_or_endpoint:
source_version:
instrument_id:
issuer_id:
event_time:
knowledge_time:
ingested_at:
effective_from:
effective_to:
vintage:
revision:
source_uri:
content_hash:
quality_status:
license_profile:
terms_version:
terms_evidence_hash:
permitted_purpose:
entitlement_id:
retention_policy:
redistribution_policy:
```

`event_time`, `knowledge_time`, `ingested_at`을 분리해 미래정보 누출을 방지한다.

## 5. 발표·수정·삭제

```yaml
publication_schedule:
expected_latency:
revision_policy:
restatement_policy:
deletion_policy:
backfill_policy:
corporate_action_policy:
symbol_change_policy:
identifier_mapping:
```

## 6. Data Quality SLO

| Dimension | 목표 | 측정식 | Alert | Block 조건 | Owner |
|---|---:|---|---|---|---|
| Completeness |  |  |  |  |  |
| Accuracy |  |  |  |  |  |
| Timeliness |  |  |  |  |  |
| Consistency |  |  |  |  |  |
| Uniqueness |  |  |  |  |  |
| Lineage |  |  |  |  |  |
| Point-in-time |  |  |  |  |  |

초기 원칙:

- Critical P0 필드: 100% 요구 여부를 업무별로 판단
- Material Numeric Error: 0
- P0 출력 Lineage: 100%
- 중복 핵심 이벤트: 0
- 자금·원장·규제 상태는 평균이 아닌 Zero-Tolerance Control

## 7. 검증 규칙

```yaml
schema_validation:
range_checks:
cross_field_checks:
source_reconciliation:
duplicate_detection:
revision_detection:
outlier_policy:
manual_review_trigger:
quarantine_policy:
```

## 8. 권리 Matrix

| 권리 | 허용/금지/불명확 | 범위 | 증적 URL·조항 | 확인일 | Reviewer |
|---|---|---|---|---|---|
| Access |  |  |  |  |  |
| Internal Storage |  |  |  |  |  |
| Derived Data |  |  |  |  |  |
| Model Input |  |  |  |  |  |
| Customer Display |  |  |  |  |  |
| Redistribution |  |  |  |  |  |
| Retention |  |  |  |  |  |
| Audit Submission |  |  |  |  |  |

불명확한 권리는 허용으로 추정하지 않고 `BLOCKED`로 둔다.

## 9. 접근·Entitlement

```yaml
authentication:
credential_owner:
entitlement_id:
allowed_users_or_services:
least_privilege:
key_rotation:
rate_limit:
quota:
cost_model:
contract_expiry:
```

## 10. 보안·Privacy

```yaml
data_classification:
pii:
account_or_transaction_data:
encryption_in_transit:
encryption_at_rest:
data_residency:
subprocessors:
model_provider_egress:
logging_and_masking:
retention:
deletion:
legal_hold:
```

## 11. 장애·Fallback

```yaml
provider_sla:
observability:
retry_policy:
backoff:
circuit_breaker:
fallback_source:
manual_fallback:
degraded_mode:
maximum_staleness:
block_conditions:
incident_owner:
```

## 12. Test Data와 Golden Snapshot

```yaml
test_data_type: public | synthetic | anonymized | production_approved
golden_snapshot_location:
snapshot_hash:
expected_results:
generation_method:
rights:
refresh_policy:
holdout_policy:
```

실계좌·실주문 자격증명은 개발·CI·데모에 두지 않는다. 로그에는 원문 전체 대신 필요한 식별자·해시·마스킹 정보를 남긴다.

## 13. Readiness 판정

```text
PRODUCTION      권리·품질·장애·운영 검증 완료
PILOT           제한된 사용자·범위에서 사용 가능
RESEARCH_ONLY   분석·프로토타입만 가능
SCREEN_GRADE    후보 탐색에만 사용
BLOCKED         권리·품질·접근 문제로 사용 금지
```

```yaml
readiness_label:
open_gaps:
mitigations:
approvers:
next_review:
```
