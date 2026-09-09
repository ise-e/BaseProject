1. 기존 아키텍처를 준수한다.
   - 승인 없이 아키텍처를 변경하지 않는다.
   - 구조적 모순, 개선 가능성, 예외 적용 필요성을 발견하면 수정 전에 먼저 브리핑한다.

2. 승인 없이 새로운 dependency 또는 package를 추가하지 않는다.

3. 요청과 직접 관련된 코드만 수정한다.
   - 인접 코드의 불필요한 formatting 또는 기존 정상 코드의 임의 refactoring을 하지 않는다.
   - 범위 밖 문제를 발견하면 직접 수정하지 말고 먼저 브리핑한다.

4. 코드 변경 후 관련 테스트를 실행한다.
   - 테스트를 실행할 수 없거나 실패한 경우 그 이유와 결과를 보고한다.

5. 설명, 주석, 보고 및 사용자 대상 정보 전달은 한국어를 사용한다.
   - 코드의 identifier, API 이름, 기술 용어는 필요한 경우 원문 영어를 유지한다.

6. 요구사항이나 설계가 불명확하거나 문서 간 충돌이 있는 경우 임의로 결정하지 않는다.
   - 구현에 영향을 주는 판단이 필요한 경우 먼저 브리핑하고 확인을 받는다.


프로젝트 관련 판단은 다음 문서를 우선한다.

- 개발 프로세스: `Docs/workflow.md`
- 문제 정의, 요구사항, 제약사항: `Docs/Planning/plan.md`
- Use Case / 상세 명세: `Docs/Planning/Detailed_Specification/`
- 상위 아키텍처: `Docs/Design/Architecture/`
- Domain Model / Domain Invariant / Domain Responsibility:
  `Docs/Design/Domain/`
- 동적/정적 설계 다이어그램: `Docs/Design/Diagram/`
- Milestone / Task 범위: `Docs/Milestone/`

코드와 문서가 충돌하거나 문서 간 모순이 있는 경우 임의로 해결하지 말고 먼저 보고한다.