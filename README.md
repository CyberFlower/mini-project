# Mini Project Skills

작은 프로젝트를 위한 Codex 스킬 모음이다.

실행 지침은 각 스킬의 `SKILL.md`, 대상 프로젝트에 적용할 템플릿·지침은 `assets/`에 있다. 이 저장소의 작업 원칙은 [AGENTS.md](AGENTS.md)에 둔다. 스킬 본문과 자산을 직접 관리하며 별도의 개발용 요구사항·구조·Feature 문서는 두지 않는다.

| 스킬 | 용도 |
| --- | --- |
| `toy-project-init` | 개발 지침, 요구사항 문서, 구조 문서와 Feature별 구현 문서를 준비한다. 기존 프로젝트에서는 내용을 보존하며 부족한 부분만 보완한다. |
| `commit-review` | 커밋을 하나씩 따라가며 의도와 핵심 변경, 테스트 시나리오를 보고해 설명할 근거가 없는 변경과 검증 근거가 없는 동작을 드러낸다. |

## 설치

이 저장소를 내려받고 사용할 스킬 폴더(`skills/<스킬>`)를 아래 위치 중 한 곳에 복사한다. 스킬마다 따로 복사해도 된다. 같은 이름의 스킬이 이미 있으면 내용을 비교한 뒤 갱신한다.

| 적용 범위 | 설치 위치 |
| --- | --- |
| 개인의 여러 프로젝트 | `~/.agents/skills/<스킬>` |
| 특정 프로젝트 | `<프로젝트>/.agents/skills/<스킬>` |

```bash
git clone https://github.com/CyberFlower/mini-project.git
cd mini-project
mkdir -p ~/.agents/skills
# 새로 설치하는 경우에만 실행
cp -R skills/toy-project-init skills/commit-review ~/.agents/skills/
```

복사한 뒤 대상 프로젝트에서 새 Codex 세션을 열어 사용한다. git 외의 별도 실행 스크립트나 런타임 의존성은 없다. 설치 위치는 [공식 OpenAI Skills 안내](https://learn.chatgpt.com/docs/customization/overview#skills)를 따른다.

## toy-project-init 사용

```text
$toy-project-init 이 프로젝트의 개발 지침과 REQUIREMENTS.md를 준비해줘.
프로젝트 목표: CSV 파일에서 월별 지출 합계를 출력하는 작은 CLI.
```

대상 프로젝트의 문서는 기본적으로 다음 구조로 생성하거나 보완한다. Feature 문서는 다음에 구현할 요구사항을 정제한 뒤 필요한 것부터 만든다.

```text
AGENTS.md
REQUIREMENTS.md
requirements/<ID>.md      # 긴 요구사항만
ARCHITECTURE.md
docs/features/<feature>/
└── IMPLEMENTATION.md
```

`REQUIREMENTS.md`는 전체 요구사항의 개요다. 짧은 요구사항은 그 안에 Acceptance Criteria까지 두고, 긴 요구사항은 `requirements/<ID>.md`에 Acceptance Criteria·다이어그램·근거를 둔다. 형식은 [요구사항 템플릿](skills/toy-project-init/assets/REQUIREMENTS.md)과 [세부 요구사항 템플릿](skills/toy-project-init/assets/requirement-detail.md)을 따른다. `ARCHITECTURE.md`는 구성 요소·흐름과 구조의 선택 이유를, Feature별 `IMPLEMENTATION.md`는 요구사항 ID를 참조해 구현 상태와 실제 검증 결과를 기록한다.

`AGENTS.md`에는 개발 원칙과 문서 위치·조회 규칙만 둔다. [구조 템플릿](skills/toy-project-init/assets/ARCHITECTURE.md)과 [구현 템플릿](skills/toy-project-init/assets/IMPLEMENTATION.md)의 상세 형식은 해당 문서에서 관리한다.

```text
$toy-project-init REQUIREMENTS.md에서 다음 Feature를 정제하고 설계·구현·검증을 진행해줘.
```

## toy-project-init 없이 지침만 적용

스킬을 설치하지 않고 [개발 지침](skills/toy-project-init/assets/development-guidelines.md)을 프로젝트의 `AGENTS.md`로 복사해도 된다. 기존 파일이 있으면 내용을 통합한다. 문서를 준비할 때는 위 템플릿을 참고하여 요구사항·구조 문서와 필요한 Feature 문서를 작성한다.

## commit-review 사용

```text
$commit-review 이 브랜치의 커밋을 오래된 순으로 하나씩 보여줘.
$commit-review HEAD~5..HEAD 최신순으로 보여줘.
```

범위를 주지 않으면 현재 브랜치의 전체 커밋(merge 커밋 제외)을 보고, 순서를 주지 않으면 시작 전에 묻는다. 목록은 요청할 때만 최신순 또는 오래된 순으로 최대 10개 보여준다. 목록 순서가 미지정이면 리뷰 순서를 따르며, 목록 표시 개수는 리뷰 범위를 제한하지 않는다. 한 번에 한 커밋만 보고하며 `다음`·`이전`·번호·해시로 이동한다. 커밋마다 출처가 붙은 의도, 핵심 변경, 의도와 다른 점, 적혀 있지 않은 결정과 그 결정이 담긴 diff(최대 3줄), 테스트 시나리오와 검증 근거를 보고한다. 미커밋 문서도 의도와 검증 근거의 출처로 읽을 수 있다. 보고는 대화창에만 하고 파일과 git 상태를 바꾸지 않는다.
