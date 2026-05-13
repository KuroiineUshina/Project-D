# Escape from Tarkov UX/운영 레퍼런스 조사

조사 기준일: 2026-05-13 KST  
대상 관점: Project D의 싱글 플레이어 3D 판타지 좀비 아포칼립스 익스트랙션 루팅 게임에 적용할 UX, 정보 설계, 퀘스트, 메타 진행, 운영 교훈

## 요약

Escape from Tarkov는 "모르는 상태에서 준비하고, 잃을 수 있는 장비를 들고 들어가, 살아서 나와야만 성과가 확정되는" 구조가 장르의 핵심 긴장을 만든다. 하지만 같은 불친절함이 지도, 탄약, 퀘스트, 사후 정산, 창고 관리까지 과도하게 누적되면 긴장보다 피로와 외부 위키 의존을 만든다.

Project D는 PvP 경쟁과 라이브 와이프가 없는 싱글 플레이어 게임이므로 Tarkov의 고통을 그대로 복제하면 장점보다 단점이 커질 가능성이 높다. 대신 "위험한 원정", "살아 돌아와야 완성되는 루팅", "지역 지식이 곧 성장인 구조", "캠프와 정비의 손맛"은 가져오고, "핵심 정보 은폐", "반복 메뉴 노동", "외부 위키 강제", "설명 없는 진행 초기화"는 줄이는 쪽이 맞다.

## 1. 하드코어 UX: 정보 부족, 지도/탄약/퀘스트 설명의 불친절함

### 조사 내용

Tarkov의 기본 UX는 플레이어에게 많은 정보를 숨기거나 간접적으로만 제공한다. 레이드에서 탈출하려면 추출 지점으로 이동해야 하지만, 게임 안에서 확인 가능한 것은 현재 레이드의 추출 지점 목록에 가깝고 정확한 위치 학습은 플레이어의 기억, 외부 지도, 경험에 크게 의존한다. 공식 위키의 게임 모드 설명도 추출 지점 목록은 게임 안에서 볼 수 있으나, 생존과 아이템 보존은 추출 성공에 달려 있다고 설명한다.

탄약과 방어구는 훨씬 더 복잡하다. 공식 위키의 Ballistics 문서는 탄속, 중력, 공기 저항, 관통력, 장갑 등급, 장갑 내구도, 도탄, 둔탁 피해 등을 별도 시스템으로 설명한다. 즉 "총이 좋다"보다 "어떤 탄을 어떤 장갑에 쏘는가"가 결과를 좌우한다. 이 깊이는 매력적이지만, 게임 내부 정보만으로 직관적으로 판단하기 어렵다.

퀘스트도 목표 장소나 상호작용 대상이 매우 구체적인 반면, 안내는 종종 불충분하다. GamesRadar 리뷰는 맵과 퀘스트의 사인포스팅이 약해 위키가 사실상 필수처럼 기능한다고 평가했다.

### 핵심 메커니즘

- 추출 성공 전까지 루팅 결과가 확정되지 않는다.
- 지도는 "방향 감각과 랜드마크 기억"을 요구한다.
- 탄약 성능이 장비 등급보다 더 중요한 경우가 많다.
- 퀘스트는 특정 장소, 특정 물체, 특정 장비 조건을 요구한다.
- 정보 부족이 위험 감각과 숙련자 우위를 동시에 만든다.

### 디자인 의도 추정

Tarkov는 "작전 전 준비"와 "지역 지식"을 플레이 실력의 핵심으로 만들려는 의도가 강하다. UI가 모든 답을 주지 않기 때문에 플레이어는 외부 자료, 커뮤니티, 반복 경험, 사전 계획을 통해 지식을 축적한다. 이 지식 격차가 장기 몰입을 만들지만, 신규 유저에게는 장벽이 된다.

### Project D 적용점

Project D에서는 정보 부족을 "세계관적 불확실성"으로 남기되, 필수 생존 정보는 게임 안에서 단계적으로 제공해야 한다. 예를 들어 첫 방문 지역은 안개 낀 미지의 숲으로 두되, 발견한 탈출로는 지도에 영구 기록하고, 디아나의 학자 설정을 활용해 관찰 기록, 몬스터 도감, 탄약/마법 장비 실험 노트를 게임 안에 쌓이게 한다.

