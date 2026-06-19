# Evidence Register

증거는 가설·결정과 분리해 보존한다. 민감한 고객 자료는 이 공개 저장소에 원문을 올리지 않고 승인된 보관 위치와 해시·메타데이터만 기록한다.

| ID | 수집일 | 유형 | 설명 | Level | 관련 가설·Wedge | 보관 위치 | 사용 권리 | Reviewer | 상태 |
|---|---|---|---|---:|---|---|---|---|---|
| EVD-001 | 2026-06-19 | GitHub/공식문서 | 현재 `tradingcodex` 제품 방향·역할·통제 구조 | E1 | A-007 | Repository docs | 공개 라이선스 확인 필요 | TBD | ACTIVE |
| EVD-002 | 2026-06-19 | GitHub/공식문서 | DartLab DART·EDGAR 정규화·분석 기능 | E1 | W1, A-004 | External repository | Apache-2.0 및 데이터 권리 별도 | TBD | ACTIVE |
| EVD-003 | 2026-06-19 | GitHub/공식문서 | KIS Open Trading API 상품·주문·모의환경 샘플 | E1 | W5 | External repository | 샘플 조건·API 약관 별도 | TBD | ACTIVE |
| EVD-004 | 2026-06-19 | GitHub/공식문서 | Anthropic Financial Services 업무 Agent·Human Sign-off 경계 | E1 | W1–W4 | External repository | 라이선스 확인 필요 | TBD | ACTIVE |
| EVD-005 | 2026-06-19 | 대화·문서 | Finance OS Research-to-Product Roadmap v1.1 | E1 | Program | Project artifact | 내부 연구문서 | Program Owner | ACTIVE |

## Evidence Level

```text
E0  이름·주장만 존재
E1  공식 문서·인터뷰 주장
E2  실제 산출물·직접 API Probe·설치 확인
E3  사전등록 비교·Golden Dataset·측정 결과
E4  Shadow Pilot·Design Partner 운영
E5  유료·반복 운영과 장기 품질·복원력
```

## Evidence Status

```text
ACTIVE       현재 결정에 사용 가능
STALE        기준일·버전이 오래됨
CONFLICTING  다른 증거와 충돌
REVOKED      권리·동의·정확성 문제로 사용 금지
ARCHIVED     현재 범위 밖이나 보존
```

## Evidence Record 템플릿

```yaml
id:
collected_at:
evidence_type: interview | artifact | log | api_probe | contract | official_doc | experiment | pilot
source_or_owner:
description:
evidence_level:
related_assumptions:
related_wedges:
related_candidate:
as_of:
version:
collection_method:
raw_location:
content_hash:
sensitivity: public | internal | confidential | restricted
consent_or_permission:
permitted_use:
retention:
quality_notes:
conflicts:
reviewer:
status: ACTIVE
```

## 최소 품질 규칙

- 인터뷰 메모에는 응답자 역할, 조직 유형, 날짜, 최근 실제 사건이 포함되어야 한다.
- 업무 산출물에는 생성시점, 입력 원천, 작성·검토·승인 역할이 포함되어야 한다.
- API Probe에는 요청·응답 Schema, 시각, 버전, Rate Limit, 오류, 원천 Snapshot Hash를 남긴다.
- 실험에는 사전등록 기준, 환경, 코드·모델·Prompt 버전, Raw Result, 비용을 남긴다.
- 계약·약관 증거에는 URL 또는 문서 버전, 확인일, 적용 범위와 검토자를 남긴다.
- 고객·계좌·거래·PII 원문을 공개 저장소에 저장하지 않는다.
