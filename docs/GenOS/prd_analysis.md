# GenOS 금융권 AI 보안 솔루션 — PRD 분석 보고서

> **분석일:** 2026-02-06
> **소스:** `prd_description_agent/outputs/description_20260206_195335.json` (11,700줄 / 421KB)
> **버전:** Description v1.0 / Architect v2.0

---

## 1. 프로젝트 개요

| 항목 | 값 |
|------|---|
| **제품명** | GenOS (제논) Financial AI Security Platform |
| **도메인** | 금융권 AI 보안 솔루션 |
| **원본 PRD** | `prd_agent/docs/genon/genos-financial-ai-security-prd.md` |

---

## 2. 페르소나 (3명)

| ID | 이름 | 역할 | 숙련도 |
|---|---|---|---|
| P1 | 김부장 | 금융사 IT 보안 담당자 | 중급 — 보안 솔루션 운영 경험, AI 에이전트는 처음 |
| P2 | 이과장 | 금융사 디지털 혁신 PM | 초급 — 비즈니스 성과/리포트 중심 |
| P3 | 제논 CSM/PM | 내부 고객 성공 매니저 | 고급 — 전체 시스템 이해, 고객 건강 지표 선제 관리 |

---

## 3. 페이즈별 페이지 구성 (총 16페이지)

### Phase 1 (MVP) — 12페이지

| Page ID | 페이지명 | 컴포넌트 | 대상 페르소나 |
|---------|---------|----------|-------------|
| PG-01 | 로그인 | LoginForm, SSOProviderList, MFAVerification | P1, P2, P3 |
| PG-02 | 메인 대시보드 | StatusSummaryCards, DetectionTrendChart, AlertTimeline, QuickActions | P1, P2 |
| PG-03 | 에이전트 템플릿 라이브러리 | CategoryFilter, TemplateGrid, TemplateDetailPanel | P1 |
| PG-04 | 에이전트 배포 위저드 | StepProgress, WizardContent, NavigationButtons | P1 |
| PG-05 | 데이터 소스 커넥터 허브 | ConnectorList, ConnectionStatus, AddConnectorForm | P1 |
| PG-06 | 실시간 모니터링 대시보드 | LiveAlertFeed, DetectionHeatmap, TransactionDetail, ActionPanel | P1 |
| PG-07 | 알림 관리 | ChannelSettings, EscalationRules, AlertHistory | P1, P2 |
| PG-08 | 컴플라이언스 리포트 센터 | ReportTemplates, ReportScheduler, ReportHistory, ReportPreview | P1, P2 |
| PG-09 | 감사 로그 뷰어 | LogSearchBar, LogTable, LogDetail, ExportPanel | P1 |
| PG-10 | 사용자/권한 관리 | UserList, RoleManager, PermissionMatrix | P1 |
| PG-11 | 시스템 상태/DR 모니터링 | RegionStatusCards, BackupStatus, FailoverHistory, DRTestSchedule | P1 |
| PG-12 | 설정 | ProfileSettings, SecuritySettings, NotificationPreferences, DisplaySettings | P1, P2, P3 |

### Phase 2 — 2페이지

| Page ID | 페이지명 | 컴포넌트 | 대상 페르소나 |
|---------|---------|----------|-------------|
| PG-13 | 워크플로우 빌더 | NodePalette, WorkflowCanvas, PropertyPanel, VersionHistory | P1 |
| PG-14 | 고객 Health 대시보드 | HealthScorePanel, CustomerOverview, UsageAnalytics, MaintenanceCalendar | P3 |

### Phase 3 — 2페이지

| Page ID | 페이지명 | 컴포넌트 | 대상 페르소나 |
|---------|---------|----------|-------------|
| PG-15 | AI 재학습 파이프라인 관리 | ModelVersionList, TrainingStatus, PerformanceComparison, DeploymentControl | P3 |
| PG-16 | 벤치마킹 대시보드 | IndustryBenchmarks, CrossCustomerMetrics, TrendAnalysis | P3 |

---

## 4. 네비게이션 구조 (사이드바 7그룹)

```
┌─────────────────────────────┐
│  GenOS Logo                 │
├─────────────────────────────┤
│  보안 운영                   │
│    ├ PG-02 메인 대시보드      │
│    ├ PG-06 실시간 모니터링    │
│    └ PG-07 알림 관리          │
│                              │
│  에이전트 관리                │
│    ├ PG-03 템플릿 라이브러리  │
│    ├ PG-04 배포 위저드        │
│    └ PG-05 커넥터 허브        │
│                              │
│  자동화                      │
│    └ PG-13 워크플로우 빌더    │
│                              │
│  리포팅/감사                  │
│    ├ PG-08 컴플라이언스 리포트│
│    └ PG-09 감사 로그 뷰어    │
│                              │
│  시스템 관리                  │
│    ├ PG-10 사용자/권한 (admin)│
│    ├ PG-11 시스템/DR (admin)  │
│    └ PG-12 설정               │
│                              │
│  내부 관리 (CSM)              │
│    ├ PG-14 고객 Health        │
│    └ PG-16 벤치마킹           │
│                              │
│  고도화                      │
│    └ PG-15 AI 재학습          │
└─────────────────────────────┘
```

---

## 5. 통계 요약

| 지표 | 값 |
|------|---|
| 총 페이지 수 | 16 |
| 총 컴포넌트 수 | 51 |
| 페이지당 평균 컴포넌트 | 3.2개 |
| 최다 컴포넌트 페이지 | PG-06, PG-08, PG-11, PG-14 (4개) |
| Phase 1 비중 | 75% (12/16) |

---

## 6. 컴포넌트 명세 포함 항목

각 컴포넌트별로 아래 명세가 포함되어 있음:

- `fields` — 필드명, 타입, 필수 여부, validation 규칙
- `actions` — 사용자 실행 가능 액션
- `interaction` — 인터랙션 시나리오 (키보드, 포커스 등)
- `empty_state` — 데이터 없을 때 표시
- `loading_state` — 로딩 중 표시
- `error_state` — 에러 발생 시 표시
- `accessibility` — WCAG 2.1 AA (aria_label, keyboard_nav, focus_order, screen_reader_hint)
- `data_binding` — API 엔드포인트, 요청/응답 스키마, 폴링 주기

---

## 7. 구현 우선순위 (권장)

Phase 1 MVP 내에서도 아래 순서로 구현을 권장:

1. **PG-01 로그인** — 진입점, 인증 흐름 기반
2. **PG-02 메인 대시보드** — 로그인 후 랜딩, 전체 현황 파악
3. **PG-06 실시간 모니터링** — 핵심 가치 (이상 탐지)
4. **PG-03 에이전트 템플릿** → **PG-04 배포 위저드** — 에이전트 라이프사이클
5. **PG-05 커넥터 허브** — 데이터 소스 연결
6. **PG-07 알림 관리** → **PG-08 컴플라이언스** → **PG-09 감사 로그** — 운영/감사
7. **PG-10 사용자/권한** → **PG-11 시스템/DR** → **PG-12 설정** — 관리

---

## 8. 소스 파일 경로

| 파일 | 경로 |
|------|------|
| PRD Description JSON | `../prd_description_agent/outputs/description_20260206_195335.json` |
| PRD Description MD | `../prd_description_agent/outputs/description_result.md` |
| Architect Blueprint | `../prd_architect_agent/docs/deep-research-ui-blueprint.json` |