하드코어함은 "정확한 수치 은폐"가 아니라 "정보를 얻기 위해 위험을 감수해야 하는 구조"에서 나오는 편이 좋다. 처음부터 모든 좀비 약점을 공개하지 않되, 한 번 분석한 적과 재료는 캠프 도감에서 다시 볼 수 있게 만든다.

### 출처 링크

- Steam Store, Escape from Tarkov: https://store.steampowered.com/app/3932890/Escape_from_Tarkov/
- Game modes, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Game_modes
- Ballistics, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Ballistics
- GamesRadar review: https://www.gamesradar.com/games/fps/escape-from-tarkov-review/
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/

## 2. 신규 유저 진입 장벽과 학습 곡선

### 조사 내용

Tarkov는 신규 유저에게 가혹한 게임으로 알려져 있지만, 1.0 전후로 튜토리얼과 단계적 진행을 도입한 흔적이 있다. 공식 위키 Changelog의 1.0 항목에는 튜토리얼, 단계적 진행, UI/QoL 조정이 핵심 기능으로 언급된다. PC Gamer 리뷰도 1.0에서 입문 경험이 과거보다 좋아졌고, 초반에는 무료 치료가 제공된다고 평가했다. 공식 위키 Health system도 일정 조건 이하의 플레이어에게 Therapist 치료가 무료라고 설명한다.

그럼에도 학습 곡선은 여전히 높다. 플레이어는 조작, 탄약, 장갑, 부상, 출혈, 에너지/수분, 소리, 스폰, 추출, 퀘스트, 경제, 창고를 동시에 배워야 한다. Practice 모드는 장소 탐색과 무기 테스트를 허용하지만, 진행 저장은 되지 않는다.

### 핵심 메커니즘

- 고위험 레이드가 기본 경험이다.
- 초반 완충 장치로 튜토리얼, 무료 치료, 연습 모드가 있다.
- 실전 지식은 대부분 반복 실패와 외부 정보에서 얻어진다.
- 배울 시스템 수가 많아 초반 인지 부하가 크다.

### 디자인 의도 추정

Tarkov는 쉬운 입문보다 "버틴 사람만 깊이를 얻는 게임"에 가깝다. 다만 1.0 이후 튜토리얼과 초반 치료 완화가 들어간 것은, 최소한의 이탈 방지 장치는 필요하다는 개발 측 판단으로 보인다.

### Project D 적용점

Project D는 싱글 플레이어이므로 초반 완충을 더 적극적으로 넣어도 하드코어 정체성이 무너지지 않는다.

- 첫 3회 원정은 장비 영구 손실을 제한한다.
- 첫 지역은 "훈련장"이 아니라 실제 게임 공간인 움브라데 외곽으로 만든다.
- 첫 사망 후에는 디아나가 캠프로 간신히 귀환하는 연출과 함께 치료/정비 UX를 가르친다.
- 플레이어가 실패한 이유를 사후 정산에서 명확히 보여준다.
- "몰라도 되는 수치"와 "모르면 억울한 정보"를 구분한다.

### 출처 링크

- Changelog, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Changelog
- Health system, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Health_system
- Game modes, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Game_modes
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/

## 3. 퀘스트 구조: 탐색, 회수, 처치, 표식, 특정 장비 조건

### 조사 내용

공식 위키의 Quests 문서는 Tarkov 퀘스트가 상인에게서 주어지며, 물건 회수, 처치, 특정 장소 표식, 차량/장소 마킹 등으로 구성된다고 설명한다. 보상은 EXP, 상인 평판, 돈, 희귀 컨테이너, 구매 해금 등으로 이어진다.

실제 퀘스트 목록에는 다음 유형이 반복된다.

