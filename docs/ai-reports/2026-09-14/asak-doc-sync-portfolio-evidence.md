# ASAK 포트폴리오 근거 문서 동기화 — 2026-09-14

## 1. 대상 저장소와 기준 커밋

| 저장소 | 기준 커밋 | 상태 |
| --- | --- | --- |
| `ASAK` / `asak-docs` | `2bc5f7d` | `main == origin/main`, 기존 `docs/ai-reports/2026-09-13/` 미추적 변경 보존 |
| `devportfolio` | `794b66a` | `main == origin/main`, 작업 트리 clean 상태에서 문서만 수정 시작 |
| `asak-agent-kit` | `dddaf96` | `main == origin/main` |

`https://github.com/hagenie128/ASAK-skill`과 `https://github.com/hagenie128/asak-agent-kit`은 확인 시점에 같은 HEAD `dddaf96`을 반환했다. 공개 포트폴리오 링크는 사용자가 지정한 `ASAK-skill` 주소를 사용한다.

## 2. 확인한 코드·문서·원격 근거

- `ASAK-back/docs/ai-reports/2026-08-20/dashboard-performance-optimization.md`
- `ASAK/docs/ai-reports/2026-08-19/asak-doc-sync-schema-actual-ddl.md`
- `ASAK/docs/wiki/qa-execution-report-2026-09-02.md`
- `ASAK/docs/wiki/qa-kiosk-execution-report-2026-09-02.md`
- `ASAK/worklog/entries/이하진/2026-07-16-product-bible-wbs-release-governance.md`
- `asak-agent-kit/README.md`
- Notion `ASAK 키오스크 프로젝트`, `키오스크 풀스택 프로젝트`, 포트폴리오 요약, `00~11` 전체 기준 페이지
- `devportfolio/index.html`, `devportfolio/PORTFOLIO_REVIEW.md`

Figma는 이번 문서 동기화의 대상이 아니며 새로 조회하거나 수정하지 않았다.

## 3. 갱신한 문서

1. `docs/portfolio/이하진/asak-lee-hajin-portfolio.md`
   - 공식 기간을 `2026.07.02~09.02`로 정정
   - 역할을 `2인 공동개발 · Admin/Backend 중심`으로 명확화
   - Data Modeling / Technical Decisions / Performance & QA / Project Coordination 근거 추가
   - 전체 대시보드 성능과 View 단일 조회 실패 수치 분리
   - 최종 API QA 결과와 미검증 범위 추가
   - asak-docs, Notion, WBS, asak-agent-kit 링크 연결
2. `devportfolio/PORTFOLIO_REVIEW.md`
   - 코드 수정 전 채용용 재편 명세로 갱신
   - Hero·프로젝트·Case Study의 순서와 문장 원칙 확정
   - 노출 가능한 수치와 보류할 수치 구분
3. Notion ASAK 프로젝트 27개 페이지
   - 프로젝트 루트, 풀스택 프로젝트 본문, 포트폴리오 요약에 2026-09-14 최종 기준 추가
   - `00. 현재 운영 기준`부터 `11. 최종 제출 체크리스트`까지 페이지별 최종 상태 추가
   - `지금 작업`, `구현 기준`, `워크로그·포트폴리오`, 종합 기획서, 최종 발표, 온보딩, FWD 초기 문서와 WBS 미러 등 보조 페이지 12개를 종료 상태/역사 문서로 구분
   - 2026-09-02 Admin/Kiosk QA, READY 취소 409 재검증, DB/성능 근거, 미검증 범위를 기능별로 분리
   - 기존 일정·회의·계획 블록과 연결 데이터베이스는 삭제하지 않고 당시 이력으로 보존
