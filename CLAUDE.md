# Agent Observability Dashboard

## 프로젝트 설명
Claude Code 에이전트 팀을 실시간 모니터링하는 Multi-Agent Observability Dashboard.
disler/claude-code-hooks-multi-agent-observability 를 포크해서 커스터마이징하여 관리한다.
이 프로젝트 자체는 에이전트의 작업 대상이 아니라 관제 도구다.

## 기술 스택
- Frontend: Vue 3 + TypeScript + Tailwind CSS (apps/client/)
- Backend: Bun + SQLite (apps/server/)
- Hook Scripts: Python + uv (.claude/hooks/)

## 디렉토리 구조 (수정 시 참고)
apps/client/src/components/
├── EventTimeline.vue     ← 타임라인 UI (이벤트 목록)
├── EventRow.vue          ← 개별 이벤트 행
├── LivePulseChart.vue    ← 실시간 활동 차트 (Canvas 기반)
├── FilterPanel.vue       ← 필터 패널
└── ChatTranscriptModal.vue ← 채팅 히스토리 뷰어

apps/client/src/composables/
├── useEventColors.ts     ← 에이전트별 색상 시스템 (여기서 색상 변경)
├── useEventEmojis.ts     ← 이벤트 타입별 이모지 매핑
└── useChartData.ts       ← 차트 데이터 집계 로직

## 개발 서버 실행
just start              # 서버 + 클라이언트 동시 실행
just stop               # 종료
just restart            # 재시작
# 대시보드: http://localhost:5173
# API 서버: http://localhost:4000

## 원본 업데이트 반영 방법
git fetch upstream
git merge upstream/main
# 충돌 시 내 커스터마이징을 우선하여 해결

## 이 프로젝트와 실제 작업 프로젝트의 관계
~/tools/agent-observability/   ← 이 대시보드 (관제탑)
        ↑ HTTP POST로만 연결
~/Downloads/project/project-a/ ← 실제 작업 프로젝트들 (피관찰 대상)
~/Downloads/project/project-b/
연결고리는 Hook의 HTTP POST 하나뿐. 대시보드 수정이 실제 프로젝트에 영향 없음.

## Remote 관리
- origin: 내 포크 레포 (Fork 후 URL 변경 필요)
- upstream: https://github.com/disler/claude-code-hooks-multi-agent-observability.git

## Fork 후 remote 변경 방법
git remote set-url origin https://github.com/내계정/claude-code-hooks-multi-agent-observability.git
git push -u origin main

<!-- MEMORY:START -->
# agent-observability

_Last updated: 2026-02-26 | 0 active memories, 0 total_

_For deeper context, use memory_search, memory_related, or memory_ask tools._
<!-- MEMORY:END -->
