# 개발 작업 프로세스

> 프로젝트 기획부터 구현 결과 측정과 설계 개선까지 이어지는 기본 작업 흐름과 역할을 정의한다.

---

## 1. 기본 작업 프로세스

### 1. Project Planning · 프로젝트 기획

- Problem
- Requirement
- Constraint

### 2. Use Case Scenario · 유즈케이스 시나리오

> 상황에 따라 Detailed Specification에 편입할 수 있다.

### 3. Detailed Specification · 상세 명세

- Actor
- Trigger
- Precondition
- Main Flow
- Alternative / Exception Flow
- Postcondition
- Business / Data Rules
- Acceptance Criteria (필요 시)

### 4. Domain Model · 도메인 개념 모델

### 5. Invariant · 불변 조건

> 도메인 문서에 통합하여 작성한다.

### 6. Dynamic Design · 동적 설계

- Sequence Diagram
- State Diagram

### 7. Responsibility Assignment · 책임 할당

> 도메인 문서에 통합하여 작성한다.

### 8. Design Class Diagram · 설계 클래스 다이어그램

### 9. Test Design · 테스트 설계

### 10. Task Decomposition · 작업 분해

> 마일스톤 문서에 작성한다.

### 11. AI Implementation · AI 구현

> 프로젝트 브랜치 하나에서 마일스톤을 순서대로 구현한다. 기능별 브랜치와 병렬 구현은 사용하지 않는다.

### 12. Verification · 검증

> 각 단계는 앞 단계와 다른 새 세션에서 실행한다.

1. 마일스톤 리뷰: 리뷰어는 코드를 고치지 않고 지적만 남긴다. (`/milestone-review <ID>`)
2. 리뷰 수정: 별도 세션이 수정 대상과 사용자가 고른 결정 항목을 고친다. (`/review-fix <ID> [선택 항목]`)
3. 재리뷰: 수정 커밋만 1회 리뷰한다. 남은 지적은 반복 수정하지 않고 사용자가 처리 방식을 정한다. (`/milestone-review <ID> 재리뷰`)
4. 사람 기능 테스트: 사람이 실제 기능을 시험한다. (`/human-test-plan <ID>`) 나온 수정은 새 세션에서 고쳐 `FIX: <ID> 사람 테스트 수정`으로 커밋하고, 수정 묶음마다 재리뷰를 1회 한다.
5. E2E 테스트: 모든 기능 마일스톤이 끝난 뒤 프로젝트 브랜치에서 수행한다. (`/human-test-plan E2E`) 나온 수정은 4번과 같이 처리하되, 재리뷰에는 수정 커밋 범위를 지정한다.

### 13. Measurement · 측정

### 14. Architecture / Design Revision · 아키텍처·설계 수정

> 아키텍처 문서는 프로젝트 전반에 걸쳐 지속적으로 작성하고 갱신한다.

---

## 2. 작업자의 역할

### 2.1 문제와 요구사항 정의

- Problem (문제 정의)
- Requirement (요구사항)
- Constraint (제약사항)
- Detailed Specification (상세 명세 작성)

### 2.2 설계와 작업 계획

- Architecture (아키텍처 설계)
- Invariant (불변 조건)
- Acceptance Criteria (인수 조건 / 완료 기준)
- Task Decomposition (작업 분할)

### 2.3 구현 지원과 결과 평가

- AI Agent (AI 에이전트 사용)
- Verification (검증)
- Measurement (측정)
- Architecture Revision (아키텍처 개선 / 수정)

---

## 3. AI의 역할

- Implementation (구현)
- Test Generation (테스트 생성)
- Documentation (문서화)
- Refactoring (리팩터링)
- Boilerplate (반복적 기본 코드 작성)
- Code Exploration (코드 탐색 / 코드베이스 분석)
- Alternative Proposals (대안 제시)
