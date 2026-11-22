# 기획 저장소

프로젝트별 기능 요청과 기획 문서를 관리하는 저장소입니다.

## 디렉터리 구조

```text
.
├── README.md                             # 저장소 소개와 사용법
├── AGENTS.md                             # 기획 작업 흐름과 문서 작성 지침
├── planning-process-guide.md             # Codex CLI를 활용한 단계별 기획 가이드
├── change-request-guide.md               # 요청사항 변경 시 산출물 갱신 가이드
├── .agents/                              # 저장소 전용 Codex 리소스
│   └── skills/                           # 기획 단계별 Codex 스킬
│       ├── new-feature/
│       │   └── SKILL.md                  # 기능 폴더 생성과 요청서 템플릿 복사 절차
│       ├── analyze-request/
│       │   └── SKILL.md                  # 요청서 검토와 분석서 작성 절차
│       ├── define-requirements/
│       │   └── SKILL.md                  # 사용자 흐름, 정책, 예외, 확인 기준 정의 절차
│       ├── plan-tasks/
│       │   └── SKILL.md                  # 요구사항을 실행 과제와 완료 조건으로 구체화하는 절차
│       ├── define-screen-flow/
│       │   └── SKILL.md                  # Figma 화면정의서와 프로세스 흐름 작성 절차
│       └── export-project-status/
│           └── SKILL.md                  # 프로젝트별 기획 문서 작성률과 미작성 문서 집계 절차
├── projects/                             # 프로젝트별 기획 문서
│   ├── raidio/                           # raidio 프로젝트
│   │   ├── project.md                    # 프로젝트 목표, 범위, 주요 결정 사항
│   │   └── features/                     # 기능별 기획 문서 폴더
│   ├── raidio-biz/                       # raidio-biz 프로젝트
│   │   ├── project.md                    # 프로젝트 목표, 범위, 주요 결정 사항
│   │   └── features/                     # 기능별 기획 문서 폴더
│   │       └── winter-new-channel-popup/ # 겨울 신규채널 안내 기능
│   │           ├── request.md            # 요청 배경과 기대 결과
│   │           ├── analysis.md           # 요청 내용 검토와 확인이 필요한 질문
│   │           ├── requirements.md       # 사용자 흐름, 정책, 예외, 확인 기준
│   │           └── tasks.md              # 실행 과제, 선행 조건, 완료 조건
│   └── raidio-brand/                     # raidio-brand 프로젝트
│       ├── project.md                    # 프로젝트 목표, 범위, 주요 결정 사항
│       └── features/                     # 기능별 기획 문서 폴더
├── status-reports/                       # 프로젝트별 기획 산출물 작업현황표
│   ├── raidio-status.md                  # raidio 작업현황표
│   ├── raidio-biz-status.md              # raidio-biz 작업현황표
│   └── raidio-brand-status.md            # raidio-brand 작업현황표
└── templates/                            # 공용 기획 문서 템플릿
    ├── request.md                        # 요청 배경, 대상 사용자, 기대 결과 정리
    ├── analysis.md                       # 현재 흐름, 근거, 가설, 대안 검토
    ├── requirements.md                   # 범위, 동작, 예외, 확인 기준 정의
    └── tasks.md                          # 실행 과제, 선행 조건, 완료 조건 정리
```

## 기획 프로세스

[기획 프로세스 사용 가이드](planning-process-guide.md)에서 Codex CLI 실행 방법과 단계별 산출물 작성·검토 절차를 확인할 수 있습니다.

대표나 타 부서에서 받은 요청과 기획자가 직접 제안한 기능은 같은 흐름으로 정리합니다.