- 탐색: 특정 지점, 창고, 사무실, 차고를 정찰한다.
- 회수: 특정 장소에서 문서, 장치, 패키지를 찾아 넘긴다.
- 처치: 특정 맵에서 Scav, PMC, 보스 등을 처치한다.
- 표식/설치: MS2000 Marker 같은 장비로 특정 물체나 경로를 표시한다.
- 장비 조건: 특정 방어구, 헬멧, 헤드셋, 무기군을 착용하거나 사용한다.
- 연계 작전: 여러 맵을 이동하고, 운송/전달/처치/추출을 순서대로 수행한다.

### 핵심 메커니즘

- 퀘스트가 레이드의 목적지를 만든다.
- 장비 조건이 플레이스타일을 강제로 바꾼다.
- 특정 위치 목표가 맵 학습을 유도한다.
- 보상이 상인, 장비, 경제 진행과 연결된다.
- 회수형 퀘스트 아이템은 추출 실패 시 사라질 수 있어 긴장이 크다.

### 디자인 의도 추정

퀘스트는 단순한 이야기 전달보다 "플레이어를 위험 지역으로 밀어 넣는 동선 엔진"에 가깝다. 아무 목적 없이 루팅하면 플레이어는 안전한 루트만 반복할 수 있으므로, 퀘스트가 특정 건물, 특정 교전 거리, 특정 장비, 특정 루트를 강제해 게임 전체를 순환시킨다.

### Project D 적용점

Project D의 퀘스트는 Tarkov의 유형을 가져오되, 판타지 생존 맥락으로 재해석하는 것이 좋다.

- 탐색: 오염된 숲 구역, 폐전장, 마법 지뢰 지대 조사
- 회수: 고대 마법 기록, 생존자 물자, 변질된 마력 샘플 회수
- 처치: 특정 변이 좀비, 군집 핵, 오염 야수 제거
- 표식: 안전 통로, 지뢰 위험 구역, 정화 지점 표시
- 장비 조건: 마력 없는 디아나가 특정 도구, 방독 장비, 은제 무기, 드워프 장비를 사용

주의할 점은 장비 조건을 "귀찮은 족쇄"가 아니라 "새로운 공략법을 배우는 요청"으로 만들어야 한다는 것이다. 예를 들어 "활로 15마리 처치"보다 "소리를 줄여야 하는 오염 둥지에서 소음이 적은 무기를 사용"이 낫다.

### 출처 링크

- Quests, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Quests
- Operational Tasks, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Quests#Operational_Tasks

## 4. 일일/주간/이벤트성 목표가 반복 플레이에 주는 영향

### 조사 내용

Tarkov의 Operational Tasks는 랜덤 일일/주간 퀘스트다. 공식 위키에 따르면 일일은 레벨 5부터, 주간은 레벨 15부터 열리며, 아이템 찾기/전달, 특정 위치에서 Scav 처치, 특정 추출 성공 같은 단순 목표를 준다. 보상은 EXP, 화폐, 아이템, 상인 평판 등이다.

1.0.2.0 패치에서는 Escape from Duckov 협업 이벤트처럼 특정 기간 목표와 보상이 추가되었다. 1.0.2.5 패치에서는 무기 부착물 전반의 성능 조정, 매칭/로딩/사후 통계 속도 개선 등이 포함되어 메타와 반복 플레이 리듬에 영향을 주었다.

### 핵심 메커니즘

- 매일/매주 플레이할 작은 이유를 제공한다.
- 반복 가능한 목표가 고정 퀘스트 고갈을 보완한다.
- 랜덤 목표가 플레이 루트와 장비 선택을 흔든다.
- 이벤트는 짧은 기간 동안 경제와 관심사를 집중시킨다.
- 과도한 FOMO는 피로와 반발을 만든다.

### 디자인 의도 추정

라이브 서비스 게임에서는 고정 콘텐츠만으로 장기 접속을 유지하기 어렵다. 일일/주간 목표는 "오늘 할 일"을 주고, 이벤트는 커뮤니티의 동시성을 만든다. 다만 보상과 기간 압박이 강하면 플레이어가 재미보다 숙제처럼 느낄 수 있다.

### Project D 적용점

Project D는 싱글 플레이어이므로 실제 시간 기반 일일/주간은 조심해야 한다. 대신 게임 내 날짜와 지역 상태를 기반으로 한 "원정 의뢰"가 적합하다.

