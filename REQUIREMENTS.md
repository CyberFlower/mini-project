# Requirements

## 0. 용어

| 용어 | 뜻 |
| --- | --- |
| 의도 부채 | 바뀐 코드의 이유가 기록된 출처에 없거나, 기록된 의도와 실제 동작이 다른 상태 |
| 구현 부채 | 의도는 정해졌지만 구현이 빠졌거나, 그 동작을 확인하는 테스트·검증 기록이 없는 상태 |

## 1. Goal & Scope

- 목표: 작은 toy project에서 개발 원칙과 요구사항·구조·검증 기록을 일관되게 유지하고, AI가 만든 커밋을 사람이 설명할 수 있는지 점검하는 재사용 가능한 Codex 스킬을 제공한다.
- 포함 범위: 개발 지침 반영, 요구사항 개요·세부 문서, 구조 문서, Feature별 구현 문서와 템플릿, 커밋별 의도 부채·구현 부채 보고, 설치·사용 안내.
- 제외 범위: 제품 기능이나 기술 스택의 임의 추가, 별도 실행 스크립트와 런타임 의존성 도입.

## 2. Functional Requirements

### FR-01: 개발 지침 적용

Feature: `skill-bootstrap`

기존 개발 원칙을 유지하되 합의한 문서 체계에 필요한 부분만 조정한다. 기존 프로젝트 지침은 보존하면서 누락된 내용만 보완하고 중복 삽입하지 않는다. 지침 파일이 없으면 `AGENTS.md`를 생성한다.

#### Acceptance Criteria

- 스킬 본문에 개발 원칙과 기존 지침 보완에 관한 문단이 포함된다.
- 스킬의 개발 원칙과 직접 복사용 지침 자산, 이 저장소의 `AGENTS.md`가 일치한다.

### FR-02: 요구사항 개요와 세부 문서

Feature: `feature-documentation`

프로젝트 루트의 `REQUIREMENTS.md`에 요구사항 개요를 두고, 긴 요구사항의 세부는 `requirements/<ID>.md`에 둔다. [세부](requirements/FR-02.md)

### FR-03: Feature 정제와 구조·구현 문서

Feature: `feature-documentation`

구조와 그 선택 이유는 루트 `ARCHITECTURE.md`에, Feature의 진행 상태와 검증 결과는 Feature별 `IMPLEMENTATION.md`에 둔다. [세부](requirements/FR-03.md)

### FR-04: 간결한 지침과 필요한 문서 조회

Feature: `feature-documentation`

`AGENTS.md`에는 개발 원칙과 문서 위치·조회 규칙만 두고, 형식과 세부 내용은 각 문서에서 관리한다.

#### Acceptance Criteria

- 문서별 템플릿이 제공되며 `AGENTS.md`에 상세 형식이 복사되지 않는다.
- 작업 시 요구사항 개요와 관련 세부 파일, 현재 Feature 문서를 읽고, 구조를 바꾸면 `ARCHITECTURE.md`도 읽으며, 다른 Feature 문서는 관련이 있을 때만 조회하도록 안내한다.

### FR-05: 재사용 가능한 배포 패키지

Feature: `skill-bootstrap`

스킬 폴더만 복사해 재사용할 수 있도록 메타데이터·자산·설치 및 사용 안내를 제공한다. [세부](requirements/FR-05.md)

### FR-06: 커밋 목록과 하나씩 확인

Feature: `commit-review`

커밋 목록을 사용자가 정한 순서로 보여주고, 한 번에 한 커밋만 보고한다.

#### Acceptance Criteria

- 점검 대상은 커밋으로 한정하고, 커밋되지 않은 변경은 보지 않는다.
- 사용자가 범위(revision 범위나 개수)를 주지 않으면 현재 브랜치 HEAD에서 닿는 전체 커밋을 대상으로 한다. merge 커밋은 목록에서 뺀다.
- 순서는 오래된 순 또는 최신순이며, 사용자가 정하지 않으면 시작 전에 묻는다.
- 정한 순서로 번호·짧은 해시·제목 목록을 보여준 뒤 첫 커밋 하나만 보고한다.
- 사용자가 다음·이전·번호·해시로 고를 때까지 다른 커밋을 보고하지 않는다.

### FR-07: 커밋별 의도 부채·구현 부채 보고

Feature: `commit-review`

커밋마다 출처가 붙은 의도, 실제 코드 기준의 핵심 변경, 테스트 시나리오를 보고해 의도 부채와 구현 부채를 드러낸다. [세부](requirements/FR-07.md)

## 3. Non-functional Requirements

- NFR-01: 스킬 실행에 git 외의 별도 프로그램이나 런타임 의존성을 요구하지 않는다.
- NFR-02: 문서는 간결하게 유지하고, 결정의 이유와 실제 검증 결과를 기록하며 코드에서 쉽게 확인할 수 있는 세부 사항을 반복하지 않는다.

## 4. Constraints

- 지침 파일과 스킬 진입점은 `AGENTS.md`, `SKILL.md` 이름을 사용한다.
- 커밋과 push는 사용자 사전 승인 후 수행한다.
