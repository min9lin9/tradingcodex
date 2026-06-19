# Candidate Landscape

## 원칙

후보는 이름이나 인기순으로 비교하지 않는다. 선택된 Wedge가 요구하는 Capability별로 분류하고 동일 유형 안에서만 비교한다. 오픈소스만 조사하면 Build 편향이 생기므로 상용 Buy 후보와 최소 자체구현 Baseline을 반드시 포함한다.

현재 모든 항목은 조사 후보이며, `UNDECIDED` 또는 `REFERENCE` 상태다.

## 후보 유형

```text
Data / Disclosure / Market
Research / Agent
Broker / Execution
Workflow / Policy / Audit
Model / Quant / Backtest
Ledger / Reconciliation / Accounting
Reporting / Terminal / UX
Standards / Protocol
Commercial Vendor / Buy Alternative
```

## 필수 후보 필드

```yaml
candidate_id:
name:
url:
type:
capability:
access_status:
evidence_level:
decision_status:
next_action:
official_or_unofficial:
license_and_terms:
data_dependencies:
data_rights:
deployment_and_egress:
security_posture:
maintenance_and_bus_factor:
benchmark_applicability:
tco_range:
exit_path:
reviewed_at:
```

## 데이터·공시·시장

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| SEC EDGAR | 미국 공식 제출·XBRL 원천 | E1 | UNDECIDED | API·빈티지·Rate Limit Probe |
| OpenDART | 한국 공시·재무 공식 원천 | E1 | UNDECIDED | 정정공시·XBRL·원문 Probe |
| KRX OPEN API | 한국 종목·거래 공식 원천 | E1 | UNDECIDED | 범위·권리·지연 Probe |
| FRED/ALFRED | 매크로·빈티지 공식 원천 | E1 | UNDECIDED | Point-in-time Probe |
| ECOS | 한국 매크로 공식 원천 | E1 | UNDECIDED | 수정정책·식별자 Probe |
| DartLab | DART+EDGAR 정규화·분석 | E1 | UNDECIDED | 공시 수평화 정확도 Bake-off |
| Korea Stock MCP | DART/KRX MCP 표면 | E1 | UNDECIDED | 대용량 공시·Schema Probe |
| yfinance | 프로토타입 시장 데이터 | E1 | RESEARCH_ONLY | 권리상 운영 사용 제외 검토 |
| ETFdb API wrapper | ETF 데이터 비공식 래퍼 | E1 | UNDECIDED | 약관·안정성 조사 |
| Trading Economics | 전망·정보구조 | E1 | REFERENCE | UX 비교만 수행 |
| Moabbs 미국지수 | 시장 UX·데이터 후보 | E0 | UNDECIDED | 접근·출처 확인 |

## 리서치·에이전트

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| PRISM-INSIGHT | 한국·미국 분석·리포트·거래 앱 | E1 | UNDECIDED | 출처·평가·통제·AGPL 검토 |
| TradingAgents | 역할 기반 멀티에이전트 연구 | E1 | UNDECIDED | 단일 Agent·결정론 Baseline 비교 |
| Dexter | 계획·도구·자기검증형 Agent | E1 | UNDECIDED | Eval·Trace·Failure Mode 검증 |
| AI Hedge Fund | 투자자 페르소나 PoC | E1 | REFERENCE | 역할 중복·재현성 분석 |
| Daily Stock Analysis | 다시장 분석·알림 앱 | E1 | UNDECIDED | 데이터 우선순위·Fallback 검토 |
| Anthropic Financial Services | 금융 업무 Skill·Agent 참조 | E1 | UNDECIDED | 업무 Taxonomy·Human Sign-off 연구 |
| Vibe Investing — fivetaku | 투자 Skill 라이브러리 | E1 | UNDECIDED | 계보·품질·라이선스 검토 |
| Vibe Investing — monarchjuno | 투자 Skill 라이브러리 | E1 | UNDECIDED | fivetaku와 Diff·원본성 확인 |

## 브로커·실행

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| KIS Open Trading API | 공식 시세·계좌·주문 샘플 | E1 | UNDECIDED | 모의환경 조회 전용 Probe |
| KIS AI Extensions | 전략·백테스트·주문·보안 Hook | E1 | UNDECIDED | 승인·비밀·로그 우회 테스트 |
| Korea Investment MCP | KIS API 검색 카탈로그 | E1 | REFERENCE | 실행기와 분리 유지 |
| LS OpenAPI Samples | LS증권 API 샘플 | E1 | UNDECIDED | 인증·시세·계좌·모의 Probe |

실계좌·실주문 자격증명은 연구, CI, 데모 환경에서 사용하지 않는다.

