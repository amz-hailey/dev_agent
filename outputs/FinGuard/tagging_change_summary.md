# Tagging Change Summary — FinGuard v2

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

## PG-04_deploy_wizard.html — 7개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | card | container | outlined | lg | default | 배포 위자드 메인 래퍼 |
| 2 | card | container | outlined | md | default | 단계별 설정 카드 |
| 3 | card | container | default | md | default | 설정 옵션 카드 |
| 4 | card | container | outlined | md | default | 배포 확인 카드 |
| 5 | alert | warning | soft | sm | default | 배포 주의 경고 (bg-amber-50) |
| 6 | alert | info | soft | sm | default | 안내 메시지 (bg-blue-50) |
| 7 | alert | danger | soft | sm | default | 오류 경고 (bg-red-50) |

---

## PG-05_connector_hub.html — 5개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | card | container | outlined | lg | default | 커넥터 목록 래퍼 |
| 2 | badge | success | soft | xs | default | 활성 상태 뱃지 |
| 3 | badge | status | soft | xs | default | 커넥터 상태 뱃지 (동적) |
| 4 | badge | info | soft | xs | default | 타입 라벨 뱃지 |
| 5 | tab | filter | segment | sm | default | 커넥터 필터 탭 |

---

## PG-06_realtime_monitoring.html — 8개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | badge | danger | soft | xs | default | 사이드바 알림 카운트 |
| 2 | badge | success | soft | sm | default | 실시간 인디케이터 |
| 3 | badge | status | soft | xs | default | 심각도 뱃지 (동적) |
| 4 | card | container | outlined | lg | default | 모니터링 차트 래퍼 |
| 5 | card | container | outlined | lg | default | 이벤트 타임라인 래퍼 |
| 6 | card | container | outlined | md | default | 설정 카드 |
| 7 | card | container | outlined | md | default | 필터 카드 |
| 8 | tab | filter | segment | sm | default | 기간 필터 탭 |

---

## PG-07_alert_management.html — 7개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | tab | nav | segment | md | default | 알림 탭 네비게이션 |
| 2 | card | container | outlined | lg | default | 알림 목록 래퍼 |
| 3 | card | container | outlined | md | default | 알림 상세 패널 |
| 4 | badge | status | soft | xs | default | 심각도 뱃지 (동적) |
| 5 | badge | status | soft | xs | default | 상태 뱃지 (동적) |
| 6 | badge | info | soft | xs | default | 카테고리 뱃지 |
| 7 | badge | neutral | soft | xs | default | 태그 뱃지 |

---

## PG-08_compliance_reports.html — 14개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1-6 | card (6) | container/action | outlined/default | md/lg | default | 리포트 카드, 필터 영역 등 |
| 7-13 | badge (7) | info/status/neutral/success | soft | xs/sm | default | 상태/카테고리/태그 뱃지 |
| 14 | alert | warning | soft | sm | default | 마감 임박 경고 |

---

## PG-09_audit_log.html — 6개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | badge | status | soft | xs | default | 심각도 뱃지 — 테이블 (동적 :class) |
| 2 | badge | status | soft | xs | default | 결과 뱃지 — 테이블 (동적 :class) |
| 3 | card | container | outlined | lg | default | 로그 상세 사이드 패널 |
| 4 | badge | status | soft | xs | default | 심각도 뱃지 — 상세 패널 |
| 5 | badge | status | soft | xs | default | 결과 뱃지 — 상세 패널 |
| 6 | alert | danger | soft | sm | default | 오류 정보 블록 (bg-red-50) |

---

## PG-10_user_permissions.html — 9개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | tab | nav | segment | md | default | 메인 탭 (사용자/역할/매트릭스) |
| 2 | badge | info | soft | xs | default | 사용자 역할 라벨 (violet) |
| 3 | badge | status | soft | xs | default | MFA 상태 뱃지 (동적) |
| 4 | badge | status | soft | xs | default | 사용자 상태 뱃지 (동적) |
| 5 | badge | status | soft | xs | default | 역할 타입 라벨 (동적) |
| 6 | badge | success | soft | sm | default | "저장됨" 확인 뱃지 |
| 7 | badge | neutral | soft | xs | default | 권한 카테고리 라벨 |
| 8 | alert | warning | soft | sm | default | 미저장 변경 경고 |
| 9 | alert | warning | soft | sm | default | MFA 정책 알림 (bg-amber-50) |

---

