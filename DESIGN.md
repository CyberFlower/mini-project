# Design

## 구조와 선택 이유

- `skills/toy-project-init/SKILL.md`: 필수 메타데이터 뒤에 사용자 제공 지침 원문과 기존 지침 보완에 관한 문단 하나만 둔다. 원문을 그대로 사용하려는 요청에 따라 별도 상세 절차를 제거했다.
- `skills/toy-project-init/assets/development-guidelines.md`: README에서 안내하는 `AGENTS.md` 직접 복사용 원문이다. 스킬 본문을 읽는 데 이 파일을 추가로 조회할 필요는 없다.
- 루트 `AGENTS.md`: 이 저장소에도 같은 지침을 실제 적용한 결과다. 스킬 원본과 프로젝트 적용 결과는 역할이 다르다.
- 세 프로젝트 문서는 요구사항과 완료 기준, 설계 결정의 이유, 진행과 검증 결과를 각각 맡는다. 스킬 내부에 문서 템플릿을 별도로 복제하지 않는다.
- 루트 `README.md`는 공개 배포를 위한 설치·사용 안내다. 개발 상태와 설계 설명을 반복하지 않는다.

## 변경 방식

기존 지침은 보존하면서 누락된 내용만 보완하고 중복 삽입하지 않는다. 지침 파일이 없으면 `AGENTS.md`를 생성한다. 중요한 모호함의 확인 등 나머지 개발 방식은 사용자 원문을 따른다.

## 형식 근거

공식 OpenAI 문서의 [Skills 안내](https://learn.chatgpt.com/docs/customization/overview#skills)에 따라 `SKILL.md`와 선택적 자산을 스킬 폴더에 묶는다. 프로젝트별 설치는 `.agents/skills`, 개인용 설치는 `~/.agents/skills`를 사용한다. 프로젝트 지침 파일명은 `AGENTS.md`로 통일한다.
