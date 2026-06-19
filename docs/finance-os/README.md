# Finance OS Research-to-Product Program

> 상태: **G0 실행 시작**  
> 기준일: 2026-06-19  
> 원칙: Research-First · Wedge-First · Evidence-First · Control-by-Design · Platform-Extraction-Last

## 목적

Finance OS는 처음부터 범용 금융 플랫폼으로 개발하지 않는다. 먼저 고객이 반복적으로 수행하고 비용을 지불할 금융 업무 하나를 검증한다. 해당 업무의 데이터 권리, 품질 기준, 통제, 예외, 규제 경계를 확인하고 후보 기술을 동일 시나리오로 비교한 뒤에만 Adopt / Buy / Build를 결정한다.

이 디렉터리는 Finance OS 연구와 제품화 의사결정의 단일 진입점이다. 현재 저장소의 기존 코드나 외부 오픈소스는 모두 **후보 또는 참고자료**이며, 커널로 확정되지 않았다.

## 90일 목표

한 개의 고객 세그먼트와 한 개의 반복 업무를 선택하고 다음 Gate를 통과한다.

| Gate | 결정 | 목표 시점 | 핵심 산출물 |
|---|---|---:|---|
| G0 | Research Charter 승인 | Week 1 | 범위, 역할, 증거 규칙, WIP, 예산 |
| G1 | Segment + Wedge | Week 4 | 고객·구매자·업무 증거, 기준선, 선택/중단 결정 |
| G2 | Feasibility | Week 6 | 데이터 권리, 규제 경계, Data Contract, Golden Snapshot |
| G3 | Shortlist | Week 8 | OSS·상용·자체개발 후보 2–3개 |
| G4 | Adopt / Buy / Build | Week 12 | ADR, MVS 계획, 예산·역량 승인 |

G5 Minimum Vertical Slice는 Month 4–5, G6 Shadow Pilot은 Month 5–6의 목표다.

## 현재 Wedge 가설

| ID | Wedge | 구매자 가설 | 측정 가능한 기준선 |
|---|---|---|---|
| W1 | 공시 변경 인텔리전스 | 애널리스트·PM | 업데이트 시간, 누락률, 검토시간 |
| W2 | 투자위원회 Evidence Pack | PM·리스크·IC | 작성·검토시간, 발견 오류 |
| W3 | 현금·포지션 대사 | 패밀리오피스·운용지원 | Break 발견시간, 미해결 건수 |
| W4 | GL 대사·월말 마감 | 펀드 관리자·재무팀 | 마감시간, 재작업, 오류율 |
| W5 | 모의주문 정책·감사 | 소형 운용팀·개발자 | 차단 정확도, 중복률, 감사완결성 |
| W6 | 정기 투자·운영 보고 | 운용사·패밀리오피스 | 작성시간, 수정횟수 |

Public Equity는 테스트 데이터가 풍부한 Reference Sandbox일 뿐 고객 Wedge로 자동 선정하지 않는다.

## 비협상 원칙

1. README, 데모, GitHub 스타, 에이전트 수만으로 후보를 채택하지 않는다.
2. 데이터 접근 가능성과 상업 이용·저장·표시·재배포 권리를 분리한다.
3. AI는 분석과 초안을 보조할 수 있으나 정책·승인·주문·원장·대사는 결정론적 계층과 인간 권한을 가진다.
4. 입력, 원천, 기준시점, 모델·프롬프트·도구 버전, 검토·승인을 재현할 수 있어야 한다.
5. 데이터 권리, 보안, 재현성, 운영성, 교체성 Hard Gate 중 하나라도 실패하면 가중점수를 계산하지 않는다.
6. 최소 두 개의 검증된 워크플로에서 공통 Capability가 반복되기 전에는 Finance OS Kernel을 추출하지 않는다.
7. 실거래는 별도 법률·운영·보안 Gate를 통과하기 전까지 범위 밖이다.

## 문서 구조

```text
docs/finance-os/
├── README.md
├── research-charter.md
├── wedge-evaluation.md
├── candidate-landscape.md
├── execution-plan.md
├── registers/
│   ├── assumptions.md
│   ├── decisions.md
│   └── evidence.md
└── templates/
    ├── interview-evidence.md
    ├── candidate-card.md
    └── data-contract.md
```

## 증거 수준

| Level | 의미 | 예시 |
|---|---|---|
| E0 | 이름·주장만 존재 | 링크, 구두 아이디어 |
| E1 | 공식 문서·인터뷰 주장 | README, 문서, 인터뷰 메모 |
| E2 | 직접 확인·실행 | 실제 산출물, API Probe, 설치 결과 |
| E3 | 측정된 비교 | 사전등록 Bake-off, Golden Dataset |
| E4 | 제한된 실제 운영 | Shadow Pilot, Design Partner 검증 |
| E5 | 반복 가능한 운영 증거 | 유료 운영, 장기 품질·복원력 지표 |

증거 수준과 결정 상태는 분리한다. 예를 들어 E3 후보도 Hard Gate 실패 시 REJECT할 수 있다.

## 결정 상태

```text
DISCOVERED → RESEARCHING → PROBED → SHORTLISTED
→ ADOPT | ADAPT | FORK | BUY | BUILD | REFERENCE | DEFER | REJECT
```

## 즉시 실행 순서

1. `research-charter.md`에서 G0 범위와 역할을 확정한다.
2. 사용자·구매자·승인자를 분리해 인터뷰 대상을 모집한다.
3. 최근 실제 사건과 산출물을 수집하고 TACDERT 형식으로 업무를 재구성한다.
4. 활성 세그먼트와 Wedge를 최대 2개로 줄인다.
5. 공식 데이터 2개를 E2 수준으로 Probe한다.
6. G1 Pre-read에서 SELECT / NARROW / PIVOT / PAUSE / STOP을 결정한다.

## 현재 보류된 결정

- 첫 고객과 구매자
- 첫 유료 워크플로
- 첫 관할과 배포형태
- 실거래 지원 여부
- 핵심 데이터 공급자
- 원장·워크플로·에이전트·UI 기술
- `tradingcodex` 및 외부 프로젝트 채택 여부

이 항목은 증거 없이 기본값을 두지 않는다.
