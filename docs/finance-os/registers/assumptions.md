# Assumption Register

가설은 사실로 서술하지 않는다. 각 가설에는 반증 조건, 필요한 증거, 소유자와 검토일을 둔다.

| ID | 가설 | 범주 | 현재 증거 | 반증 조건 | 다음 실험 | Owner | 상태 |
|---|---|---|---|---|---|---|---|
| A-001 | 공시 변경 업데이트는 반복 빈도와 시간 압력이 충분하다 | Customer | E0 | 대상 역할의 최근 사건·비용이 낮음 | 애널리스트·PM 인터뷰와 최근 업데이트 재구성 | TBD | OPEN |
| A-002 | 현금·포지션 대사는 측정 가능한 오류·시간 기준선을 가진다 | Customer | E0 | Break 빈도·Reviewer Time이 낮음 | 운용지원·패밀리오피스 인터뷰 | TBD | OPEN |
| A-003 | GL 대사·월말 마감은 구매자와 예산이 명확하다 | Commercial | E0 | 문제는 강하지만 조달·데이터 접근 불가 | 펀드관리·재무 구매자 인터뷰 | TBD | OPEN |
| A-004 | 공식 공시 API로 P0 데이터를 합법적으로 확보할 수 있다 | Data | E1 | 저장·파생·고객표시 권리가 불명확 | DART·SEC Rights Matrix와 Probe | TBD | OPEN |
| A-005 | AI는 Reviewer Time을 줄이면서 Material Error 0을 유지할 수 있다 | Model | E0 | 오류·누락 또는 검토시간 증가 | Human/Deterministic/Agent Blind Bake-off | TBD | OPEN |
| A-006 | 첫 제품은 실거래 없이도 충분한 지불가치를 만든다 | Product | E0 | 구매자가 실행 연결 없이는 지불하지 않음 | 가격·구매 인터뷰 | TBD | OPEN |
| A-007 | `tradingcodex`의 일부 통제 패턴은 선택 Wedge에 재사용 가능하다 | Technology | E1 | K1–K7 또는 TCO·교체성 실패 | Wedge 선택 후 최소 Spike | TBD | OPEN |
| A-008 | 한국 금융 데이터·업무 특화가 Right-to-win이 될 수 있다 | Strategy | E0 | 고객 접근·차별화·유통이 약함 | 첫 20개 계정과 경쟁대안 조사 | TBD | OPEN |

## 상태

```text
OPEN       검증 전
TESTING    실험·인터뷰 진행
SUPPORTED  현재 증거가 지지하나 변경 가능
REFUTED    반증됨
RETIRED    범위 변경으로 더 이상 유효하지 않음
```

## 새 가설 템플릿

```yaml
id:
statement:
category: Customer | Commercial | Data | Regulatory | Model | Security | Operations | Technology | Strategy
created_at:
owner:
evidence_level:
evidence_links:
why_it_matters:
falsification_condition:
next_test:
decision_deadline:
status: OPEN
```
