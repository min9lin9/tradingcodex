# Decision Register

모든 결정은 날짜, Gate, 대안, 근거, 반대 의견, 재검토 Trigger를 기록한다. 미결정 상태를 숨기기 위해 임시 기본값을 영구 구조로 만들지 않는다.

| ID | 날짜 | Gate | 결정 | 상태 | 핵심 근거 | 반대·불확실성 | 재검토 Trigger | Owner |
|---|---|---|---|---|---|---|---|---|
| D-001 | 2026-06-19 | G0 | Research-First와 Wedge-First를 최상위 원칙으로 채택 | ACCEPTED | 업무·데이터·통제 확인 전 기술 선정 위험 | 조사기간 장기화 가능 | 고객 증거가 즉시 특정 제품을 요구 | Program Owner |
| D-002 | 2026-06-19 | G0 | 모든 OSS·데이터·모델을 미선정 후보로 유지 | ACCEPTED | 현재 증거가 E0–E1 중심 | 기존 코드 재사용 속도 이점 | E3 Bake-off와 K1–K7 통과 | Architecture Lead |
| D-003 | 2026-06-19 | G0 | 90일 목표를 G1–G4 완료로 제한 | ACCEPTED | Production-ready 약속은 증거·일정과 모순 | 시장 진입이 느려질 수 있음 | G1·G2가 조기 통과하고 Design Partner가 C3 도달 | Program Owner |
| D-004 | 2026-06-19 | G0 | 실거래는 초기 범위에서 제외 | ACCEPTED | 규제·손실·보안·운영 표면이 큼 | 실행 연결 없는 가치가 낮을 수 있음 | G6 이후 별도 법률·운영 Gate 승인 | Risk Reviewer |
| D-005 | 2026-06-19 | G0 | Public Equity는 Reference Sandbox이지 자동 Wedge가 아님 | ACCEPTED | 테스트 데이터 풍부함과 구매 문제 강도는 별개 | 기존 자산과의 정합성이 높음 | G1 고객 증거가 Public Equity Wedge를 SELECT | Product Research Lead |
| D-006 | 2026-06-19 | G0 | Finance OS Kernel 추출은 최소 2개 검증 워크플로 이후 | ACCEPTED | 조기 공통화·플랫폼 과설계 방지 | 중복 개발 가능 | 두 번째 G6 통과 후 공통 Capability 분석 | Architecture Lead |

## 상태

```text
PROPOSED
ACCEPTED
REJECTED
SUPERSEDED
DEFERRED
EXPIRED
```

## Decision Record 템플릿

```yaml
id:
date:
gate:
title:
context:
options:
  - option:
    benefits:
    costs:
    risks:
decision:
status: PROPOSED | ACCEPTED | REJECTED | SUPERSEDED | DEFERRED | EXPIRED
evidence_links:
assumptions:
independent_challenge:
consequences:
owner:
approvers:
review_trigger:
review_date:
```

## Gate Decision 최소 항목

- 판단할 질문
- 통과·중단 기준
- 사용한 증거와 증거 수준
- 계산식과 입력값
- 선택하지 않은 대안
- 치명적 불확실성
- 책임자와 승인자
- 다음 Gate 전 필수 행동
- 재검토 Trigger
