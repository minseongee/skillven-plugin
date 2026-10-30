# Skillven for Claude Code

Claude finds a security-reviewed [Agent Skill](https://agentskills.io) or step-by-step
workflow when a task needs one, and installs it after you approve once.
Browse everything at [skillven.com](https://skillven.com).

[한국어](#한국어)

## Install

In Claude Code, run these two lines in order. The first adds this marketplace; without it
`/plugin install` can't find skillven.

```
/plugin marketplace add minseongee/skillven-plugin
/plugin install skillven@skillven
```

From a terminal:

```bash
claude plugin marketplace add minseongee/skillven-plugin && claude plugin install skillven@skillven
```

Then work as usual. When a task would go better with a skill, Claude searches Skillven and
asks before installing anything. You can also ask directly:

- `/skillven:find extract tables from PDFs`: search and pick
- `/skillven:install skill 123`: install the one you chose on skillven.com (each page has
  its command to copy)

## What it does

- **Searches on your machine.** The plugin downloads a signed catalog from
  `cdn.skillven.com` and searches it locally. Your requests and Claude's searches are never
  sent anywhere.
- **Installs only what was reviewed.** Every skill version is pinned to a commit, checked by
  automated rules and read by an AI reviewer. You see the review in the approval dialog,
  and every installed file is checked against the reviewed copy's hash. Skills that are
  blocked later are refused even from an older catalog.
- **Workflows.** Some jobs take several skills in order; a workflow installs them together
  and walks through the steps with you.

## Privacy

The plugin sends anonymous usage events (a skill was installed, declined, found helpful)
and, after a workflow runs, a short review of how it went, never your request, code or
project. Turn workflow reviews off in the plugin's settings (`report_workflow_outcomes`).
Details: [skillven.com/privacy](https://skillven.com/privacy).

## About this repository

This repository only distributes the plugin. It is published automatically from
Skillven's main repository, so changes made here are overwritten; report issues on this
repository.

---

## 한국어

작업에 스킬이 필요하면 Claude가 보안 검토를 거친 [Agent Skill](https://agentskills.io)이나 워크플로를
찾아서, 처음 한 번 승인하면 설치해요. 전체 목록은 [skillven.com/ko](https://skillven.com/ko)에서 볼 수 있어요.

### 설치

Claude Code에서 두 줄을 순서대로 입력해요. 첫 줄이 이 마켓플레이스를 추가해요. 빼먹으면
`/plugin install`이 skillven을 못 찾아요.

```
/plugin marketplace add minseongee/skillven-plugin
/plugin install skillven@skillven
```

터미널에서는:

```bash
claude plugin marketplace add minseongee/skillven-plugin && claude plugin install skillven@skillven
```

그다음은 평소처럼 일을 시키면 돼요. 스킬이 있으면 더 나은 작업이면 Claude가 Skillven에서 찾아보고,
설치 전에 꼭 물어봐요. 직접 요청할 수도 있어요.

- `/skillven:find PDF에서 표 뽑기`: 찾아서 고르기
- `/skillven:install skill 123`: skillven.com에서 고른 스킬 설치하기 (페이지마다 복사할 명령이 있어요)

### 하는 일

- **검색은 내 컴퓨터에서.** 플러그인이 `cdn.skillven.com`에서 서명된 목록을 내려받아 내 컴퓨터에서
  검색해요. 요청 내용이나 검색어는 밖으로 나가지 않아요.
- **검토한 것만 설치.** 모든 스킬 버전은 커밋에 고정되고, 자동 규칙과 AI가 검토해요. 승인 창에서
  검토 결과를 보여 주고, 설치하는 파일마다 검토한 것과 해시를 대조해요. 나중에 차단된 스킬은 예전
  목록에서도 설치를 거부해요.
- **워크플로.** 여러 스킬을 순서대로 써야 하는 일은 워크플로가 한꺼번에 설치하고 단계별로 함께 진행해요.

### 개인정보

플러그인은 익명 사용 이벤트(설치함, 거절함, 도움이 됨)와, 워크플로 실행 후 짧은 후기만 보내요.
요청 내용, 코드, 프로젝트 정보는 보내지 않아요. 워크플로 후기는 플러그인 설정
(`report_workflow_outcomes`)에서 끌 수 있어요. 자세한 내용:
[skillven.com/ko/privacy](https://skillven.com/ko/privacy)

### 이 저장소에 대해

이 저장소는 플러그인 배포만 해요. Skillven 본 저장소에서 자동으로 올라오기 때문에 여기서 바꾼 내용은
덮어써져요. 문제는 이 저장소의 이슈로 알려 주세요.
