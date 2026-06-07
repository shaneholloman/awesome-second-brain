# Awesome AI Second Brain 기여 가이드

이 레포는 AI-native 세컨드 브레인을 만들기 위한 기존 도구와 제품을 비교합니다. 기여 내용은 독자가 무엇을 평가해야 하는지, 어떤 트레이드오프가 중요한지, 어떤 workflow가 실제로 지원되는지 판단하는 데 도움이 되어야 합니다.

## 포함해야 하는 것

이 레포는 AI-native 세컨드 브레인 시스템을 의사결정 중심으로 비교합니다. 좋은 기여는 실용적인 질문에 답합니다.

- memory가 어디에 있는가: local, hosted, self-hosted, platform-bound 중 무엇인가?
- 처음 쓸 만한 memory를 얻기까지 얼마나 걸리는가?
- 어떤 데이터를 수집할 수 있는가?
- 원본 데이터가 자동으로 정리된 지식이 되는가?
- 통합, 회고, dream cycle을 지원하는가?
- AI 도구가 MCP, API, SDK, CLI, plugin을 통해 읽고 쓸 수 있는가?
- 개인, 프로젝트, workspace, team scope를 분리할 수 있는가?
- 사용자가 무엇을 확인, 편집, 삭제, 내보내기, 감사할 수 있는가?

일반 vector database, RAG library, note app, agent framework는 세컨드 브레인 안에서 어떤 역할을 하는지 명확히 설명할 수 있을 때만 포함합니다.

## MECE 의사결정 모델

두 의사결정 축을 분리해서 다룹니다.

- 생애주기 빈칸: 독자가 먼저 해결하려는 세컨드 브레인 단계입니다. 수집, 정리, 발전, 활용, 관리 중 어디가 막혔는지를 봅니다.
- 주 계층: 독자가 처음 채택하는 시스템 종류입니다. end-to-end app, local workspace, agent memory layer, memory substrate, platform baseline 중 하나로 봅니다.

생애주기 chooser는 "무슨 문제를 먼저 풀어야 하는가?"에 답합니다. Solution Snapshot, Solution Layers, Capability Matrix는 "어떤 종류의 시스템을 채택하고 있고, 그 계층의 트레이드오프는 무엇인가?"에 답합니다. 생애주기 행, capability page, layer grouping으로 이미 설명할 수 있는 차이를 새 제품 분류로 만들지 마세요.

하나의 시스템이 여러 영역을 걸치더라도 README와 matrix에서는 하나의 primary adoption layer를 고릅니다. secondary role은 솔루션 프로필 안에서 설명합니다. 예를 들어 connector가 있는 memory API가 수집, 정리, 활용을 지원하더라도, 사용자가 API, SDK, MCP, plugin으로 먼저 채택한다면 agent memory layer로 분류합니다.

## 기여 유형

가진 근거에 맞는 가장 작은 기여 유형을 고르세요.

- Core solution profile: 독자가 지금 평가할 수 있는 shipped, source-backed 시스템입니다.
- Capability 또는 comparison update: 특정 workflow에는 관련 있지만 full profile로 넣기에는 좁은 변경입니다.
- Setup guide: `setup-guides/` 아래에 들어가는 검증된 설정 경로입니다. retrieval, write-back, activation이 동작했는지 확인하는 방법을 포함해야 합니다.
- Example: `examples/` 아래에 들어가는 시나리오 수준 workflow입니다.
- Watchlist entry: 관리자가 추적하고 싶지만 아직 full evaluated profile은 아닌 프로젝트입니다.

거절된 core profile이 항상 watchlist가 되는 것은 아닙니다. 너무 초기 단계이거나, 범위 밖이거나, 출처가 부족하거나, license가 불명확하거나, 미래/WIP 기능에 크게 의존하거나, 독자에게 충분한 의사결정 가치를 주지 못하면 완전히 제외될 수 있습니다.

## Core Solution 기준

full solution profile을 열기 전에 아래 기준을 모두 확인하세요.

- 범위 적합성: AI second-brain, agent memory, 개인/팀 지식, context-engineering workflow를 직접 다룹니다.
- shipped surface: 핵심 주장은 오늘 사용할 수 있는 기능을 설명해야 합니다. planned feature, open issue, roadmap, WIP branch는 제한사항으로 언급할 수 있지만 core placement의 근거로 삼지 않습니다.
- 활용 경로: MCP, API, SDK, CLI, plugin, app UI, 문서화된 connector 중 하나 이상의 AI-tool access path가 오늘 동작해야 합니다.
- 생애주기 범위: Collect, Organize, Evolve, Use, Govern 중 여러 단계를 의미 있게 다뤄야 합니다. 한 축에만 강하면 core profile보다 capability page가 더 적합할 수 있습니다.
- 주 계층 적합성: secondary role이 있더라도 README와 matrix grouping에 넣을 primary layer 하나를 고를 수 있어야 합니다.
- 의사결정 가치: 기존 core entry를 덜 성숙하거나 근거가 약한 형태로 반복하는 것이 아니라, 독자에게 구분되는 선택지를 제공해야 합니다.
- 운영 명확성: deployment model, setup burden, data ownership, license/source availability, personal/team scope를 출처 기반으로 설명할 수 있어야 합니다.

