# Hermes Agent + LLM Wiki

## 스냅샷

- 웹사이트 / 문서: https://hermes-agent.nousresearch.com/
- 레포 / skill: https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki
- 회사 / 관리자: Nous Research / Hermes Agent 관리자
- 상태: `llm-wiki` skill이 번들된 활성 공개 레포
- 오픈 소스: 예
- 배포 방식: Hermes는 사용자의 서버나 머신에서 실행되고, wiki는 로컬 Markdown 디렉터리로 저장됨
- 주 사용자: 확인 가능한 로컬 Markdown 세컨드 브레인을 원하는 local-first AI operator, researcher, agent 사용자
- 세컨드 브레인에서 가장 잘 맞는 역할: 에이전트가 운영하는 로컬 Markdown wiki
- 마지막 검토: 2026-05-31
- 검토 근거: Hermes Agent 웹사이트, 공식 `hermes-agent` 레포, 번들된 `skills/research/llm-wiki/SKILL.md`

## 한 줄 요약

Hermes Agent + LLM Wiki는 Hermes에 번들된 skill을 사용해 원본 자료로부터 상호 연결된 Markdown 지식 베이스를 만들고, 검색하고, 점검하고, 유지합니다.

## 세컨드 브레인 적합도

Hermes Agent + LLM Wiki는 관리형 세컨드 브레인 제품이라기보다 로컬에서 에이전트가 운영하는 wiki 패턴으로 이해하는 것이 정확합니다. 이 skill은 파일, URL, 논문, transcript, 붙여넣은 텍스트를 원본 자료, entity page, concept page, comparison page, query page, index, append-only log로 정리하도록 에이전트에게 명시적인 작업 규칙을 줍니다.

읽을 수 있는 Markdown 안에서 지식이 누적되기를 원하고, 에이전트가 구조를 유지하도록 맡길 수 있는 사용자에게 잘 맞습니다. 다만 커넥터가 많은 호스팅형 제품, 팀 거버넌스 계층, 범용 memory API는 아닙니다.

## 기능

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | 로컬 또는 사용자 서버 소유. Hermes는 사용자가 통제하는 인프라에서 실행되고 wiki는 기본적으로 `~/wiki` 또는 설정한 `WIKI_PATH`에 저장됩니다. |
| 맥락 수집 | skill의 작업 흐름을 통해 URL, PDF, 붙여넣은 텍스트, 파일, article, paper, transcript, asset을 다룹니다. 그 자체로 넓은 OAuth 커넥터 계층은 아닙니다. |
| 지식 정리 | `SCHEMA.md`, `index.md`, `log.md`, raw source 폴더, entity page, concept page, comparison page, query page, YAML frontmatter, tag, wikilink, confidence, contradiction marker를 사용하는 Markdown wiki 구조가 내장되어 있습니다. |
| Memory 발전 | 부분 지원 / 에이전트 운영형. ingest, re-ingest, query 저장, lint, source drift 확인, page split, archive, log rotation 규칙은 정의되어 있지만 품질은 에이전트가 skill을 잘 따르는지와 사용자가 유지보수를 실행하거나 예약하는지에 달려 있습니다. |
| 검색 / 활용 | wiki orientation, file search, 관련 page 읽기, compiled page 기반 종합 답변, 가치 있는 답변을 `queries/` 또는 `comparisons/`에 다시 저장하는 흐름을 지원합니다. 기본적으로 vector DB나 graph RAG engine은 아닙니다. |
| 에이전트 활용 / 쓰기 반영 | Hermes 내부의 번들 skill로 내장되어 있습니다. 호출되면 에이전트가 Markdown wiki 파일을 만들고 업데이트할 수 있습니다. |
| 개인 / 팀 범위 | 부분 지원. 여러 wiki 디렉터리, schema, vault로 프로젝트를 나눌 수 있지만 팀 permission과 governance는 파일시스템, sync, 운영 프로세스의 책임입니다. |
| 검토 / 정정 | Markdown 관점에서는 내장입니다. 사용자는 page를 직접 확인/수정하고, lint를 실행하고, low-confidence 또는 contested page를 표시하고, claim을 raw source까지 추적할 수 있습니다. |
| 프라이버시 / 통제권 | wiki 자체는 로컬 파일 통제권이 강합니다. 실제 모델, 브라우저, web extraction, sync의 프라이버시는 Hermes 배포 방식과 provider 설정에 달려 있습니다. |
| 설정 / 운영 | 중간. Hermes에는 빠른 설치 경로가 있지만 wiki 위치 선택, source 선별, 에이전트가 쓴 내용 검토, 지속적인 wiki 유지보수는 사용자가 책임져야 합니다. |

