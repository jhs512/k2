# Knowledge Graph Vault — Master Index

> **Entry point for AI agents.** This index lists every node in the vault, grouped by type, with summary and edge count for rapid scanning.

---

## pillar

| ID | Summary | Edges |
|---|---|---|
| `pillar-personal-foundation` | The founding principle that deliberate, recorded decisions outperform ad-hoc reactions over time. | 1 |
| `pillar-jhs-causality` | 장희성의 핵심 신념. 인과율을 믿어 뿌린 대로 거둔다고 본다. 돈 버는 것을 좋아하지만 인색하지 않은 태도의 근거. | 2 |

---

## decision

| ID | Summary | Edges |
|---|---|---|
| `decision-personal-first` | When facing ambiguous problems with time pressure, default to reversible actions over reversible inactions. | 1 |

---

## concept

*No nodes created yet.*

---

## question

*No nodes created yet.*

---

## playbook

| ID | Summary | Edges |
|---|---|---|
| `playbook-springboot-setup` | 장희성 표준 스프링부트 세팅: yaml, 최신 안정 버전, JDK 25+, com/back, Gradle KTS, 필수 의존성, 시큐리티 전체 허용 + H2 콘솔 + CSRF 비활성, REST 선호. | 1 |
| `playbook-springboot-test-strategy` | dev 프로필은 H2 파일모드, test 프로필은 H2 메모리모드. 테스트는 메모리 DB에 실제 HTTP 콜을 날린 뒤 트랜잭션 롤백으로 초기화하는 방식. | 2 |

---

## task

*No nodes created yet.*

---

## event

*No nodes created yet.*

---

## pattern

| ID | Summary | Edges |
|---|---|---|
| `pattern-sql-logging-binding-extract` | 모든 SQL은 포맷팅된 형태로 자세히 출력하고, 파라미터 binding과 결과 extract 로그까지 모두 보이게 설정하는 것을 선호. | 2 |

---

## hypothesis

*No nodes created yet.*

---

## fact

| ID | Summary | Edges |
|---|---|---|
| `fact-jhs-preferences` | 풋살과 한식을 좋아하고 대중문화에는 관심이 없다. 잡담·추천·예시 선정 시 참고할 취향 프로필. | 1 |

---

## source

*No nodes created yet.*

---

## bookmark

*No nodes created yet.*

---

## note

*No nodes created yet.*

---

## contact

| ID | Summary | Edges |
|---|---|---|
| `contact-jang-heeseong` | 1986년생 한국 남성, IT 강사. 스프링부트 강의가 주력. 이 vault의 주인. | 3 |

---

## reference

*No nodes created yet.*

---

## custom

*No nodes created yet.*

---

## log

> Log nodes are not indexed here. They live in `logs/` and are self-contained. To review recent operations, scan `logs/` directly.

---

## Adding New Nodes

When you create a new node:

1. Add a frontmatter block with all required fields per `_system/FRONTMATTER-SCHEMA.md`.
2. Assign a unique `id` in `type-slug` format.
3. Populate `edges` with at least one relationship to another node.
4. Update this index by inserting a row into the appropriate table.
5. Use `related` for informal wikilinks that don't need a formal edge.
6. `log` nodes are never added to this index — they are self-contained in `logs/`.

---

*Last updated: 06/11/2026 — 장희성 프로필·신념·취향 + 스프링부트 표준(세팅/테스트/SQL로깅) 6개 노드 추가*