## Core Profile 연결 범위

full core solution profile은 단독 페이지로만 추가하지 말고 레포의 의사결정 경로에 연결해야 합니다.

core profile에 필수인 항목:

- `solutions/<solution-name>.md`, [templates/system-profile.md](templates/system-profile.md)에서 복사
- [../README.ko.md](../README.ko.md)의 생애주기 chooser 행과 Solution Snapshot의 적절한 layer group
- [solutions/README.md](solutions/README.md)
- [comparisons/solution-layers.md](comparisons/solution-layers.md)
- [comparisons/capability-matrix.md](comparisons/capability-matrix.md)

출처로 뒷받침되고 관련 있을 때 조건부로 필요한 항목:

- chooser, setup burden, agent access, local vs cloud, personal vs team 같은 `comparisons/*` 문서
- 솔루션이 실제로 지원하는 workflow에 대한 `capabilities/*` 문서
- main curated set에 들어가는 솔루션이라면 영어 문서의 mirror

해당 의사결정 경로를 채울 만큼 근거가 충분하지 않다면 더 좁은 기여 유형을 사용하거나 아직 추가하지 마세요.

## 프로필 내용

모든 솔루션 프로필은 아래 항목에 답해야 합니다.

- 배포와 소유권 요약
- 맥락 수집 방식
- 지식 정리 방식
- 통합 또는 유지보수 방식
- 검색과 근거 제시 방식
- AI 도구 활용과 write-back surface
- workspace와 team 지원
- UI, 검토, 정정 surface
- 프라이버시, 이동성, 통제권
- 설정 부담
- 잘 맞는 사용자
- 잘 맞지 않는 사용자
- 트레이드오프
- 공식 설정 또는 평가 링크

command-by-command 설치 설명을 길게 복제하기보다 공식 설정 문서, 공식 저장소, 1차 출처를 링크합니다. 확실하지 않은 필드는 추측하지 말고 `미확인`으로 표시합니다.

## 출처와 주장

가능하면 1차 출처를 사용하세요.

- 공식 문서
- 공식 저장소
- maintainer가 작성한 예시
- 제품 문서와 changelog
- 재현 가능한 local test report

local 또는 내부 test report를 사용할 때는 명확하게 요약하고, 검증되지 않은 가정을 제품 주장처럼 쓰지 마세요.

closed-source와 hosted product도 기여 가능합니다. 기여자가 내부 모델, prompt, ranking logic, graph construction, infrastructure detail을 증명하거나 공개할 필요는 없습니다. 문서, 제품 UI, API, 저장소, 직접 테스트로 검증 가능한 공개 동작을 설명하세요. 비공개이거나 확인할 수 없는 세부사항은 `비공개` 또는 `미확인`으로 표시합니다.

### Benchmark와 주장

benchmark는 유용하지만 누가 만들었고 무엇을 측정했는지 설명해야 합니다. independent third-party validation, maintainer-published benchmark, local test report, vendor claim을 구분하세요. end-to-end answer grading, Recall@K, latency, cost처럼 서로 다른 metric을 같은 것처럼 비교하지 마세요.

보수적인 표현을 사용하세요.

- 좋음: "maintainer-published benchmark는 ...라고 보고합니다."
- 좋음: "local hands-on test에서는 ...를 확인했습니다."
- 피하기: "best", "leader", "state of the art" 같은 넓은 품질 주장. 독립 출처가 그 비교를 정확히 뒷받침할 때만 사용합니다.

### License와 Source Availability

프로젝트에 인정되는 open-source license가 있거나 공식 source에 license가 명확히 적혀 있을 때만 `Open source: Yes`를 사용하세요. 공개 저장소지만 license가 없으면 `Public repo; license not declared` 같은 표현을 사용합니다.

## 작성 스타일

- 사실 기반으로 구체적으로 씁니다.
- tutorial 문체보다 의사결정에 도움이 되는 landscape 문체를 선호합니다.
- 내장 지원, 연동 지원, 커스텀 수집기 작업을 구분합니다.
- 관찰 가능한 제품 동작과 공개되지 않은 내부 동작을 구분합니다.
- [../README.ko.md](../README.ko.md)의 표준 지원 라벨을 사용합니다.
- 추천은 해당 workflow에 맞게 범위를 좁히고, 홍보성 표현 없이 트레이드오프를 설명합니다.

## Pull Request 체크리스트

- PR 하나에는 솔루션 또는 workflow 하나만 담는 것을 권장합니다.
- 출처와 검증 메모를 포함합니다.
- 알려진 제한사항을 부드럽게 숨기지 말고 명시합니다.
- 관련 없는 formatting change는 제외합니다.
- placeholder 또는 watchlist entry라면 아직 완전히 평가된 것이 아니라는 점을 명확히 표시합니다.
- review를 요청하기 전에 `main`과의 conflict를 해결합니다.
- 미래 또는 WIP 기능에 기대어 core placement를 정하지 않습니다.

## 라이선스 동의

기여하면 해당 기여가 이 프로젝트와 동일하게 Apache License 2.0으로 라이선스되는 데 동의하는 것입니다.