## PG-11_system_dr.html — 22개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1-13 | badge (13) | status/danger/success/info/neutral | soft | xs/sm | default | DR 테스트 결과/심각도/상태 뱃지 |
| 14-19 | card (6) | container/summary | outlined/default | sm/md/lg | default | 테스트 목록, 상세 패널, 차트 래퍼 등 |
| 20-22 | alert (3) | danger/warning/info | soft | sm | default | 오류/경고/안내 알림 |

---

## PG-12_settings.html — 12개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | tab | nav | segment | md | default | 설정 섹션 탭 |
| 2-9 | card (8) | container | default | sm/md | default | 프로필/MFA/세션/알림/표시 설정 카드 |
| 10 | badge | neutral | solid | xs | default | "정책 적용" 라벨 |
| 11 | badge | success | soft | xs | default | "현재 세션" 뱃지 |
| 12 | alert | warning | soft | sm | default | CRITICAL 면제 알림 (bg-amber-50) |

---

## PG-13_workflow_builder.html — 12개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1 | badge | success | soft | sm | default | "v2.1 배포됨" 뱃지 |
| 2 | badge | info | soft | sm | default | 알림 수신자 태그 뱃지 |
| 3 | badge | status | soft | xs | default | 버전 히스토리 상태 (동적) |
| 4-11 | card (8) | action | outlined | sm | default | 워크플로우 노드 카드 (N1~N8) |
| 12 | card | container | outlined | sm | default | 미니맵 래퍼 |

---

## PG-14_customer_health.html — 16개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1-10 | badge (10) | danger/success/neutral/status | soft | xs/sm | default | 알림카운트/인디케이터/업종/추이 뱃지 |
| 11-12 | tab (2) | filter | segment | sm | default | 업종/기간 필터 탭 |
| 13-16 | card (4) | container | outlined | md/lg | default | 테이블/차트/캘린더/빈상태 래퍼 |

---

## PG-15_ai_pipeline.html — 13개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1-6 | badge (6) | danger/success/neutral/status | soft | xs/sm | default | 알림카운트/활성/버전/모델타입/상태 뱃지 |
| 7-11 | card (5) | container/summary | outlined | md/lg | default | 모델테이블/학습패널/차트/배포/빈상태 래퍼 |
| 12 | tab | filter | segment | sm | default | 모델 타입 필터 |
| 13 | alert | warning | outlined | sm | default | 배포 경고 (bg-amber-50, border) |

---

## PG-16_benchmarking.html — 11개 요소

| # | Component | data-intent | data-variant | data-size | data-state | 설명 |
|---|-----------|-------------|--------------|-----------|------------|------|
| 1-6 | badge (6) | danger/info/neutral/warning/status | soft | xs/sm | default | 알림카운트/활성/라벨/등급/점수 뱃지 |
| 7-8 | tab (2) | filter | segment | sm | default | 업종/지표 필터 탭 |
| 9-11 | card (3) | container | outlined | md/lg | default | 비교테이블/벤치마크/추이 차트 래퍼 |

---

## 총 변경 통계 (전체 16페이지)

| 페이지 | badge | tab | alert | card | 합계 |
|--------|-------|-----|-------|------|------|
| PG-01_login | 0 | 1 | 3 | 1 | **5** |
| PG-02_dashboard | 4 | 1 | 1 | 7 | **13** |
| PG-03_agent_templates | 8 | 0 | 0 | 4 | **12** |
| PG-04_deploy_wizard | 0 | 0 | 3 | 4 | **7** |
| PG-05_connector_hub | 3 | 1 | 0 | 1 | **5** |
| PG-06_realtime_monitoring | 3 | 1 | 0 | 4 | **8** |
| PG-07_alert_management | 4 | 1 | 0 | 2 | **7** |
| PG-08_compliance_reports | 7 | 0 | 1 | 6 | **14** |
| PG-09_audit_log | 4 | 0 | 1 | 1 | **6** |
| PG-10_user_permissions | 6 | 1 | 2 | 0 | **9** |
| PG-11_system_dr | 13 | 0 | 3 | 6 | **22** |
| PG-12_settings | 2 | 1 | 1 | 8 | **12** |
| PG-13_workflow_builder | 3 | 0 | 0 | 9 | **12** |
| PG-14_customer_health | 10 | 2 | 0 | 4 | **16** |
| PG-15_ai_pipeline | 6 | 1 | 1 | 5 | **13** |
| PG-16_benchmarking | 6 | 2 | 0 | 3 | **11** |
| **합계** | **79** | **12** | **16** | **65** | **172** |

---

## 미적용 요소 (범위 외)

- `data-component="stat"`: 전체 페이지에 존재하는 stat 요소 — 대상 외
- `data-component="modal"`: 전체 페이지에 존재하는 modal 요소 — 대상 외
