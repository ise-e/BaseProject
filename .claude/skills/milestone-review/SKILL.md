---
name: milestone-review
description: 마일스톤 구현이나 리뷰 수정을 reviewer 서브에이전트로 읽기 전용 리뷰하고 보고서를 남긴다.
argument-hint: "<마일스톤 ID> [재리뷰] [base..head]"
disable-model-invocation: true
---

# 마일스톤 리뷰

인자: `$ARGUMENTS`

코드를 고치지 않는다. 수정은 새 세션의 `/review-fix`가 맡는다.

## 절차

1. 이 세션에서 대상 코드를 구현했거나 수정했다면 멈추고 새 세션에서 실행하도록 안내한다.
2. 리뷰 범위를 정한다.
   - 첫 리뷰: `git log --reverse --format=%H --grep="^<ID>:"`의 첫 커밋의 부모부터 `HEAD`까지
   - 재리뷰: `.local/reviews/`에서 가장 최근 `<ID>` 보고서의 `리뷰 완료 커밋`부터 `HEAD`까지
   - 인자에 `<base>..<head>` 범위가 있으면 그 범위를 쓴다.
   - 재리뷰는 수정 묶음마다 1회만 한다. 범위에 커밋이 없으면 멈추고 그 이유를 알린다.
3. `git status --short` 결과를 기록한다.
4. `reviewer` 서브에이전트에 코드 리뷰 기준으로 리뷰를 요청한다. 범위, `Docs/Milestone/`의 해당 마일스톤 문서, 테스트 명령만 전달한다. 구현 세션의 설명이나 요약은 전달하지 않는다.
5. 리뷰 뒤 `git status --short`를 다시 확인한다. 달라졌으면 보고서와 사용자 보고에 적는다.
6. 리뷰 결과를 저장한다. 첫 리뷰는 `.local/reviews/<ID>-review.md`, 재리뷰는 `.local/reviews/<ID>-recheck-<N>.md`이다. `N`은 1부터 늘린다. 머리에 다음을 적는다.
   - 대상 범위: `<base>..<head>`
   - 리뷰 완료 커밋: `<head>`의 전체 해시
7. 사용자에게 보고한다.
   - 첫 리뷰: 결정 필요 항목을 번호로 보여주고, 다음 단계로 새 세션의 `/review-fix <ID> [1-a 2-b]`를 안내한다.
   - 재리뷰: 남은 지적을 보고한다. 수정과 리뷰를 더 반복하지 않고 사용자가 처리 방식을 정한다.