- 캠프 게시판에 3개의 선택 의뢰를 제공한다.
- 플레이어가 원정을 다녀오면 의뢰 목록이 갱신된다.
- 실시간 날짜가 아니라 게임 내 생존 일수로 운영한다.
- 놓친 의뢰가 영구 손실되지 않게 한다.
- 이벤트는 라이브 운영보다 "세계 상태 변화"로 표현한다.

예: "비가 온 다음 날, 오염 늪에서 희귀 약초 출현", "테네비라 정찰대가 숲 가장자리에 보급품을 남김", "좀비 군집 이동으로 특정 탈출로 위험 증가".

### 출처 링크

- Operational Tasks, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Quests#Operational_Tasks
- Changelog, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Changelog
- Patch 1.0.2.5, SteamDB: https://steamdb.info/patchnotes/22211569/

## 5. 퀘스트와 맵 지식 학습의 연결

### 조사 내용

Tarkov에서 퀘스트는 맵 학습 장치다. 플레이어는 특정 건물, 방, 차량, 창고, 루트, 추출 지점, 전이 지점, 보스 스폰, 전리품 스폰을 반복적으로 방문한다. 공식 위키의 인터랙티브 맵은 스폰, 추출, 전리품, 열쇠, 퀘스트 위치를 함께 표시한다.

이는 게임 내부 UX의 약점을 외부 위키가 보완하는 구조이기도 하다. GamesRadar 리뷰는 대부분의 대피 지점을 게임이 충분히 보여주지 않으며, 많은 플레이어가 폰이나 세컨드 모니터에 지도를 띄우고 배운다고 지적했다.

### 핵심 메커니즘

- 퀘스트 목표가 맵 곳곳을 방문하게 만든다.
- 반복 방문으로 랜드마크 기억이 생긴다.
- 추출 지점과 위험 구역 지식이 생존율을 올린다.
- 같은 장소도 스폰 위치, 시간, 장비, 목표에 따라 다르게 느껴진다.

### 디자인 의도 추정

맵은 단순 배경이 아니라 "암기하고 해석하는 던전"이다. 지도 지식은 레벨이나 장비와 별개의 장기 성장축이 된다. 그래서 Tarkov의 숙련자는 총을 잘 쏘는 사람이라기보다 "어디서 누가 나올지 아는 사람"에 가깝다.

### Project D 적용점

Project D의 움브라데 숲도 "반복 방문할수록 해석되는 공간"이어야 한다.

- 첫 방문: 길, 랜드마크, 안전지대만 표시
- 두 번째 방문: 좀비 이동 경로, 소리 위험, 마법 지뢰 흔적 추가
- 세 번째 방문: 숨겨진 지름길, 고급 채집 지점, 특수 탈출로 발견
- 퀘스트 완료 후: 디아나의 지도에 손그림 주석이 남음

Project D는 외부 위키 대신 내부 조사 노트가 성장해야 한다. "플레이어가 외운 지식"과 "캐릭터가 기록한 지식"을 함께 성장시키면 싱글 플레이어에 맞는 학습 만족이 생긴다.

### 출처 링크

- Map: Ground Zero, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Map:Ground_Zero
- Game modes, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Game_modes
- GamesRadar review: https://www.gamesradar.com/games/fps/escape-from-tarkov-review/

## 6. 사망 후 정산, 치료, 재정비 UX

### 조사 내용

Tarkov의 사망은 강하다. 공식 위키 Game modes는 사망 또는 시간 초과 시 일부 예외를 제외하고 가져간 장비와 획득 아이템을 잃는다고 설명한다. Health system 문서는 사망 후 체력이 30%로 돌아오고, 특정 사망 유형은 1%로 돌아올 수 있으며, 레이드 밖에서 자연 회복하거나 아이템/치료 서비스를 사용할 수 있다고 설명한다.

보험은 손실을 완전히 막지 않고, 다른 플레이어가 가져가지 않은 장비를 지연 반환하는 완충 장치다. PC Gamer 리뷰는 초반 무료 치료가 신규 유저 QoL로 작동한다고 평가했다. SteamDB의 1.0.2.5 패치 노트에는 레이드 완료와 사후 통계 표시를 빠르게 하는 변경이 들어갔다.

