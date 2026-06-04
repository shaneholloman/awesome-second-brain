# Honcho

## Snapshot

- 웹사이트 / 문서: https://honcho.dev/docs/v3/documentation/introduction/overview
- 회사 / 관리자: Plastic Labs
- 상태: managed와 self-hosted 배포 경로가 있는 open-source project
- 오픈소스: 예, AGPL-3.0 라이선스 repository
- 배포: Managed Honcho service, local/self-hosted FastAPI server, SDK integration, MCP server
- 주요 사용자: persistent memory와 user modeling이 필요한 stateful agent를 만드는 개발자
- 세컨드 브레인 역할: Stateful agent memory와 user-modeling 계층
- 마지막 검토: 2026-06-04

## 한 줄 요약

Honcho는 message를 저장하고 peer history를 reasoning한 뒤, context, search, representation, conclusion, SDK, MCP tool을 stateful agent에 제공하는 agent memory library이자 managed service입니다.

## 세컨드 브레인 적합성

Honcho는 소비자용 note workspace라기보다 agent나 application 안에 세컨드 브레인을 넣어야 할 때 가장 잘 맞습니다. 사용자, agent, group, project, idea 같은 entity에 대한 상태를 시간이 지나도 유지해야 하는 builder에게 관련성이 높습니다.

자가 발전형 세컨드 브레인 관점에서 Honcho는 message/session 저장, peer representation, background reasoning, search, context retrieval, MCP/API/SDK access를 통해 수집, 정리, 발전, 활용 단계를 다룹니다. governance, 최종 사용자 검토 UI, connector 범위, 사람이 직접 다루는 지식 workflow는 Honcho 위에 만드는 제품이나 agent experience에 달려 있습니다.

## 기능

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Managed service와 self-hosted FastAPI server 경로가 문서화되어 있으며, core repository는 AGPL-3.0입니다. |
| 맥락 수집 | API/SDK/MCP write로 message, session, uploaded document를 추가합니다. 더 넓은 source capture는 통합하는 app 또는 agent에 달려 있습니다. |
| 지식 정리 | workspace, peer, session, message, conclusion, representation, peer card, session context 중심 모델입니다. |
| Memory 발전 | background processing이 message를 reasoning해 peer representation/conclusion을 업데이트하며, MCP에는 `schedule_dream`이 노출됩니다. |
| 검색 / 활용 | search, get context, peer/session representation, peer card, conclusion, chat-style context query가 문서화되어 있습니다. |
| 에이전트 활용 / 쓰기 반영 | MCP, Python/TypeScript SDK, API, Claude Code, OpenCode, OpenClaw, Hermes, MCP 호환 client 연동이 문서화되어 있습니다. |
| 개인 / 팀 범위 | workspace는 application/environment를 격리하고, peer와 session은 user, agent, group 등 entity를 모델링할 수 있습니다. |
| 검토 / 정정 | 개발자용 inspection과 conclusion 도구는 있지만, polished end-user correction workflow는 통합 구현에 달려 있습니다. |
| 프라이버시 / 통제권 | self-hosting이 가능하지만 service, model provider key, storage, update 운영은 사용자가 맡아야 합니다. |
| 설정 / 운영 | hosted MCP 설정은 agent client 기준 빠르지만, self-hosting과 production integration은 backend 운영과 memory 설계가 필요합니다. |

## 강점

- workspace, peer, session, message, conclusion, representation이라는 stateful agent용 primitive가 명확합니다.
- MCP 지원으로 일반 agent client에서 사용할 수 있습니다.
- Python과 TypeScript SDK가 application integration을 지원합니다.
- managed service보다 더 많은 통제가 필요할 때 self-hosting 경로가 있습니다.
- Hermes와 OpenClaw 통합이 있어 이 레포에서 추적하는 agent-memory workflow와 관련성이 높습니다.

## 한계

- 완성된 소비자용 세컨드 브레인 제품이라기보다 agent/application memory infrastructure입니다.
- 최종 사용자 UI, source connector, permission workflow, review/correction flow는 통합하는 제품에 달려 있습니다.
- self-hosted 사용은 service, provider key, storage, update 운영 부담을 추가합니다.
- benchmark position이나 social intelligence 같은 vendor claim은 이 프로필의 평가 근거로 다루지 않았습니다.

## 잘 맞는 경우

- cross-session state가 필요한 agent를 만드는 개발자.
- application memory 일부로 user 또는 agent modeling이 필요한 제품.
- hosted 또는 self-hosted 선택지가 있는 MCP-accessible memory를 원하는 agent workflow.
- 사용자와 agent가 별도 persistent representation을 가져야 하는 multi-agent system.

## 잘 맞지 않는 경우

- 노트, 자료, 수동 지식 관리용 ready-made second-brain dashboard를 원하는 사용자.
- app-specific ingestion을 직접 만들지 않고 넓은 SaaS connector를 바로 원한다면.
- API-managed representation보다 local Markdown inspection이 더 중요한 workflow.

## 트레이드오프

Honcho는 builder에게 agent용 state layer를 제공하지만, 사용자 경험은 그 위에 붙는 application이나 agent가 결정합니다. 완성형 세컨드 브레인 앱이 아니라 programmable memory가 필요할 때 Mem0/OpenMemory, Hindsight, Supermemory, Hyperspell, Zep/Graphiti, Cognee와 비교하는 것이 적절합니다.

## 공식 설정 / 평가 링크

- 문서: https://honcho.dev/docs/v3/documentation/introduction/overview
- Repository: https://github.com/plastic-labs/honcho
- MCP integration: https://honcho.dev/docs/v3/guides/integrations/mcp
- Hermes integration: https://honcho.dev/docs/v3/guides/integrations/hermes
- API reference: https://honcho.dev/docs/v3/api-reference/introduction

## 출처

- https://honcho.dev/docs/v3/documentation/introduction/overview
- https://github.com/plastic-labs/honcho
- https://honcho.dev/docs/v3/guides/integrations/mcp
- https://honcho.dev/docs/v3/guides/integrations/hermes
