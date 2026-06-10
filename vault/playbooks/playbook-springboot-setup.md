---
id: playbook-springboot-setup
title: "스프링부트 프로젝트 표준 세팅"
type: playbook
namespace: personal
visibility: public
summary: "장희성 표준 스프링부트 세팅: yaml, 최신 안정 버전, JDK 25+, com/back, Gradle KTS, 필수 의존성, 시큐리티 전체 허용 + H2 콘솔 + CSRF 비활성, REST 선호."
auto_inject: false
applicable_when: "새 스프링부트 프로젝트 생성 또는 세팅 관련 강의/작업"
confidence: 1.0
verified_at: "06/11/2026"
verified_by: "장희성 (본인 진술)"
staleness_signal: "JDK/스프링부트 메이저 버전 정책이 바뀌거나 본인이 표준을 변경하면 갱신"
tags: ["spring-boot", "setup", "gradle-kts", "jdk25", "security", "h2", "rest"]
edges: [
  {"target": "contact-jang-heeseong", "type": "authored_by", "weight": 1.0, "note": "본인의 강의·개발 표준"}
]
related: ["[[playbook-springboot-test-strategy]]", "[[pattern-sql-logging-binding-extract]]"]
source_url: "Empty"
---

# 스프링부트 프로젝트 표준 세팅

## 프로젝트 생성

| 항목 | 표준 |
|---|---|
| 설정 파일 | **yaml** 방식 (`application.yml`) |
| 스프링부트 버전 | **최신 안정 버전** |
| JDK | **25 이상** |
| Group | `com` |
| Artifact | `back` |
| 빌드 | **Gradle KTS** (`build.gradle.kts`) |

## 필수 의존성

- Spring Web
- Spring Security
- H2 Database
- Spring Data JPA
- DevTools
- Lombok (자바 프로젝트인 경우; 자바+스프링 = "자프링")

## 시큐리티·H2 기본 설정

- 시큐리티는 **모든 요청 허용** (permitAll)
- **H2 콘솔이 반드시 작동**해야 함 (frameOptions 허용 포함)
- **CSRF 전부 비활성화**

## 아키텍처 성향

- 타임리프(서버 사이드 템플릿)보다 **REST API 방식 선호**

프로필 구성과 테스트 전략은 [[playbook-springboot-test-strategy]], SQL 로깅은 [[pattern-sql-logging-binding-extract]] 참조.