### 핵심 메커니즘

- 죽으면 장비를 잃고, 캐릭터 상태도 손상된다.
- 치료는 비용, 시간, 아이템 중 하나를 요구한다.
- 보험은 손실 완화지만 확정 반환이 아니다.
- 사후 정산은 손실, 보상, 경험 학습을 연결한다.

### 디자인 의도 추정

사망 후에도 게임은 끝나지 않고 "다음 출격을 준비하는 전략 단계"로 이어진다. 손실 때문에 레이드가 긴장되고, 치료/보험/재정비 때문에 캠프나 은신처가 의미를 가진다.

### Project D 적용점

Project D의 사망/실패는 싱글 플레이어 기준으로 조정해야 한다.

- 완전 장비 삭제보다 "회수 가능한 배낭" 시스템이 적합하다.
- 사망 시 디아나는 캠프로 구조되지만, 일부 전리품과 원정 시간이 손실된다.
- 심한 부상은 다음 원정의 이동/스태미나/조준/소음에 영향을 준다.
- 불칸이 장비 복구, 수리, 임시 대체품 제작을 담당한다.
- 사후 정산에서 "무엇 때문에 죽었는지"를 명확히 보여준다.

Project D의 핵심은 벌주는 것이 아니라, 다음 준비를 더 똑똑하게 만드는 것이다.

### 출처 링크

- Game modes, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Game_modes
- Health system, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Health_system
- Patch 1.0.2.5, SteamDB: https://steamdb.info/patchnotes/22211569/
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/

## 7. 인벤토리 관리 UX와 몰입/피로의 경계

### 조사 내용

Tarkov의 인벤토리는 격자 기반이다. 공식 위키 Looting 문서는 스태시 크기가 에디션과 업그레이드에 따라 달라지고, 컨테이너로 공간 효율을 높일 수 있으며, 장비 대부분은 레이드 중 손실될 수 있다고 설명한다. 보안 컨테이너는 죽어도 보존되는 제한 공간으로, 리스크를 완화하는 핵심 장치다.

이 격자형 인벤토리는 루팅의 물성을 강하게 만든다. 아이템 크기와 형태, 가방/조끼/컨테이너의 공간 효율, 빠른 정리 판단이 게임의 일부가 된다. 하지만 메뉴 정리 시간이 길어지면 레이드 사이 템포를 끊고 피로를 만든다. PC Gamer 리뷰도 Tarkov의 메뉴 관리와 반복 정리 부담을 강하게 언급했다.

### 핵심 메커니즘

- 아이템은 무게뿐 아니라 칸 수와 형태를 가진다.
- 스태시와 컨테이너가 장기 경제 성장축이 된다.
- 보안 컨테이너가 리스크 완충 역할을 한다.
- 정리/판매/보관 판단이 레이드 사이 플레이가 된다.
- 과도하면 "흥미로운 선택"이 아니라 "청소 노동"이 된다.

### 디자인 의도 추정

Tarkov의 인벤토리는 현실감을 주는 동시에 경제 게임을 만든다. 어떤 아이템을 가져갈지, 무엇을 버릴지, 어떤 컨테이너에 보관할지가 생존 판단이 된다. 그러나 편의 기능이 부족하거나 반복 클릭이 많으면 몰입보다 피로가 커진다.

### Project D 적용점

Project D는 격자형 인벤토리를 도입해도 좋지만, 싱글 플레이어이므로 편의성을 더 줘야 한다.

- 원정 중 가방은 제한적 격자 인벤토리로 유지한다.
- 캠프 창고는 자동 정렬, 카테고리 필터, 즐겨찾기, 퀘스트 필요 표시를 제공한다.
- "중요 재료"는 팔기 전 경고한다.
- 장비 프리셋을 저장해 재출격 시간을 줄인다.
- 전리품 가치는 "돈"뿐 아니라 제작, 정화, 연구, 방어시설에 연결한다.

인벤토리의 목표는 플레이어를 괴롭히는 것이 아니라, "무엇을 들고 돌아갈지 고민하게 만드는 것"이다.

