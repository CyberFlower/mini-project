# Requirements

## 1. Goal & Scope

- 목표: 작은 toy project에서 개발 원칙과 요구사항·설계·검증 기록을 일관되게 유지하는 재사용 가능한 Codex 스킬을 제공한다.
- 포함 범위: 개발 지침 반영, 단일 요구사항 문서, Feature별 설계·구현 문서와 템플릿, 설치·사용 안내.
- 제외 범위: 제품 기능이나 기술 스택의 임의 추가, 별도 실행 스크립트와 런타임 의존성 도입.

## 2. Functional Requirements

### FR-01: 개발 지침 적용

Feature: `skill-bootstrap`

기존 개발 원칙을 유지하되 합의한 문서 체계에 필요한 부분만 조정한다. 기존 프로젝트 지침은 보존하면서 누락된 내용만 보완하고 중복 삽입하지 않는다. 지침 파일이 없으면 `AGENTS.md`를 생성한다.

#### Acceptance Criteria

- 스킬 본문에 개발 원칙과 기존 지침 보완에 관한 문단이 포함된다.
- 스킬의 개발 원칙과 직접 복사용 지침 자산, 이 저장소의 `AGENTS.md`가 일치한다.

### FR-02: 단일 요구사항 문서와 고정 형식

Feature: `feature-documentation`

프로젝트 루트의 `REQUIREMENTS.md` 하나에 요구사항을 유지한다. 확정된 요구사항과 가정을 구분하고, 중요한 모호함은 관련 구현 전에 확인한다.

#### Acceptance Criteria

- `1. Goal & Scope`, `2. Functional Requirements`, `3. Non-functional Requirements`, `4. Constraints` 순서를 유지한다.
- 기능 요구사항에 고유 ID와 개별 `Acceptance Criteria`가 있다.
- 미확정 사항이 있을 때만 `Open Questions`를 추가하고, 해결하면 해당 본문에 반영한다.
- 필요한 비기능 요구사항이나 제약이 없으면 억지로 추가하지 않고 현재 없음을 표시한다.
- 배포용 요구사항 템플릿 외에 프로젝트 요구사항 원본을 여러 파일로 나누지 않는다.

### FR-03: 요구사항에서 Feature별 문서로 연결

Feature: `feature-documentation`

하나의 사용자 목적을 완성하고 검증할 수 있는 요구사항들을 Feature로 묶는다. 다음에 구현할 Feature부터 정제하고 해당 문서를 생성한다.

#### Acceptance Criteria

- Feature별로 `docs/features/<feature>/DESIGN.md`와 `IMPLEMENTATION.md`를 유지한다.
- 설계에는 관련 요구사항 ID, 구현 방식과 선택 이유가 있다.
- 구현 기록에는 관련 요구사항 ID, 구현 순서·상태와 실제 검증 결과가 있다.
- 요구사항 전문과 Acceptance Criteria 정의는 복사하지 않고 루트 원본을 참조한다.
- 기존 설계·구현 기록은 새 위치로 이동하면서 보존하고 링크를 갱신한다.
- 아직 결정되지 않은 Feature의 빈 문서를 미리 만들지 않는다.

### FR-04: 간결한 지침과 필요한 문서 조회

Feature: `feature-documentation`

`AGENTS.md`에는 개발 원칙과 문서 위치·조회 규칙만 두고, 형식과 세부 내용은 각 문서에서 관리한다.

#### Acceptance Criteria

- 문서별 템플릿이 제공되며 `AGENTS.md`에 상세 형식이 복사되지 않는다.
- 작업 시 단일 요구사항 원본과 현재 Feature 문서를 읽고, 다른 Feature 문서는 관련이 있을 때만 조회하도록 안내한다.

### FR-05: 재사용 가능한 배포 패키지

Feature: `skill-bootstrap`

스킬 폴더만 복사해 재사용할 수 있도록 메타데이터·자산·설치 및 사용 안내를 제공한다.

#### Acceptance Criteria

- 스킬 메타데이터가 유효하고 내부 참조가 스킬 폴더 안에서 해결된다.
- README의 설치 안내와 예시가 현재 문서 체계에 맞는다.
- 공개 배포 대상은 `https://github.com/CyberFlower/mini-project.git`이다.
- 이 저장소의 `/docs/`는 로컬 개발 기록으로 유지하고 Git에서 제외한다. 스킬과 템플릿은 배포 대상에 포함한다.

## 3. Non-functional Requirements

- NFR-01: 스킬 실행에 별도 프로그램이나 런타임 의존성을 요구하지 않는다.
- NFR-02: 문서는 간결하게 유지하고, 결정의 이유와 실제 검증 결과를 기록하며 코드에서 쉽게 확인할 수 있는 세부 사항을 반복하지 않는다.

## 4. Constraints

- 지침 파일과 스킬 진입점은 `AGENTS.md`, `SKILL.md` 이름을 사용한다.
- 이번 변경의 커밋과 `main` 브랜치 push는 사용자 승인을 받았다.