## 강점

- 공식 Hermes Agent 레포에 직접 번들되어 있습니다.
- 불투명한 memory record 대신 확인 가능한 Markdown을 만듭니다.
- raw source와 curated wiki page를 분리합니다.
- schema, index, log, provenance, confidence, contradiction 관리를 장려합니다.
- Obsidian 호환 wikilink와 로컬 파일 검토에 잘 맞습니다.
- LLM Wiki의 "한 번 compile하고 계속 재사용한다"는 패턴에 잘 맞습니다.

## 한계

- 관리형 커넥터 제품은 아닙니다. source capture는 에이전트, 파일, workflow 중심입니다.
- 계정, 프로젝트, 팀, 보존 정책, export 제어가 있는 호스팅형 대시보드가 아닙니다.
- 기본적으로 vector DB, graph DB, 자동 cross-app memory 계층은 아닙니다.
- 품질은 에이전트가 skill 지침을 따르는 정도와 사용자의 검토 습관에 의존합니다.
- 팀 사용에는 외부 파일시스템, git, sync, vault, permission 설계가 필요합니다.
- OpenClaw에서도 installable/community skill로 LLM Wiki 스타일 workflow를 붙일 수는 있지만, OpenClaw core에 LLM Wiki가 built-in으로 포함된 것은 확인되지 않았습니다.

## 잘 맞는 사용자

- 로컬에서 읽을 수 있고 오래 유지할 수 있는 Markdown 세컨드 브레인을 원하는 사용자.
- 자료를 entity, concept, comparison page로 compile하고 싶은 researcher.
- LLM Wiki workflow용 번들 skill을 원하는 Hermes 사용자.
- 호스팅형 memory 인프라보다 확인 가능한 파일을 선호하는 사람.

## 잘 맞지 않는 사용자

- 원클릭 앱 커넥터와 호스팅형 백그라운드 정리를 원하는 사용자.
- 내장 workspace permission과 admin control이 필요한 팀.
- application backend용 memory API/SDK가 필요한 builder.
- 에이전트가 작성한 Markdown을 검토하거나 관리하고 싶지 않은 사용자.

## 트레이드오프

Hermes Agent + LLM Wiki는 강한 로컬 확인 가능성과 명확한 지식 compile 흐름을 주지만, 그만큼 책임이 사용자와 에이전트 루프에 더 많이 남습니다. 강력한 DIY/local-first 경로이지만, 설정 부담이 낮은 end-to-end 세컨드 브레인 제품은 아닙니다.

## 공식 설정 / 평가 링크

- [Hermes Agent 웹사이트](https://hermes-agent.nousresearch.com/)
- [Hermes Agent GitHub 레포](https://github.com/NousResearch/hermes-agent)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hermes LLM Wiki SKILL.md](https://raw.githubusercontent.com/NousResearch/hermes-agent/main/skills/research/llm-wiki/SKILL.md)

## 출처

- [Hermes Agent 웹사이트](https://hermes-agent.nousresearch.com/)
- [Hermes Agent GitHub 레포](https://github.com/NousResearch/hermes-agent)
- [Hermes LLM Wiki skill 디렉터리](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hermes LLM Wiki SKILL.md](https://raw.githubusercontent.com/NousResearch/hermes-agent/main/skills/research/llm-wiki/SKILL.md)
- [Karpathy LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