### 출처 링크

- Looting, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Looting
- Changelog, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Changelog
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/
- Patch 1.0.2.5, SteamDB: https://steamdb.info/patchnotes/22211569/

## 8. 위키 의존도와 게임 내부 정보 제공의 장단점

### 조사 내용

Tarkov의 공식 위키는 사실상 거대한 보조 UI다. 퀘스트, 탄약, 장갑, 맵, 추출, 전리품, 은신처, 치료, 보험 등 수많은 정보를 제공한다. 공식 위키의 Ballistics와 Quests 페이지가 방대한 데이터표와 상세 조건을 제공한다는 사실 자체가 게임 내부 정보만으로는 이해하기 어려운 시스템이 많다는 반증이기도 하다.

GamesRadar 리뷰는 퀘스트와 맵 안내가 약해 위키 의존이 커진다고 지적했다. PC Gamer 리뷰는 Tarkov의 매력 중 하나가 불완전한 정보와 의도적 불투명성에 있다고 보면서도, 불필요한 바쁜 일이 장점을 묻을 수 있다고 평가했다.

### 핵심 메커니즘

- 외부 위키가 학습, 계획, 최적화를 담당한다.
- 커뮤니티가 지식 생산에 참여한다.
- 정보 탐색도 게임 문화가 된다.
- 하지만 게임 밖 확인이 강제되면 몰입이 깨진다.
- 패치로 정보가 바뀌면 위키/유저 기억도 흔들린다.

### 디자인 의도 추정

Tarkov는 외부 지식 생태계까지 포함해 작동하는 게임이 되었다. 이는 장기 커뮤니티에는 강력하지만, 싱글 플레이어 게임이 그대로 따라 하기에는 위험하다. 싱글 게임에서 외부 위키 의존은 커뮤니티 놀이보다 정보 설계 실패로 느껴질 가능성이 높다.

### Project D 적용점

Project D는 "내부 위키"를 게임 시스템으로 흡수해야 한다.

- 디아나의 연구 노트: 좀비, 오염 마력, 약초, 유물 정보 축적
- 불칸의 제작 도감: 장비 개조, 재료 출처, 수리 요구량 표시
- 지도 주석: 발견한 탈출로, 위험 구역, 반복 스폰, 퀘스트 위치 기록
- 퀘스트 추적: 목표의 정확도 단계를 나눔
- 예: "북쪽 폐전장 근처" -> 단서 발견 후 "부서진 투석기 옆" -> 시야 안 진입 시 상호작용 하이라이트

외부 공략을 막을 수는 없지만, 게임을 정상적으로 즐기기 위해 외부 공략이 필수가 되면 안 된다.

### 출처 링크

- Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Escape_from_Tarkov_Wiki
- Quests, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Quests
- Ballistics, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Ballistics
- GamesRadar review: https://www.gamesradar.com/games/fps/escape-from-tarkov-review/
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/

## 9. 시즌/와이프/패치 변화가 장기 플레이에 주는 영향

### 조사 내용

Tarkov는 오랫동안 대규모 패치와 와이프가 결합된 게임으로 인식되어 왔다. 1.0 이후에는 전통적인 전체 초기화에서 시즌/별도 캐릭터 모델로 이동하는 흐름이 보인다. GameSpot은 2026년 4월 기준 마지막 와이프가 2025년 11월 15일 1.0 출시와 함께 있었고, 이후에는 지속 캐릭터와 선택형 시즌 캐릭터 구조로 이동한다고 설명했다.

공식 위키 Changelog에서도 BattlePass 진행/화폐가 와이프를 넘어 유지되는 구조, PvP/EFT Arena/PvE의 캐릭터 와이프 범위 구분, Prestige 관련 내용이 확인된다. 즉 Tarkov는 장기 진행을 완전히 지우는 방식에서, 일부 진행은 유지하고 일부는 새로 시작하는 방식으로 조정하고 있다.

운영 변화는 장점과 위험이 모두 있다. 1.0.2.5 패치의 무기 부착물 대규모 밸런스 조정은 메타를 새로 만들 수 있다. 반대로 2025년 Hardcore Wipe 논란처럼, 퀘스트와 맵 접근을 크게 제한하는 변화가 충분히 명확히 전달되지 않으면 큰 반발을 만든다.

