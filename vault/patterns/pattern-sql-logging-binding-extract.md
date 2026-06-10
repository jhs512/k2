---
id: pattern-sql-logging-binding-extract
title: "SQL 상세 로깅 — 예쁜 출력 + binding/extract까지"
type: pattern
namespace: personal
visibility: public
summary: "모든 SQL은 포맷팅된 형태로 자세히 출력하고, 파라미터 binding과 결과 extract 로그까지 모두 보이게 설정하는 것을 선호."
auto_inject: false
applicable_when: "스프링부트 + JPA/Hibernate 프로젝트의 로깅 설정"
confidence: 1.0
verified_at: "06/11/2026"
verified_by: "장희성 (본인 진술)"
staleness_signal: "Hibernate 메이저 버전 변경으로 로거 이름이 바뀌면 설정 예시 갱신"
tags: ["spring-boot", "jpa", "hibernate", "sql-logging", "binding", "extract"]
edges: [
  {"target": "playbook-springboot-setup", "type": "part_of", "weight": 0.9, "note": "표준 세팅의 로깅 영역 세부 규칙"},
  {"target": "playbook-springboot-test-strategy", "type": "supports", "weight": 0.7, "note": "테스트 시 실제 발생 SQL을 검증하는 데 필수"}
]
related: ["[[playbook-springboot-setup]]", "[[playbook-springboot-test-strategy]]"]
source_url: "Empty"
---

# SQL 상세 로깅 — 예쁜 출력 + binding/extract까지

모든 SQL은 **자세히, 예쁘게(포맷팅·하이라이팅)** 출력하고, 물음표(?)로 가려지는 **파라미터 binding 값**과 조회 결과의 **extract 값까지** 전부 로그로 확인하는 것을 선호한다.

## Hibernate 6 기준 yaml 설정

```yaml
spring:
  jpa:
    properties:
      hibernate:
        format_sql: true
        highlight_sql: true
        use_sql_comments: true

logging:
  level:
    org.hibernate.SQL: DEBUG
    org.hibernate.orm.jdbc.bind: TRACE
    org.hibernate.orm.jdbc.extract: TRACE
```

- `org.hibernate.SQL: DEBUG` — 실행 SQL 출력
- `format_sql` + `highlight_sql` — 줄바꿈·색상으로 예쁘게
- `org.hibernate.orm.jdbc.bind: TRACE` — 바인딩 파라미터 값 출력
- `org.hibernate.orm.jdbc.extract: TRACE` — 결과 컬럼 추출 값 출력

dev·test 프로필 모두에 적용한다 ([[playbook-springboot-test-strategy]]).
