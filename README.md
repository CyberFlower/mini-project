# Toy Project Init

작은 프로젝트를 시작할 때 개발 지침과 세 문서를 준비하는 Codex 스킬이다. 기존 프로젝트에서는 내용을 보존하며 부족한 부분만 보완한다.

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
$toy-project-init으로 이 프로젝트의 개발 지침과 세 문서를 초기 설정해줘.
프로젝트 목표: CSV 파일에서 월별 지출 합계를 출력하는 작은 CLI.
```

스킬은 프로젝트 루트에 다음 파일을 생성하거나 보완한다.

- `AGENTS.md`: 개발 지침
- `REQUIREMENTS.md`: 요구사항, 제약, 완료 기준
- `DESIGN.md`: 아키텍처, 기술 선택과 근거
- `IMPLEMENTATION.md`: 구현 순서, 진행 상태, 검증 결과

스킬 본문은 제공된 개발 지침 원문과 기존 지침 보완에 관한 문단 하나로 구성된다. 이후에는 `AGENTS.md`가 지침을 유지하며, 같은 스킬로 개발을 이어가도록 요청할 수도 있다.

```text
$toy-project-init 지침에 따라 REQUIREMENTS.md의 첫 번째 기능을 구현하고 검증해줘.
```

## 지침만 적용

스킬을 설치하지 않고 [개발 지침 원본](skills/toy-project-init/assets/development-guidelines.md)을 프로젝트의 `AGENTS.md`로 복사해도 된다. 기존 파일이 있으면 내용을 통합한다. 이 방식은 세 문서를 자동으로 준비하지 않으므로 첫 작업에서 문서 초기화를 요청한다.
