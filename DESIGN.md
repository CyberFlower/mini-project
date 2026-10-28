# Design

## 구조와 선택 이유

- `skills/toy-project-init/SKILL.md`: 초기화와 이후 개발에서 적용할 절차를 정의한다. 반복적인 파일 변환이 필요하지 않아 별도 실행 스크립트를 두지 않는다.
- `skills/toy-project-init/assets/development-guidelines.md`: 사용자가 제공한 지침 원본이다. 스킬은 이 파일을 읽어 프로젝트 `AGENTS.md`에 반영한다.
- 루트 `AGENTS.md`: 이 저장소에도 같은 지침을 실제 적용한 결과다. 스킬 원본과 프로젝트 적용 결과는 역할이 다르다.
- 세 프로젝트 문서는 요구사항과 완료 기준, 설계 결정의 이유, 진행과 검증 결과를 각각 맡는다. 스킬 내부에 문서 템플릿을 별도로 복제하지 않는다.
- 루트 `README.md`는 공개 배포를 위한 설치·사용 안내다. 개발 상태와 설계 설명을 반복하지 않는다.

## 변경 방식

기존 파일을 먼저 읽고 필요한 내용만 통합한다. 기존 문서의 결정을 새 프로젝트용 빈 문서로 바꾸지 않으며, 동일한 지침을 중복 삽입하지 않는다. 충돌은 요구사항과 가정으로 구분하고 중요한 충돌은 변경 전에 확인한다.

## 형식 근거

공식 OpenAI 문서의 [Skills 안내](https://learn.chatgpt.com/docs/customization/overview#skills)에 따라 `SKILL.md`와 선택적 자산을 스킬 폴더에 묶는다. 프로젝트별 설치는 `.agents/skills`, 개인용 설치는 `~/.agents/skills`를 사용한다. 프로젝트 지침 파일명은 `AGENTS.md`로 통일한다.
