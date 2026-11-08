---
name: toy-project-init
description: 작은 toy project의 개발 지침, REQUIREMENTS.md와 ARCHITECTURE.md를 준비하고, 요구사항에서 도출한 Feature별 IMPLEMENTATION.md를 작성하거나 정리한다. 프로젝트 시작 또는 같은 문서 흐름으로 개발을 이어갈 때 사용한다.
---

# Development Guidelines

## 1. Requirements
- 모든 필수 요구사항을 충족한다.
- 명시되지 않은 기능은 추가 요청 없이 구현하지 않는다.
- 필수 기능의 구현과 검증에 필요한 최소한의 보조 코드는 허용한다.
- 확정된 요구사항과 가정을 구분하고, 중요한 모호함은 구현 전에 확인한다.

## 2. Documentation
- 문서는 간결하고 명확하게 작성한다.
- 규칙의 선택 이유는 해당 요구사항의 근거에, 구조의 선택 이유는 `ARCHITECTURE.md`에 기록한다.
- 코드에서 쉽게 확인할 수 있는 세부 구현 내용은 반복하지 않는다.
- 요구사항은 프로젝트 루트의 `REQUIREMENTS.md`(개요)와 `requirements/<ID>.md`(세부)에서 관리한다. 모든 규칙은 ID가 있는 요구사항 안에 두고, 짧은 요구사항은 세부 파일 없이 개요에 둔다.
- 구성 요소와 흐름은 루트 `ARCHITECTURE.md`, Feature별 진행 상태와 검증 결과는 `docs/features/<feature>/IMPLEMENTATION.md`에서 관리한다.
- 작업 시 `REQUIREMENTS.md`와 관련 세부 파일, 현재 Feature 문서를 읽는다. 구조를 바꾸면 `ARCHITECTURE.md`도 읽고, 다른 Feature 문서는 관련이 있을 때만 조회한다.
- 다이어그램은 표와 글만으로 이해하기 어려울 때 Mermaid로 적극적으로 사용하고, 같은 규칙을 글·표·그림으로 중복하지 않는다. 규칙 그림은 요구사항 세부 파일에, 구조 그림은 `ARCHITECTURE.md`에 둔다.
- `REQUIREMENTS.md` 0절 용어에는 도메인 전문 용어와 프로젝트에서 정한 뜻으로 쓰는 말만 두고, 낱말만으로 뜻이 자명한 일반 용어는 넣지 않는다. 뜻만 간결하게 쓰고 규칙은 본문에 두며, 본문은 0절의 용어를 그대로 쓴다.
- 문서 형식과 세부 사항은 각 문서에서 관리하며 불필요한 중복을 피한다.

## 3. Implementation
- 요구사항을 만족하는 가장 단순한 아키텍처를 우선한다.
- 불필요한 추상화, 의존성, 기능 확장을 피한다.
- 동작 가능한 최소 버전을 우선 구현하고 단계적으로 완성한다.

## 4. Verification
- 주요 기능 구현 후 실제 실행 및 관련 테스트를 수행한다.
- 테스트 결과와 발견된 문제를 해당 Feature의 `IMPLEMENTATION.md`에 간결하게 기록한다.
- 실행하지 않은 테스트를 성공했다고 보고하지 않는다.

프로젝트의 AGENTS.md 등 기존 지침 파일에 동일하거나 관련된 내용이 있다면, 기존 내용을 보존하면서 누락된 부분만 보완하고 중복해서 추가하지 않는다. 지침 파일이 없다면 AGENTS.md를 생성하여 위 지침을 반영한다.

## 문서 초기 설정

프로젝트 루트의 `REQUIREMENTS.md`는 [요구사항 템플릿](assets/REQUIREMENTS.md), 긴 요구사항의 `requirements/<ID>.md`는 [세부 요구사항 템플릿](assets/requirement-detail.md)의 형식을 따른다. 기존 요구사항·가정·검증 조건은 보존하여 통합하고, 제품 목표가 없으면 요구사항을 만들어내지 않는다. 미확정 사항이 있을 때만 `Open Questions`를 추가한다.

요구사항에서 하나의 사용자 목적을 완성하고 검증할 수 있는 Feature를 정제한다. 파일이나 기술 계층별로 나누지 않으며, 다음에 구현할 Feature부터 결정한다. 아직 결정되지 않은 Feature의 빈 문서는 만들지 않는다.

루트 `ARCHITECTURE.md`는 첫 Feature의 구조를 정할 때 [구조 템플릿](assets/ARCHITECTURE.md)으로 만들고, 구성 요소나 연결이 바뀔 때 갱신한다. 선택한 Feature의 `docs/features/<feature>/IMPLEMENTATION.md`는 [구현 템플릿](assets/IMPLEMENTATION.md)을 바탕으로 작성한다. 초기 설정 시 각 템플릿을 확인하되, 이후 작업에서는 필요한 문서만 조회한다. 요구사항 전문은 복사하지 않고 ID로 참조하며, Acceptance Criteria의 정의는 요구사항 문서에, 실제 검증 결과는 해당 Feature의 `IMPLEMENTATION.md`에 기록한다. 같은 요구사항은 한 곳에만 두고, 요구사항이 달라지면 그 원본을 갱신한다.

`AGENTS.md`에는 위 개발 원칙과 문서 위치·조회 규칙만 반영하고, 문서 템플릿이나 상세 형식은 복사하지 않는다. 기존 문서가 다른 위치에 있으면 내용을 보존하여 새 구조에 통합하고 관련 링크도 갱신한다. 이전 형식의 Feature `DESIGN.md`가 있으면 규칙의 이유는 해당 요구사항의 근거로, 구조와 그 이유는 `ARCHITECTURE.md`로 옮긴 뒤 삭제한다.
