# Project D 협업 및 Git 작업 흐름

## 기본 원칙

Project D는 여러 컴퓨터, Codex 서브 에이전트, 여러 세션에서 이어서 작업할 수 있도록 GitHub 저장소를 단일 기준점으로 사용한다.

`main` 브랜치는 현재 합의된 안정 문서와 작동 가능한 구현을 보관하는 기준 브랜치다. 실험, 조사, 프로토타입, 대규모 수정은 별도 브랜치에서 진행한 뒤 확정된 내용만 `main`에 합친다.

## 역할

### 사용자

- 최종 디렉터
- 캐릭터 디자인, 모델링, 애니메이션 주도
- 비주얼 톤과 세계관 결정권
- 구현 우선순위 승인

### Codex

- Unity 6 프로젝트 구조 설계
- 시스템 설계와 코드 구현
- 문서 정리와 Git 관리
- 수직 슬라이스 구현 지원
- 조사 결과 취합과 설계 결정 문서화

### Codex 서브 에이전트

- 별도 브랜치에서 아이디어 확장
- 문서 초안 작성
- UI/UX 흐름 비교
- 프로토타입 검증
- 구현 대안 조사

Codex 서브 에이전트는 맡은 범위가 명확할 때만 파일을 수정한다. 평가나 조사만 요청받은 경우에는 파일 수정과 커밋을 하지 않는다.

Codex 서브 에이전트가 구현이나 문서 작성을 맡은 경우에도 `main`에 직접 큰 변경을 쌓기보다, 작업 범위와 변경 파일을 명확히 남긴다.

## 브랜치 규칙

권장 브랜치 이름:

- `docs/topic-name`: 문서 정리
- `research/topic-name`: 조사
- `design/topic-name`: 기획/설계
- `prototype/topic-name`: 프로토타입 구현
- `feature/topic-name`: 확정 기능 구현
- `fix/topic-name`: 버그 수정

예시:

```powershell
git checkout -b design/first-expedition-flow
git checkout -b prototype/extraction-loop
git checkout -b docs/session-handoff
```

## 작업 시작 절차

1. 최신 상태를 받는다.

```powershell
git pull
```

2. 상태를 확인한다.

```powershell
git status --short --branch
```

3. [START-HERE.md](../../START-HERE.md)를 읽고 현재 목표를 확인한다.

4. 작업이 문서, 프로토타입, 구현 중 어디에 해당하는지 정한다.

5. 필요하면 별도 브랜치를 만든다.

## 작업 중 규칙

- 관련 문서를 먼저 확인한다.
- 기존 사용자 변경을 되돌리지 않는다.
- 구현보다 범위 확인이 필요한 작업은 먼저 문서에 결정 사항을 남긴다.
- 새 기능은 첫 수직 슬라이스에 직접 도움이 될 때 우선한다.
- 평가만 요청받은 Codex 서브 에이전트는 파일 수정과 커밋을 하지 않는다.
- UI는 Unity Canvas를 우선한다.
- 이미지가 필요하면 imagegen 스킬을 사용한다.

## 문서화 규칙

새로운 결정이 생기면 다음 중 하나에 반영한다.

- 전체 방향: [project-direction.md](../project-direction.md)
- 첫 수직 슬라이스: [first-playable-slice.md](../design/first-playable-slice.md)
- 분야와 책임: [workstreams.md](workstreams.md)
- 조사 결과: `docs/research/`
- 새 세션 시작 규칙: [START-HERE.md](../../START-HERE.md)

문서에는 다음을 남긴다.

- 결정한 내용
- 왜 그렇게 결정했는지
- 지금 만들 범위
- 나중으로 미룬 범위
- 관련 파일 또는 시스템

## 커밋 규칙

커밋은 하나의 의도를 가지게 작게 만든다.

권장 메시지:

- `Document first playable slice`
- `Add extraction loop prototype`
- `Implement basic inventory UI`
- `Add first expedition design notes`

커밋 전 확인:

```powershell
git status --short --branch
git diff --stat
```

커밋과 push:

```powershell
git add .
git commit -m "작업 내용"
git push
```

## 완료 기준

문서 작업 완료 기준:

- README나 관련 인덱스에서 찾을 수 있다.
- 다음 세션에서 읽어도 의도가 분명하다.
- 현재 목표와 미룬 범위가 구분되어 있다.

구현 작업 완료 기준:

- Unity에서 실행 가능한 상태다.
- 최소한의 테스트나 직접 확인 결과가 있다.
- 실패하거나 미검증된 부분을 작업 요약에 남긴다.
- 첫 수직 슬라이스 루프에 기여한다.

## 세션 인수인계 템플릿

세션 종료 시 다음 형식으로 요약한다.

```text
작업 요약:
- 

변경 파일:
- 

검증:
- 

다음 작업:
- 

주의점:
- 
```