4. `devportfolio/index.html`, `css/layout.css`, `css/components.css`, `js/app.js`
   - 사용자 `코드 수정 승인` 후 Backend / Product Engineer 포지셔닝과 채용용 정보 순서 반영
   - ASAK·ASAK Agent Kit 프로젝트 카드와 5개 챕터 Case Study 구성
   - 성능 단계, 실패한 View 실험, API QA와 미검증 범위를 최신 근거로 교체
   - 화면 순서와 접근성 읽기 순서가 같도록 기존 scrollspy 스크립트에서 섹션 DOM 순서를 정렬

## 4. 변경 근거

- Notion 프로젝트 허브와 WBS는 프로젝트를 2인 팀, 9주, `7/2~9/2`로 기록한다.
- 성능 보고서는 대시보드 전체 응답을 약 8초에서 0.43~0.50초로 줄인 단계와, View 재작성 단일 조회가 1.3초에서 6.6~6.8초로 악화돼 원복된 사건을 분리한다.
- 2026-09-02 QA는 Admin API 22/24, Kiosk API 17/18 PASS를 기록하며, 결제수단 Admin→Kiosk 반영·일부 재료 품절 연쇄·브라우저 UI·실물 장치에는 실패 또는 미검증 상태가 남아 있다.
- 옵션 정책 감사는 레거시 `menu_option` 9,166건, `opt_policy` 82건, `opt_policy_item` 734건을 확인한다. `menu_opt_policy`는 seed-v3 279건과 같은 날 실DB 감사 324건이 달라 포트폴리오 수치 노출을 보류했다.
- 문서·WBS 기록은 요구사항부터 테스트까지 ID로 연결하고 완료 근거를 분리한 작업을 보여 주지만, 공식 PM 직함의 증거는 아니다.

## 5. 실행 또는 검증 결과

- 세 저장소의 현재 브랜치·원격·HEAD를 읽기 전용으로 확인했다.
- `asak-docs`, `ASAK-skill`, `asak-agent-kit` 원격 HEAD를 비교했다.
- Notion 연결에서 프로젝트 루트·포트폴리오·`00~11`과 보조 문서를 fetch한 뒤 27개 페이지를 갱신하고, 각 페이지를 다시 fetch해 `2026-09-14` 최종 블록 저장을 확인했다.
- 로컬 포트폴리오를 데스크톱과 390px 모바일에서 열어 시각 순서·가로 overflow·테마·아코디언을 확인했고 브라우저 콘솔 오류가 없음을 확인했다.
- 브라우저에서 `https://admin.asak.stackroom.cloud/`과 `https://asak.stackroom.cloud/`이 각각 ASAK Admin·ASAK 키오스크 화면으로 열리는 것을 확인했다.
- 포트폴리오 공개 주소는 `https://hajin.stackroom.cloud/` 기준으로 연결했다.
- 애플리케이션 빌드·API·DB 테스트는 이번 동기화에서 재실행하지 않았고 기존 실행 보고서만 사용했다.

## 6. 남은 불일치

- Notion의 과거 일정·계획·체크리스트는 프로젝트 이력 보존을 위해 본문 아래에 남아 있다. 각 페이지 맨 위의 2026-09-14 최종 블록이 현재 판정이다.
- `menu_opt_policy` 행 수는 seed-v3와 실DB 감사 스냅샷이 다르다.
- `devportfolio`의 현재 `index.html`은 여전히 `Full-Stack Developer`, `2026.07.01~08.21`, `Admin / Backend 담당`을 사용한다.
- 프로젝트 이미지 `assets/images/asak-admin.png`는 아직 없다.

## 7. 결정 필요 사항

- 포트폴리오 화면 코드는 사용자의 명시적 `코드 수정 승인` 이후 반영했으며, commit/push는 실행하지 않았다.
- 공개 이력서 파일과 관리자 화면 캡처는 개인정보·공개 범위를 확인한 후 assets에 추가한다.

## 8. 수정하지 않은 범위

- ASAK React·Java 애플리케이션 소스코드
- DB와 시드 데이터
- Figma
- DevCopilot 원격 문서
- Git commit, push, branch, merge
