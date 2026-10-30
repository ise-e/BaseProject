---
name: design-review
description: 구현 전에 기획, 상세 명세, 도메인, 설계, 테스트 설계, 마일스톤 문서의 추적성과 모순을 읽기 전용으로 리뷰한다.
argument-hint: "[리뷰할 문서 또는 범위]"
disable-model-invocation: true
---

# 설계 리뷰

인자: `$ARGUMENTS`

문서를 고치지 않는다. 인자가 없으면 `CLAUDE.md`의 Source of Truth 문서 전체를 대상으로 한다.

## 절차

1. 이 세션에서 대상 문서를 작성했다면 멈추고 새 세션에서 실행하도록 안내한다.
2. `reviewer` 서브에이전트에 문서 리뷰 기준으로 리뷰를 요청한다. 대상 범위만 전달하고, 작성 세션의 설명이나 요약은 전달하지 않는다.
3. 결과를 `.local/reviews/design-review.md`에 저장한다.
4. 사용자에게 결정 필요 항목을 먼저 보고한다.
