---
name: toy-project-init
description: 작은 toy project의 개발 지침과 단일 REQUIREMENTS.md를 준비하고, 요구사항에서 도출한 Feature별 DESIGN.md와 IMPLEMENTATION.md를 작성하거나 정리한다. 프로젝트 시작 또는 같은 문서 흐름으로 개발을 이어갈 때 사용한다.
---

# Development Guidelines

## 1. Requirements
- 모든 필수 요구사항을 충족한다.
- 명시되지 않은 기능은 추가 요청 없이 구현하지 않는다.
- 필수 기능의 구현과 검증에 필요한 최소한의 보조 코드는 허용한다.
- 확정된 요구사항과 가정을 구분하고, 중요한 모호함은 구현 전에 확인한다.

## 2. Documentation
- 문서는 간결하고 명확하게 작성한다.
- 주요 아키텍처 및 구현 방식의 선택 이유를 기록한다.
- 코드에서 쉽게 확인할 수 있는 세부 구현 내용은 반복하지 않는다.
- 프로젝트 루트에 단일 `REQUIREMENTS.md`를 유지하고, Feature별 설계와 구현 기록은 `docs/features/<feature>/DESIGN.md`와 `IMPLEMENTATION.md`에서 관리한다.
- 작업 시 `REQUIREMENTS.md`와 현재 Feature 문서를 읽고, 다른 Feature 문서는 관련이 있을 때만 조회한다.
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

프로젝트 루트의 `REQUIREMENTS.md`는 [요구사항 템플릿](assets/REQUIREMENTS.md)의 형식을 따른다. 기존 요구사항·가정·검증 조건은 보존하여 통합하고, 제품 목표가 없으면 요구사항을 만들어내지 않는다. 미확정 사항이 있을 때만 `Open Questions`를 추가한다.

요구사항에서 하나의 사용자 목적을 완성하고 검증할 수 있는 Feature를 정제한다. 파일이나 기술 계층별로 나누지 않으며, 다음에 구현할 Feature부터 결정한다. 아직 결정되지 않은 Feature의 빈 문서는 만들지 않는다.

선택한 Feature의 `docs/features/<feature>/DESIGN.md`는 [설계 템플릿](assets/DESIGN.md), `IMPLEMENTATION.md`는 [구현 템플릿](assets/IMPLEMENTATION.md)을 바탕으로 작성한다. 초기 설정 시 각 템플릿을 확인하되, 이후 작업에서는 현재 Feature의 필요한 문서만 조회한다. 요구사항 전문은 복사하지 않고 ID로 참조하며, Acceptance Criteria의 정의는 단일 `REQUIREMENTS.md`에, 실제 검증 결과는 해당 Feature의 `IMPLEMENTATION.md`에 기록한다. 요구사항이 달라지면 단일 원본을 갱신한다.

`AGENTS.md`에는 위 개발 원칙과 문서 위치·조회 규칙만 반영하고, 문서 템플릿이나 상세 형식은 복사하지 않는다. 기존 문서가 다른 위치에 있으면 내용을 보존하여 새 구조에 통합하고 관련 링크도 갱신한다.