### 핵심 메커니즘

- 와이프는 경제와 경쟁장을 초기화해 복귀 동기를 만든다.
- 시즌은 새 출발의 재미를 선택형으로 분리할 수 있다.
- 패치는 고착된 메타를 흔들고 새 빌드를 만든다.
- 진행 초기화는 강력하지만, 설명과 보상이 부족하면 신뢰를 잃는다.
- 장기 유저와 신규 유저의 격차를 줄이는 운영 장치가 필요하다.

### 디자인 의도 추정

Tarkov의 와이프/시즌은 단순 초기화가 아니라 "경제 재시작", "메타 리셋", "커뮤니티 동시 복귀" 장치다. 하지만 싱글 플레이어 Project D는 경쟁 경제가 없으므로 강제 초기화의 이점이 작다.

### Project D 적용점

Project D는 강제 와이프를 넣지 않는 것이 맞다. 대신 다음 구조가 적합하다.

- New Game Plus: 클리어 후 선택 초기화
- 원정 시즌: 게임 내 계절/오염 확산 변화
- 지역 상태 변화: 특정 구역의 좀비 밀도, 전리품, 탈출로 변화
- 도전 모드: "보급 부족", "마법 지뢰 활성화", "밤 원정" 같은 선택형 규칙
- 버전 패치 대응: 세이브 호환성과 변경점 고지를 명확히 제공

Project D의 장기 플레이는 라이브 와이프보다 "세계가 반응하고, 캠프가 성장하고, 지도 지식이 깊어지는 것"이 중심이어야 한다.

### 출처 링크

- Changelog, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Changelog
- GameSpot, next Tarkov wipe and seasons: https://www.gamespot.com/articles/when-is-the-next-escape-from-tarkov-wipe/1100-6539387/
- PC Gamer, Hardcore Wipe backlash: https://www.pcgamer.com/games/fps/escape-from-tarkov-blindsides-players-with-immediately-controversial-hardcore-wipe-that-removes-quests-and-disables-most-maps/
- Patch 1.0.2.5, SteamDB: https://steamdb.info/patchnotes/22211569/
- Steam Store, Escape from Tarkov: https://store.steampowered.com/app/3932890/Escape_from_Tarkov/

## 10. 싱글 플레이어 Project D에서 불친절함을 재미로 남기고 피로는 줄이는 방법

### 조사 내용

Tarkov의 장점은 압박감, 손실 위험, 준비의 중요성, 지식 성장, 루팅의 물성이다. 단점은 정보 은폐, 긴 재정비 시간, 위키 강제, 사인포스팅 부족, 급격한 운영 변화다. Project D는 싱글 플레이어이므로 "다른 플레이어에게 빼앗기는 공포" 대신 "숲과 감염, 시간, 자원, 부상, 귀환 실패의 공포"를 만들어야 한다.

Project D는 디아나가 학자였다는 설정을 적극적으로 써야 한다. 정보를 UI가 그냥 알려주는 것이 아니라, 디아나가 관찰하고 기록하고 추론하는 식으로 제공하면 불친절함과 친절함을 동시에 달성할 수 있다.

### 핵심 메커니즘

- 원정 전 준비: 장비, 소모품, 지도, 목표 선택
- 원정 중 판단: 더 깊이 들어갈지, 돌아갈지, 짐을 버릴지 선택
- 원정 후 정산: 치료, 연구, 제작, 방어, 다음 목표 설정
- 지식 성장: 지도, 도감, 제작법, 오염 분석 누적
- 긴장 완화: 반복 클릭과 불명확한 실패는 줄임

### 디자인 의도 추정

Project D가 배워야 할 것은 Tarkov의 "고통"이 아니라 "손실 가능성이 선택을 날카롭게 만든다"는 원리다. 플레이어가 무엇을 잃을 수 있는지 이해하고, 위험을 감수할 이유가 있으며, 실패 후 다음 선택이 더 나아진다면 하드코어함은 재미가 된다.

### Project D 적용점