1. **요청 접수** — 누가 어떤 기능이나 변경을 제안했는지 기록합니다.
2. **요청 내용 정리** — 요청 배경, 대상 사용자, 기대 결과, 일정과 제약을 정리합니다. 추가로 확인할 내용은 질문으로 남깁니다. [`request.md`](templates/request.md)
3. **요청 내용 분석** — 현재 사용자 흐름과 확인된 근거를 살펴보고, 어떤 문제를 해결해야 하는지 파악합니다. 요청한 방식이 목적에 맞는지 검토하고 필요하면 다른 방법과 비교합니다. [`analysis.md`](templates/analysis.md)
4. **프로세스 정리** — 사용자가 어디서 시작해 무엇을 하고 어떤 결과를 보는지 순서대로 정리합니다. 중간에 취소하거나 오류가 발생할 때의 흐름도 함께 정의합니다. [`requirements.md`](templates/requirements.md)
5. **정책 정리** — 누구에게 언제 적용하는지, 조건별로 어떻게 동작하는지, 예외는 어떻게 처리하는지 정합니다. 요구사항을 충족했는지 확인할 수 있도록 조건과 기대 결과를 적습니다. [`requirements.md`](templates/requirements.md)

## Codex CLI로 기능 요청서 추가하기

1. 저장소 루트에서 터미널을 열고 `codex`를 실행합니다.
2. Codex 입력창에 `$new-feature` 뒤에 프로젝트 폴더명과 새 기능 폴더명을 차례로 입력합니다. 기능 폴더명은 `winter-new-channel-popup`처럼 영문 소문자, 숫자, 하이픈으로 작성합니다.

   ```text
   $new-feature raidio-biz winter-new-channel-popup
   ```

3. Codex가 알려준 경로에서 `request.md`를 엽니다. 위 예시에서는 공용 템플릿을 `projects/raidio-biz/features/winter-new-channel-popup/request.md`로 복사합니다. 같은 기능 폴더가 이미 있으면 생성이 중단되므로 기존 요청서를 열어 작성하면 됩니다.
4. 각 질문 아래의 ‘여기에 입력’을 답변으로 바꿉니다. 마크다운 문법을 몰라도 평소처럼 글을 적으면 됩니다. 아직 모르는 항목은 ‘확인 필요’라고 적습니다.

## Codex CLI로 기능 요청서 분석하기

1. 기능 폴더의 `request.md`에 요청 배경, 대상 사용자, 기대 결과를 작성합니다.
2. 저장소 루트에서 `codex`를 실행하고, Codex 입력창에 프로젝트 폴더명과 기능 폴더명을 순서대로 입력합니다.

   ```text
   $analyze-request raidio-biz winter-new-channel-popup
   ```

3. 같은 기능 폴더에 생성된 `analysis.md`를 확인합니다. 변경 내용과 적용 위치가 명확하고 기존 흐름이나 정책에 영향이 없는 요청은 **검토 요약**에 변경 내용과 확인 방법을 적습니다. 추가 검토가 필요하면 현재 흐름, 근거, 해결 방법 등 필요한 항목을 작성합니다.
4. 분석서의 **남은 질문**에 답을 받으면 해당 질문 바로 아래에 적습니다. 아직 답을 받지 못했다면 ‘확인 필요’로 남깁니다.

요청 자체가 바뀌면 `request.md`에서 바뀐 항목을 수정하고 변경 기록을 남깁니다. 예를 들어 팝업 요청이 홈 배너로 바뀌었다면, 요청명과 기대 결과를 배너에 맞게 수정한 뒤 같은 `$analyze-request` 명령으로 분석서를 다시 갱신합니다.

## Codex CLI로 기능 요구사항 정의하기

1. 기능 폴더의 `analysis.md`에서 **남은 질문**에 대한 답변을 저장합니다.
2. 저장소 루트에서 `codex`를 실행하고, Codex 입력창에 다음과 같이 입력합니다.

   ```text
   $define-requirements raidio-biz winter-new-channel-popup
   ```