## 모델·정량·백테스트

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| Kronos | OHLCV 시계열 Foundation Model | E1 | UNDECIDED | Holdout·누출·비용 평가 |
| Qlib | 정량 연구·ML Pipeline | E1 | UNDECIDED | 데이터·Experiment Tracking 비교 |
| LEAN | 백테스트·체결 시뮬레이션 | E1 | UNDECIDED | Corporate Action·Fee·Slippage 검증 |

## Workflow·Policy·Audit

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| 현재 `tradingcodex` | 정책·승인·주문·감사 Harness | E1 | UNDECIDED | Wedge 선택 후 K1–K7 평가 |
| AI Team OS | 업무벽·지속실행·실패학습 | E1 | REFERENCE | 범용 오케스트레이션 패턴만 연구 |
| `korean-law-mcp` | 법령 근거·시점·인용 검증 | E1 | UNDECIDED | 금융 규정 Coverage 검증 |

## 보고·터미널·제품 UX

| 후보 | 역할 가설 | 증거 | 결정 | 다음 행동 |
|---|---|---:|---|---|
| Fincept Terminal | 금융 Terminal 정보구조 | E1 | REFERENCE | UX·통합 패턴 분석 |
| Typst Korean Report | 한국어 PDF 렌더링·검증 | E1 | UNDECIDED | 보고서 Suite F에서 비교 |
| Afterule | 기업 리포트 UX | E0/E1 | REFERENCE | 산출물 구조 분석 |
| FRoGie | 상대평가 지표 UX | E0/E1 | REFERENCE | 지표 설명·근거 표현 분석 |
| JangsTrading | 수급 분석 UX | E0/E1 | REFERENCE | 국내 투자자 Workflow 분석 |
| 한경 EPIC AI | 금융 AI 제품 | E0 | NEEDS_URL | 공식 URL 확인 |

## 미충족 Landscape

현재 후보는 주식 리서치와 Agent에 편중되어 있다. W3 또는 W4를 공정하게 평가하려면 다음 Longlist를 새로 작성해야 한다.

- Position / Cash / Transaction Reconciliation
- General Ledger / Fund Accounting / NAV
- Corporate Actions와 Security Master
- Workflow / Case Management / Evidence Vault
- Data Entitlement / Lineage / Quality
- FIX Engine / Post-trade Messaging
- Portfolio Accounting / Performance Attribution

## 상용 Buy 비교군

G3에서는 최소 다음 유형의 상용 후보를 포함한다.

- 공시·재무·시장·뉴스 데이터 공급자
- Portfolio / OMS / Risk / Reconciliation 솔루션
- Fund Administration / GL Close 도구
- 금융 Research Terminal
- Identity, Secrets, Audit, Observability 서비스
- Model Gateway와 평가·모니터링 도구

## Knockout Gate

| Gate | 질문 |
|---|---|
| K1 업무 적합성 | 선택된 P0 업무의 입력·산출물·예외·통제를 지원하는가? |
| K2 코드·데이터 권리 | 내부·상업 사용, 수정, 배포, 데이터 이용 조건을 충족하는가? |
| K3 보안·권한 | 비밀정보·권한·실행을 분리하고 감사할 수 있는가? |
| K4 재현성 | 입력·버전·결과를 재생하고 차이를 설명할 수 있는가? |
| K5 운영성 | 장애·지연·수정·중복 요청에서 안전하게 실패하는가? |
| K6 교체성 | 중단·가격·라이선스 변경 시 이관 가능한가? |
| K7 검증 가능성 | 내부 사용 맥락에서 독립 검증할 수 있는가? |

하나라도 실패하면 점수를 계산하지 않고 `DEFER` 또는 `REJECT`한다.

## Hard Gate 통과 후 점수

| 항목 | 가중치 |
|---|---:|
| P0 업무 적합성 | 25 |
| 정확성·재현성·시점성 | 20 |
| 통제·권한·감사 | 15 |
| 통합성과 교체 가능성 | 10 |
| 유지보수·개발성 | 10 |
| 보안·복원력 | 10 |
| 3년 총소유비용 | 10 |

## 결정 유형

```text
ADOPT     핵심 수정 없이 운영 가능
ADAPT     안정된 외부 코어에 얇은 Adapter·Policy Layer
FORK      장기 유지역량과 차별화가 충분
BUY       SLA·권리·지원·시간이 Build보다 우수
BUILD     P0 상태·통제 의미가 차별화의 핵심
REFERENCE 모델·용어·테스트·UX만 참고
DEFER     현재 증거·범위 부족
REJECT    Hard Gate 실패 또는 경제성 없음
```

모든 Adopt·Buy 결정은 데이터 Export, 대체 공급자, Schema·버전 보존, Degraded Mode, 계약 종료 후 Retention을 포함하는 Exit Plan을 가져야 한다.