Project D의 권장 UX 원칙은 다음과 같다.

- 필수 정보는 숨기지 않는다.
- 고급 정보는 관찰, 실험, 반복으로 해금한다.
- 지도는 처음부터 완성본이 아니라 발견형으로 제공한다.
- 퀘스트 설명은 시적인 문장과 실용 목표를 분리한다.
- 사망은 끝이 아니라 부상, 손실, 회수 작전으로 이어진다.
- 캠프 정비는 1분 안에 재출격 가능해야 한다.
- 인벤토리 정리는 선택의 재미만 남기고 반복 노동은 줄인다.
- 외부 위키 대신 내부 도감과 지도 주석을 강화한다.
- 일일/주간 대신 게임 내 날짜 기반 의뢰를 쓴다.
- 패치/변경은 세이브와 진행을 존중한다.

### 출처 링크

- Game modes, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Game_modes
- Health system, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Health_system
- Looting, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Looting
- Quests, Official Escape from Tarkov Wiki: https://escapefromtarkov.fandom.com/wiki/Quests
- PC Gamer review: https://www.pcgamer.com/games/fps/escape-from-tarkov-review/
- GamesRadar review: https://www.gamesradar.com/games/fps/escape-from-tarkov-review/

## Project D에 적용 가능한 UX/운영 교훈 10개

1. 원정의 핵심 보상은 "살아서 돌아와야 확정"되게 한다.
2. 지도 지식은 캐릭터 성장과 별개의 성장축으로 설계한다.
3. 발견한 정보는 내부 지도/도감/노트에 영구 기록한다.
4. 퀘스트는 플레이어를 위험 지역으로 이동시키는 동선 엔진으로 쓴다.
5. 장비 조건 퀘스트는 강제가 아니라 새로운 전술 학습으로 만든다.
6. 사망 후 정산은 벌점보다 학습 정보를 우선한다.
7. 캠프 정비는 생존 RPG의 재미이되, 재출격까지의 클릭 수를 줄인다.
8. 격자 인벤토리는 원정 중 판단에 쓰고, 캠프에서는 편의 기능을 제공한다.
9. 일일/주간 숙제보다 게임 내 세계 상태 변화 의뢰를 사용한다.
10. 패치나 밸런스 변화는 플레이어의 축적된 진행을 존중하는 방식으로 한다.

## Project D가 피해야 할 함정 10개

1. 추출 위치, 퀘스트 대상, 필수 상호작용을 지나치게 숨겨 억울한 실패를 만드는 것.
2. 탄약/속성/오염/방어 시스템을 복잡하게 만들고 내부 설명을 제공하지 않는 것.
3. 외부 위키 없이는 정상 진행이 어려운 정보 설계.
4. 초반부터 장비 영구 손실과 복잡한 치료비를 강하게 적용하는 것.
5. 퀘스트를 "몇 마리 처치", "몇 개 회수"만 반복하는 체크리스트로 만드는 것.
6. 장비 조건을 세계관 이유 없이 강제해 플레이어 빌드를 망가뜨리는 것.
7. 캠프 정비와 창고 정리를 긴 메뉴 노동으로 만드는 것.
8. 사망 원인과 손실 내용을 불명확하게 보여주는 것.
9. 싱글 플레이어 게임에 실시간 FOMO형 일일/주간 과제를 넣는 것.
10. 업데이트로 세이브, 경제, 진행을 갑자기 흔들고 충분히 설명하지 않는 것.

## 우선 설계 제안

Project D의 첫 프로토타입은 다음 3개 루프로 좁히는 것이 좋다.

1. 원정 준비: 장비 2개, 소모품 3개, 목표 1개, 탈출 계획 1개 선택
2. 원정 실행: 제한된 가방, 위험 증가, 목표 달성, 탈출 여부 판단
3. 귀환 정산: 치료, 연구 노트 갱신, 제작 재료 투입, 다음 의뢰 갱신

이 3개가 재미있으면, 이후에 좀비 변이, 마법 지뢰, 캠프 방어, NPC 의뢰, 지역 상태 변화, 장비 개조를 붙여도 중심이 흔들리지 않는다.

