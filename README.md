# Toy Project Init

작은 프로젝트를 위한 개발 지침, 단일 요구사항 문서와 Feature별 설계·구현 문서를 준비하는 Codex 스킬이다. 기존 프로젝트에서는 내용을 보존하며 부족한 부분만 보완한다.

## 설치

이 저장소를 내려받고 `skills/toy-project-init` 폴더를 아래 위치 중 한 곳에 복사한다. 같은 이름의 스킬이 이미 있으면 내용을 비교한 뒤 갱신한다.

| 적용 범위 | 설치 위치 |
| --- | --- |
| 개인의 여러 프로젝트 | `~/.agents/skills/toy-project-init` |
| 특정 프로젝트 | `<프로젝트>/.agents/skills/toy-project-init` |

```bash
git clone https://github.com/CyberFlower/mini-project.git
cd mini-project
mkdir -p ~/.agents/skills
# 새로 설치하는 경우에만 실행
cp -R skills/toy-project-init ~/.agents/skills/
```

복사한 뒤 대상 프로젝트에서 새 Codex 세션을 열어 사용한다. 별도 실행 스크립트나 런타임 의존성은 없다. 설치 위치는 [공식 OpenAI Skills 안내](https://learn.chatgpt.com/docs/customization/overview#skills)를 따른다.

## 사용

```text
$toy-project-init 이 프로젝트의 개발 지침과 단일 REQUIREMENTS.md를 준비해줘.
프로젝트 목표: CSV 파일에서 월별 지출 합계를 출력하는 작은 CLI.
```

문서는 다음 구조로 생성하거나 보완한다. Feature 문서는 다음에 구현할 요구사항을 정제한 뒤 필요한 것부터 만든다.

```text
AGENTS.md
REQUIREMENTS.md
docs/features/<feature>/
├── DESIGN.md
└── IMPLEMENTATION.md
```

`REQUIREMENTS.md` 하나에 전체 요구사항과 개별 Acceptance Criteria를 유지한다. 형식은 [요구사항 템플릿](skills/toy-project-init/assets/REQUIREMENTS.md)을 따른다. Feature별 문서는 요구사항 ID를 참조하며 설계 이유, 구현 상태와 실제 검증 결과를 기록한다.

`AGENTS.md`에는 개발 원칙과 문서 위치·조회 규칙만 둔다. [설계 템플릿](skills/toy-project-init/assets/DESIGN.md)과 [구현 템플릿](skills/toy-project-init/assets/IMPLEMENTATION.md)의 상세 형식은 해당 문서에서 관리한다.

```text
$toy-project-init REQUIREMENTS.md에서 다음 Feature를 정제하고 설계·구현·검증을 진행해줘.
```

## 지침만 적용

스킬을 설치하지 않고 [개발 지침](skills/toy-project-init/assets/development-guidelines.md)을 프로젝트의 `AGENTS.md`로 복사해도 된다. 기존 파일이 있으면 내용을 통합한다. 문서를 준비할 때는 위 템플릿을 참고하여 단일 요구사항 원본과 필요한 Feature 문서를 작성한다.