3. 같은 기능 폴더에 생성된 `requirements.md`를 확인합니다. Codex는 요청서와 분석서를 바탕으로 사용자 흐름, 정책과 예외, 동작 확인 방법을 작성하고, 미확정 내용은 **결정이 필요한 사항**에 남깁니다.
4. 분석서에 답변을 추가한 뒤에는 같은 명령을 입력하고 기존 `requirements.md`에 답변을 반영해 달라고 요청합니다. 추가로 확정한 정책은 Codex 입력창에 바로 전달할 수도 있습니다.

   ```text
   raidio-biz의 winter-new-channel-popup/requirements.md를 갱신해주세요.
   겨울 신규채널 안내는 스와이퍼의 첫 번째 항목에 표시해요.
   2026년 12월 26일까지 당일을 포함해 노출해요.
   홈 화면의 ‘추천채널’ 영역은 항상 있어요.
   ```

## Codex CLI로 Figma 화면정의서와 프로세스 흐름 작성하기

1. 기능 폴더에 `requirements.md`와 `tasks.md`를 준비합니다. 저장소 루트에서 `codex`를 실행하고, Figma MCP가 연결되어 있고 대상 Figma Design 파일에 편집 권한이 있는지 확인합니다.
2. Codex 입력창에 `$define-screen-flow` 뒤에 프로젝트 폴더명, 기능 폴더명, Figma Design URL을 차례로 입력합니다. 예시 URL은 실제 파일, 페이지 또는 프레임 링크로 바꿉니다. 기준 화면이 정해져 있다면 해당 프레임 링크를 사용합니다.

   ```text
   $define-screen-flow raidio-biz winter-new-channel-popup https://www.figma.com/design/FILE_KEY/Raidio-Biz?node-id=123-456
   ```

3. Codex가 알려준 Figma 섹션 링크를 엽니다. **화면정의서**에는 화면 요소, 표시 조건, 사용자 동작과 상태별 정책이 정리됩니다. **프로세스 흐름**에는 시작 화면부터 결과까지 사용자 행동과 화면 이동, 조건별 분기와 예외가 표시됩니다.
4. 결과와 함께 안내된 ‘확인 필요’ 항목을 검토합니다. 파일 링크만 입력해 기준 화면을 특정하기 어려운 경우에는 Codex에 해당 프레임 링크를 전달합니다.

[define-screen-flow 스킬 문서](.agents/skills/define-screen-flow/SKILL.md)

## 요청사항 변경 가이드

[요청사항 변경 가이드 보기](change-request-guide.md)

## Codex CLI로 프로젝트별 작업현황표 내보내기

저장소 루트에서 `codex`를 실행한 뒤, Codex 입력창에 `$export-project-status`와 프로젝트 폴더명을 입력합니다. 전체 프로젝트를 내보내려면 프로젝트 폴더명 대신 `all`을 입력합니다.

```text
$export-project-status raidio-biz
$export-project-status all
```

현황표는 기본적으로 [status-reports/](status-reports/)에 `<프로젝트>-status.md`로 저장됩니다. 다른 폴더에 저장하려면 프로젝트명 뒤에 저장소 루트 기준 폴더 경로를 입력합니다. 같은 위치에서 다시 실행하면 기존 현황표가 갱신됩니다.

현황표에는 기능별·프로젝트별 **기획 산출물 작성률**과 기능별 **미작성 문서 목록**이 표시됩니다. 기능마다 요청서(`request.md`), 분석서(`analysis.md`), 요구사항(`requirements.md`), 실행 과제(`tasks.md`)를 확인합니다. 파일이 없거나 비어 있거나 양식만 남아 있으면 미작성으로 집계합니다. 예를 들어 4종 중 3종을 작성하면 **75% (3/4)**로 표시됩니다. 등록된 기능이 없는 프로젝트는 **해당 없음**으로 표시합니다.

[현황표 예시](status-reports/raidio-biz-status.md) · [export-project-status 스킬 문서](.agents/skills/export-project-status/SKILL.md)
