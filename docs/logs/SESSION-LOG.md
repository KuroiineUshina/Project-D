# Project D 작업 기록 보관소

이 문서는 여러 컴퓨터와 여러 세션에서 진행한 작업을 이어가기 위한 기록 보관소다.

새 세션에서 의미 있는 변경을 했다면 아래 형식으로 항목을 추가한다.

## 기록 형식

```text
날짜:
컴퓨터/세션:
작업자:
브랜치:
커밋:

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

## 2026-05-13

컴퓨터/세션: 초기 Codex 세션  
작업자: Codex  
브랜치: main  
커밋: 7fb0dd6 ~ e234abe

작업 요약:

- GitHub 저장소 연결
- 게임 아이디어 초안 문서화
- Project D 방향과 레퍼런스 문서화
- Escape from Tarkov 조사 문서화
- 새 세션 시작 지침, 분야 분담, 첫 수직 슬라이스 문서화

변경 파일:

- `README.md`
- `AGENTS.md`
- `START-HERE.md`
- `docs/game-idea.md`
- `docs/project-direction.md`
- `docs/research/*`
- `docs/design/first-playable-slice.md`
- `docs/process/*`

검증:

- GitHub push 완료
- `main -> origin/main` 상태 확인

다음 작업:

- Unity 6 프로젝트 생성 전 결정표와 작업 범위 재확인

주의점:

- 이미지는 반드시 imagegen 스킬 사용
- UI는 Unity Canvas 우선
- 사용자가 스토리, 의뢰 라인, 추가 지역, 추가 NPC를 직접 작성할 예정

## 2026-05-13 결정 답변지 반영

컴퓨터/세션: 초기 Codex 세션  
작업자: Codex  
브랜치: main  
커밋: Record Project D gameplay decisions

작업 요약:

- 사용자 결정 답변지를 프로젝트 결정표로 문서화
- `원정`을 `탐사`, `퀘스트`를 `의뢰`, `루팅`을 `수색/전리품 획득`으로 정리
- 움브라데 숲 탐사 제한시간을 25분으로 확정
- `O` 타이머 표시와 더블 탭 귀환 지점 목록 규칙 문서화
- 실패 시 secure container 대응 물건을 제외한 전부 손실 구조 문서화
- 보험업자 NPC와 마법생물 하수인 회수 설정 문서화
- 메인 메뉴와 단일 저장 파일, 세계 초기화 규칙 문서화
- 작업 기록 보관소와 새 세션용 결정표 추가

변경 파일:

- `README.md`
- `AGENTS.md`
- `START-HERE.md`
- `docs/design/project-decisions.md`
- `docs/design/first-playable-slice.md`
- `docs/process/collaboration-workflow.md`
- `docs/process/workstreams.md`
- `docs/project-direction.md`
- `docs/logs/SESSION-LOG.md`

검증:

- 이전 용어/상충 규칙 검색
- 답변지 기준 문서 반영 여부 확인

다음 작업:

- secure container에 해당하는 Project D 고유 명칭 결정
- 마법생물 하수인 형태 결정
- 첫 버전 제외 시스템 목록 결정

주의점:

- 스토리, 의뢰 라인, 지역 설정, NPC 설정은 사용자가 직접 작성 예정
- Codex와 Codex 서브 에이전트는 질문, 피드백, 구조화, 구현을 지원

## 2026-05-14 이미지 작업 규칙 반영

컴퓨터/세션: Codex 세션  
작업자: Codex  
브랜치: main  
커밋: Image workflow update

작업 요약:

- 이미지가 필요한 작업은 먼저 Codex 서브 에이전트에게 이미지 브리프, 레퍼런스 정리, 프롬프트 초안을 맡기도록 규칙화
- 최종 이미지 생성은 imagegen 스킬만 사용하도록 기존 규칙 유지

변경 파일:

- `AGENTS.md`
- `START-HERE.md`
- `docs/design/project-decisions.md`
- `docs/process/collaboration-workflow.md`

검증:

- 이미지 작업 규칙 검색으로 반영 위치 확인

다음 작업:

- 실제 이미지 작업 요청 시 Codex 서브 에이전트가 먼저 브리프와 프롬프트 초안을 준비

주의점:

- 코드나 벡터를 통한 이미지 생성은 금지
