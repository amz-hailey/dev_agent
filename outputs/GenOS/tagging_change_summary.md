# Tagging Change Summary — GenOS v2

**작업일**: 2026-02-08
**근거 Contract**: `outputs/components_seed_contract.json`
**대상 속성**: `data-intent` · `data-variant` · `data-size` · `data-state`
**대상 컴포넌트**: badge / tab / alert / card (stat · modal 제외)

---

## Contract 정의 값

| Component | intent | variant | size | state |
|-----------|--------|---------|------|-------|
| **badge** | info, success, warning, danger, neutral, status | solid, soft | xs, sm | default |
| **tab** | nav, filter | pill, segment | sm, md | default |
| **alert** | info, success, warning, danger | soft, outlined | sm, md | default |
| **card** | container, action, summary | default, outlined | sm, md, lg | default |

> `state_policy: no-hover-focus` — hover/focus 상태는 data-state로 강제하지 않음

---

## PG-01_login.html — 5개 요소

| # | Line | data-component | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|----------------|-------------|--------------|-----------|------------|------|
| 1 | 143 | alert | danger | soft | md | default | 계정 잠금 경고 배너 (bg-red-50) |
| 2 | 310 | tab | nav | segment | md | default | MFA 인증 방법 선택 (grid-cols-2) |
| 3 | 327 | alert | danger | soft | sm | default | MFA 인증 오류 메시지 (bg-red-50) |
| 4 | 367 | alert | warning | soft | sm | default | MFA 잠금 경고 (bg-amber-50) |
| 5 | 404 | card | container | default | md | default | 인증 완료 성공 카드 |

---

## PG-02_dashboard.html — 13개 요소

### badge (4)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 1 | 50 | danger | soft | xs | default | 사이드바 알림 카운트 (bg-red-100) |
| 2 | 125 | success | soft | sm | default | 실시간 Live 인디케이터 (bg-emerald-50) |
| 3 | 221 | status | soft | xs | default | 알림 심각도 뱃지 (동적 class) |
| 4 | 228 | status | soft | xs | default | 알림 상태 뱃지 (new/acknowledged/resolved) |

### card (7)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 5 | 173 | container | outlined | lg | default | 탐지 추이 차트 래퍼 (col-span-3) |
| 6 | 194 | container | outlined | lg | default | 실시간 알림 타임라인 (col-span-2) |
| 7 | 255 | container | outlined | lg | default | 빠른 실행 섹션 래퍼 |
| 8 | 258 | action | outlined | md | default | 에이전트 배포 바로가기 |
| 9 | 268 | action | outlined | md | default | 리포트 생성 바로가기 |
| 10 | 278 | action | outlined | md | default | 데이터 소스 연결 바로가기 |
| 11 | 288 | action | outlined | md | default | 실시간 모니터링 바로가기 |

### tab (1)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 12 | 179 | filter | pill | sm | default | 차트 기간 선택 (7일/14일/30일/90일) |

### alert (1)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 13 | 212 | info | soft | sm | default | 알림 타임라인 아이템 (template 반복) |

---

## PG-03_agent_templates.html — 12개 요소

### card (4)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 1 | 88 | container | outlined | md | default | 카테고리/상태/정렬 필터 영역 |
| 2 | 144 | action | outlined | md | default | 에이전트 템플릿 카드 (template 반복) |
| 3 | 202 | container | default | lg | default | 검색 결과 없음 빈 상태 카드 |
| 4 | 280 | container | outlined | md | default | 사전 학습 모델 정보 카드 |

### badge (8)

| # | Line | data-intent | data-variant | data-size | data-state | 설명 |
|---|------|-------------|--------------|-----------|------------|------|
| 5 | 155 | info | soft | xs | default | 카테고리 뱃지 (FDS/AML/DLP/접근이상) |
| 6 | 157 | status | soft | xs | default | 상태 뱃지 (사용 가능/베타/준비 중) |
| 7 | 168 | info | soft | xs | default | 모델 자동연결 뱃지 (bg-purple-50) |
| 8 | 173 | neutral | soft | xs | default | 태그 뱃지 (bg-slate-100) |
| 9 | 244 | info | soft | xs | default | 상세 패널 카테고리 뱃지 |
| 10 | 283 | info | soft | xs | default | 상세 패널 자동연결 뱃지 (bg-purple-100) |
| 11 | 300 | info | soft | xs | default | 필요 데이터 소스 뱃지 (bg-blue-50) |
| 12 | 308 | neutral | soft | xs | default | 지원 DB 뱃지 (bg-slate-100) |

---

## 총 변경 통계

| 페이지 | badge | tab | alert | card | 합계 |
|--------|-------|-----|-------|------|------|
| PG-01_login | 0 | 1 | 3 | 1 | **5** |
| PG-02_dashboard | 4 | 1 | 1 | 7 | **13** |
| PG-03_agent_templates | 8 | 0 | 0 | 4 | **12** |
| **합계** | **12** | **2** | **4** | **12** | **30** |

---

## 미적용 요소 (이번 범위 외)

- `data-component="stat"`: PG-02 (1개), PG-03 (5개) — 대상 외
- `data-component="modal"`: PG-03 (1개) — 대상 외
- PG-04 ~ PG-16: 이번 시범 3페이지에서 제외
