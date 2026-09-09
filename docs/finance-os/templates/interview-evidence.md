# Interview Evidence Template

> 목적: 기능 선호가 아니라 최근 실제 금융 업무 사건, 산출물, 통제, 예외, 구매 경로를 재구성한다.

## 메타데이터

```yaml
interview_id:
date:
interviewer:
organization_type:
respondent_role:
respondent_relationship: user | reviewer | approver | buyer | risk | it | legal
wedge_hypothesis:
consent:
recording_allowed:
confidentiality:
```

## 1. 최근 실제 사건

- 마지막으로 이 업무를 수행한 정확한 날짜:
- 업무를 시작시킨 Trigger:
- 마감·시장시간·결제일·보고 Cut-off:
- 결과가 사용된 의사결정 또는 후속 단계:

## 2. 현재 Workflow

```yaml
actor:
reviewer:
approver:
inputs:
systems_and_files:
steps:
outputs:
state_changes:
controls:
evidence_retained:
retention:
```

### 단계별 재구성

| 순서 | 사람/시스템 | 입력 | 행동 | 출력 | 소요시간 | 오류·재작업 | 통제 |
|---:|---|---|---|---|---:|---|---|
| 1 |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |

## 3. 실패와 예외

- 최근 실패·누락·지연 사례:
- 발견한 사람과 발견 시점:
- Root Cause:
- 해결까지 걸린 시간:
- 금전·규제·평판 영향:
- 같은 문제가 재발한 횟수:
- 현재 예방·탐지 통제:
- 시스템이 절대 자동화해서는 안 되는 행동:

## 4. 기준선

```yaml
frequency:
case_volume:
elapsed_time:
active_work_time:
reviewer_time:
number_of_people:
revision_rounds:
error_rate:
late_rate:
unresolved_exceptions:
current_tool_cost:
external_service_cost:
expected_loss_or_risk:
```

## 5. 산출물 증거

| Artifact | 실제 샘플 제공 | 익명화 가능 | Owner | 생성주기 | 보존기간 | 승인 필요 |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

공개 저장소에는 원문을 올리지 않는다. 승인된 보관 위치와 Hash만 Evidence Register에 남긴다.

## 6. 현재 대안

- Excel·이메일·메신저:
- 내부 스크립트·데이터팀:
- 기존 Terminal·ERP·OMS·Reconciliation 제품:
- BPO·컨설팅·관리회사:
- 범용 AI 도구:
- 아무것도 하지 않음:
- 교체하지 못하는 이유:

## 7. 구매와 조달

```yaml
user:
champion:
buyer:
budget_owner:
security_reviewer:
it_reviewer:
legal_or_compliance_reviewer:
current_budget:
price_unit_preference:
procurement_lead_time:
required_certifications:
pilot_path:
commitment_level: C0 | C1 | C2 | C3 | C4
```

## 8. 반증 질문

- 이 문제는 실제로 얼마나 자주 발생하는가?
- 기존 도구의 설정 변경이나 교육만으로 해결 가능한가?
- 이 업무를 자동화하지 않는 것이 더 안전하거나 저렴한가?
- 데이터·보안·조달 이유로 새 제품을 도입할 수 없는가?
- 자동화로 절약되는 시간보다 검토시간이 더 커질 수 있는가?
- 이 제품이 없어도 예산이 다른 우선순위로 이동하는가?

## 9. 인터뷰 후 평가

```yaml
new_evidence_level:
strongest_supporting_evidence:
strongest_counter_evidence:
baseline_quality:
buyer_evidence:
data_access_evidence:
regulatory_or_security_blockers:
follow_up_artifact:
next_interview_role:
assumptions_updated:
confidence_change:
```
