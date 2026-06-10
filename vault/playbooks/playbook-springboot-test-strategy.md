---
id: playbook-springboot-test-strategy
title: "스프링부트 프로필 구성과 테스트 전략"
type: playbook
namespace: personal
visibility: public
summary: "dev 프로필은 H2 파일모드, test 프로필은 H2 메모리모드. 테스트는 메모리 DB에 실제 HTTP 콜을 날린 뒤 트랜잭션 롤백으로 초기화하는 방식."
auto_inject: false
applicable_when: "스프링부트 프로필 설정, 테스트 코드 작성·강의"
confidence: 1.0
verified_at: "06/11/2026"
verified_by: "장희성 (본인 진술)"
staleness_signal: "본인이 테스트 전략(롤백 방식 등)을 변경하면 갱신"
tags: ["spring-boot", "testing", "h2", "profiles", "transaction-rollback", "mockmvc"]
edges: [
  {"target": "playbook-springboot-setup", "type": "part_of", "weight": 0.9, "note": "표준 세팅의 프로필·테스트 영역 세부 규칙"},
  {"target": "contact-jang-heeseong", "type": "authored_by", "weight": 1.0, "note": "본인의 강의·개발 표준"}
]
related: ["[[playbook-springboot-setup]]", "[[pattern-sql-logging-binding-extract]]"]
source_url: "Empty"
---

# 스프링부트 프로필 구성과 테스트 전략

## 프로필별 H2 모드

| 프로필 | 파일 | H2 모드 |
|---|---|---|
| 개발 | `application-dev.yml` | **파일 모드** (재시작해도 데이터 유지) |
| 테스트 | `application-test.yml` | **메모리 모드** (빠르고 격리됨) |

## 테스트 방식

1. 테스트는 **메모리 DB**(test 프로필) 위에서 실행한다.
2. 단순 단위 테스트가 아니라 **실제 HTTP 콜 요청을 날리는 방식**을 선호한다 (MockMvc 등 통합 테스트 스타일).
3. 각 테스트 후 **트랜잭션 롤백으로 DB를 초기화**한다 (`@Transactional` 기반).

이 조합으로 테스트 간 격리가 보장되면서도 실제 요청-응답 흐름을 검증할 수 있다. 테스트 중 SQL 확인은 [[pattern-sql-logging-binding-extract]] 설정과 함께 사용한다.
