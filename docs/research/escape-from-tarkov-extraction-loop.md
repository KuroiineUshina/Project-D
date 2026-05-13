# Escape from Tarkov 핵심 익스트랙션 루프 조사

조사일: 2026-05-13  
목적: Project D의 싱글 플레이어 판타지 좀비 아포칼립스 익스트랙션 루팅 구조 설계 참고

## 조사 기준

- 최신성 기준으로 공식 위키의 Changelog는 2026-05-08 기준 현재 버전을 `1.0.4.6.44802`로 정리하고 있다.
- 공식 웹사이트 뉴스 원문은 현재 브라우저에서 직접 열람이 원활하지 않아, 공식 위키의 시스템 문서와 패치노트 컬렉션을 1차 근거로 사용했다.
- 스폰/초반 동선처럼 공식 문서가 세부를 덜 공개하는 항목은 PC Gamer, PCGamesN 등 외부 가이드를 보조 근거로만 사용했다.

주요 출처:
- [Official Wiki - Changelog](https://escapefromtarkov.fandom.com/wiki/Changelog)
- [Official Wiki - Game modes](https://escapefromtarkov.fandom.com/wiki/Game_modes)
- [Official Wiki - How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov)
- [Official Wiki - Insurance](https://escapefromtarkov.fandom.com/wiki/Insurance)
- [Official Wiki - Secure containers](https://escapefromtarkov.fandom.com/wiki/Secure_containers)
- [Official Wiki - Health system](https://escapefromtarkov.fandom.com/wiki/Health_system)
- [Official Wiki - Looting](https://escapefromtarkov.fandom.com/wiki/Looting)
- [Official Wiki - Found in raid](https://escapefromtarkov.fandom.com/wiki/Found_in_raid)
- [Official Wiki - Hideout](https://escapefromtarkov.fandom.com/wiki/Hideout)
- [Official Wiki - Scavs](https://escapefromtarkov.fandom.com/wiki/Scavs)
- [Official Wiki - Customs](https://escapefromtarkov.fandom.com/wiki/Customs)
- [PC Gamer - Customs exits guide](https://www.pcgamer.com/escape-from-tarkov-customs-map-exits/)
- [PCGamesN - Interchange map guide](https://www.pcgamesn.com/escape-from-tarkov/interchange-map-guide-extracts-stashes)

---

## 1. 레이드 진입 전 준비 단계

### 조사 내용

PMC 모드의 레이드 전 준비는 "무엇을 들고 들어가서 무엇을 잃을 각오를 할 것인가"를 정하는 단계다. 플레이어는 위치와 시간대를 고르고, 스태시에서 무기, 방어구, 탄창, 탄약, 의료품, 식량, 장비 리그, 가방, 열쇠류를 챙긴다. 공식 가이드는 장비 선택에서 가격, 입수성, 성능을 함께 보라고 설명하고, 탄약 선택은 무기 개조보다 직접적인 살상력에 더 큰 영향을 준다고 본다.

보험은 레이드 직전 화면에서 적용한다. Prapor는 저렴하지만 반환이 느리고, Therapist는 비싸지만 빠르다. 보험은 "아무도 회수하지 못하고 레이드 밖으로 나가지 않은 장비"를 나중에 돌려받는 구조라서, 사망해도 무조건 되찾는 보장은 아니다. The Lab, The Labyrinth 같은 예외 지역과 소비품, 탄약, 수류탄, 의료품, secure container 등 보험 불가 품목도 있다.

체력은 PMC에 지속된다. 사망하거나 부상 상태로 탈출하면 다음 레이드 전에 치료 비용을 지불하거나, 보유 의료품을 쓰거나, 은닉처 회복을 기다려야 한다. Secure container는 사망해도 내부 물품을 보존하는 작은 안전 공간이며, 알파/베타/감마/엡실론/카파 등 크기 차이가 존재한다.

### 핵심 메커니즘

- 진입 전부터 비용과 보상 기대값을 저울질하게 만든다.
- 장비 품질은 생존력, 루팅량, 교전 자신감에 영향을 준다.
- 탄약과 의료품 준비는 전투 성능뿐 아니라 장기 생존 루프에 직접 연결된다.
- 보험과 secure container는 전면적인 하드코어 손실을 완충하지만, 완전히 제거하지는 않는다.

### 디자인 의도 추정

진입 전 준비는 단순 장비 선택 UI가 아니라 "레이드의 판돈 설정"이다. 플레이어는 저가 세팅으로 손실을 줄이거나, 고가 세팅으로 생존/전투/수색 효율을 높일 수 있다. 이 선택이 감정적 투자와 긴장감을 만든다.

### Project D 적용점

- 디아나의 출정 준비 화면은 "전투력 세팅"보다 "위험 예산 세팅"으로 설계한다.
- 무기, 방어구, 가방, 치료제, 해독제, 마력 지뢰 탐지 도구, 부패 마력 방호 장비를 레이드 전 선택하게 한다.
- 사망해도 일부를 지키는 `보존 주머니` 또는 `귀환 인장`을 두되, 크기를 작게 유지한다.
- 보험은 판타지식으로 "불칸의 회수 계약"이나 "움브라데 숲 회수대"로 바꿀 수 있다. 회수 성공은 아이템이 적에게 노획되지 않았는지, 위치가 회수 가능한지, 시간이 지났는지에 따라 결정한다.

출처: [Game modes](https://escapefromtarkov.fandom.com/wiki/Game_modes), [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov), [Insurance](https://escapefromtarkov.fandom.com/wiki/Insurance), [Secure containers](https://escapefromtarkov.fandom.com/wiki/Secure_containers), [Health system](https://escapefromtarkov.fandom.com/wiki/Health_system)

---

## 2. 레이드 시작과 스폰 구조

### 조사 내용

Tarkov의 레이드는 맵별 제한 시간과 플레이어 수가 다르다. 예를 들어 Customs는 공식 위키 기준 35분, PMC 10-12명 구조다. 레이드에 들어가면 플레이어는 맵의 지정 스폰 지점 중 하나에서 시작한다. 추출 지점은 스폰 위치와 PMC/Scav 여부에 따라 달라진다. 즉, 스폰은 단순 시작 좌표가 아니라 "어느 방향으로 맵을 횡단해야 하는가"를 정하는 장치다.

외부 맵 가이드들은 많은 맵에서 스폰이 맵 가장자리 또는 특정 권역으로 나뉘며, 반대편 추출 지점으로 이동해야 하는 구조가 초반 동선을 만든다고 설명한다. 그래서 고가치 루트에 가까운 스폰은 빠른 파밍 이점을 주지만, 다른 플레이어와의 초반 충돌 위험도 높인다. 반대로 나쁜 스폰은 안전할 수 있지만 주요 전리품 경쟁에서 밀린다.

### 핵심 메커니즘

- 스폰 위치가 초반 목표와 추출 방향을 동시에 결정한다.
- 플레이어는 "내 스폰이면 누가 어디서 달려올까"를 예측한다.
- 고가치 지역으로 향하는 초반 러시, 스폰 근처 교전, 우회 루트 선택이 생긴다.
- 스폰 자체는 랜덤이지만, 가능한 후보와 위험권역은 학습 가능하다.

### 디자인 의도 추정

스폰 구조는 매 판을 다르게 만들면서도 완전한 혼돈으로 만들지 않는다. 숙련자는 스폰을 보고 근처 위협, 예상 적 동선, 먼저 먹을 수 있는 루팅 포인트, 안전한 후퇴 방향을 계산한다. 이 때문에 맵 지식이 곧 실력으로 전환된다.

### Project D 적용점

- 싱글 플레이어에서도 고정 시작점 하나만 두면 반복성이 빠르게 죽는다. 여러 진입 지점과 여러 귀환 지점을 둔다.
- 디아나가 숲 외곽, 폐전장, 마법 지뢰지대, 무너진 초소, 난민로 등에서 랜덤 진입하게 한다.
- 스폰 직후 30-90초 안에 "초반 판단"이 생겨야 한다. 예: 근처에서 좀비 이동 소리, 생존자 흔적, 마력 지뢰 반응, 희귀 전리품 신호 중 하나가 뜬다.
- PvP가 없으므로 초반 교전 대신 정찰대, 감염자 무리, 환경 재난, 타임 이벤트가 스폰 권역별로 다르게 작동해야 한다.

출처: [Customs](https://escapefromtarkov.fandom.com/wiki/Customs), [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov), [PC Gamer - Customs exits guide](https://www.pcgamer.com/escape-from-tarkov-customs-map-exits/), [PCGamesN - Interchange map guide](https://www.pcgamesn.com/escape-from-tarkov/interchange-map-guide-extracts-stashes)

---

## 3. 레이드 중 탐색 루프

### 조사 내용

레이드 중 기본 흐름은 이동, 수색, 루팅, 은폐, 교전 회피 또는 교전 선택이다. 공식 위키의 Looting 문서는 루팅을 아이템, 장비, 무기를 얻는 핵심 수단으로 설명하며, found in raid 상태의 주요 획득 경로로 본다. 공식 가이드는 맵 숏컷, 랜드마크, 장비 선택, 의료 처리, 탄약 확인, 탄창 관리까지 생존 루프의 일부로 다룬다.

Tarkov의 탐색은 "전리품을 찾는 행위"와 "그 행위를 하는 동안 취약해지는 리스크"가 붙어 있다. 좋은 방, 캐시, 시체, 상자는 시간을 들여 확인해야 하고, 그 사이 소리와 시야 관리가 중요해진다. 장비 무게와 부상 상태는 이동 속도와 판단에 영향을 준다. 부상당한 다리로는 추출까지 가는 것 자체가 장기 리스크가 된다.

### 핵심 메커니즘

- 루팅은 목표이지만, 루팅 행동 자체가 취약 상태를 만든다.
- 이동 루트는 전리품, 은폐, 소리, 시야, 추출 방향 사이의 타협이다.
- 맵 지식은 "좋은 아이템 위치"보다 "좋은 위험 회피 경로"에서 더 강하게 작동한다.
- 전투는 항상 답이 아니다. 회피, 대기, 우회, 포기 판단이 루프의 일부다.

### 디자인 의도 추정

탐색 루프는 플레이어가 항상 작은 결정을 하게 만든다. 문을 열지, 소리를 무시할지, 가방을 더 채울지, 부상 치료를 지금 할지, 추출까지 충분한 시간이 있는지 같은 판단이 누적되어 한 판의 이야기가 된다.

### Project D 적용점

- 전리품 상호작용은 즉시 획득보다 수색 시간, 소리, 자세 제약을 주는 편이 좋다.
- 3인칭 게임이므로 은폐물 뒤 시야 이득이 생긴다. 대신 좀비의 청각/후각/오염 감지, 마법 지뢰의 마력 반응 같은 비시야 위협을 넣어야 한다.
- "좋은 루팅 장소"는 항상 대가가 있어야 한다. 예: 부패 마력 농도, 좁은 통로, 귀환 지점과 반대 방향, 강한 감염체, 제한된 해독제 소모.
- 맵에는 초보도 이해 가능한 랜드마크가 필요하다. 예: 쓰러진 거대 성문, 마법 지뢰 표식, 불탄 전장, 엘프 유적, 마족 연구 잔해.

출처: [Looting](https://escapefromtarkov.fandom.com/wiki/Looting), [Found in raid](https://escapefromtarkov.fandom.com/wiki/Found_in_raid), [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov)

---

## 4. 추출 지점 구조

### 조사 내용

공식 가이드는 각 맵에 여러 추출 지점이 있고, 사용 가능한 추출은 스폰 위치와 PMC/Scav 여부에 따라 달라진다고 설명한다. 일부 추출은 항상 열려 있고, 일부는 가끔만 열리며, 조명/연막/신호 같은 원거리 단서로 확인할 수 있다. 또 일부 추출은 루블, 특정 아이템, 열쇠, 특수 행동, 혹은 PMC와 Scav 협동 같은 조건을 요구한다.

Customs의 공식 위키 표만 봐도 추출 지점은 매우 다양하다. Dorms V-Ex는 차량 탈출과 비용, 인원 제한이 있고, Old Gas Station은 초록 조명 조건이 있다. Railroad Passage는 초록 플레어를 쏘는 조건이 있으며, ZB-013은 레버 작동과 키가 필요하다. 즉, 추출은 "지도 끝에 닿으면 성공"이 아니라 지식, 준비물, 상태, 시간의 복합 시험이다.

### 핵심 메커니즘

- 추출 지점은 레이드의 진짜 목표이며, 성공 판정을 담당한다.
- 추출 가능 여부가 매번 달라져 플레이어가 플랜 B, 플랜 C를 갖게 한다.
- 조건부 추출은 루팅과 탐색에 새로운 목적을 부여한다.
- 추출 카운트다운은 마지막 순간까지 취약성을 유지한다.

### 디자인 의도 추정

추출 시스템은 맵 지식을 강하게 보상한다. 전투를 이기고 전리품을 얻어도, 출구를 모르거나 조건을 만족하지 못하면 실패한다. 그래서 "전투 승리"보다 "생존 귀환"이 장르의 정체성이 된다.

### Project D 적용점

- Project D의 탈출은 단순 워프 포인트가 아니라 조건부 귀환 의식으로 만든다.
- 예시 추출 조건:
  - 오래된 엘프 결계문: 특정 룬석 필요
  - 드워프 회수 마차: 돈/재료 비용, 1회성
  - 숲의 은신처: 낮에만 사용 가능
  - 오염 지대 탈출: 해독제가 남아 있어야 함
  - 마법 지뢰지대 통과: 탐지 도구나 우회 지식 필요
- UI는 Canvas 기반으로 "현재 열린 탈출 후보", "필요 조건", "남은 시간"을 명확히 보여준다.

출처: [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov), [Customs](https://escapefromtarkov.fandom.com/wiki/Customs)

---

## 5. 사망/실패 페널티

### 조사 내용

PMC가 죽거나 시간 내 추출하지 못하면 착용/소지한 대부분의 아이템을 잃는다. 공식 Game modes 문서는 사망 또는 시간 초과 시 근접무기, 완장, 특수 슬롯, secure container 내부를 제외하고 레이드에 가져온 물품을 잃는다고 정리한다. Health system 문서는 사망 또는 MIA 후 메인 메뉴로 돌아가며, 예외 물품을 제외한 아이템을 잃고 체력이 낮은 상태로 돌아간다고 설명한다.

보험은 이 손실을 늦게 일부 되돌릴 수 있지만, 다른 플레이어가 가져간 물품은 돌아오지 않는다. 또한 MIA 상태는 보험 반환에도 불리하다. 공식 보험 문서는 시간 내 탈출하지 못해 MIA가 되면 장착 보험품이 돌아오지 않는다고 설명한다.

### 핵심 메커니즘

- 죽으면 전리품뿐 아니라 "가져간 장비"도 잃는다.
- secure container는 최소한의 성과 보존 장치다.
- 보험은 하드코어함을 완화하되 즉시 복구가 아니다.
- 사망 후 치료 비용과 회복 시간은 다음 출정의 경제에 영향을 준다.

### 디자인 의도 추정

실패 페널티의 핵심은 플레이어에게 매 판을 진지하게 대하게 만드는 것이다. 단, 완전한 전부 손실만 있으면 피로해질 수 있으므로 secure container, 보험, Scav 모드, 치료 시스템 같은 완충 장치를 함께 둔다.

### Project D 적용점

- 싱글 플레이어에서는 너무 큰 손실이 저장 파일 포기나 반복 피로로 이어질 수 있다. 따라서 "장비 완전 손실"보다 계층화된 손실이 좋다.
- 추천 구조:
  - 기본 소지품 대부분 손실
  - 보존 주머니 내부는 유지
  - 장착 장비는 회수 계약 확률에 따라 일부 반환
  - 디아나는 부상/오염/피로 누적으로 다음 출정 비용 증가
  - 중요 스토리 아이템은 별도 보관 규칙 적용
- 죽음보다 더 중요한 실패 유형으로 "감염 진행", "거점 자원 소모", "탈출 지점 폐쇄"를 추가한다.

출처: [Game modes](https://escapefromtarkov.fandom.com/wiki/Game_modes), [Health system](https://escapefromtarkov.fandom.com/wiki/Health_system), [Insurance](https://escapefromtarkov.fandom.com/wiki/Insurance), [Secure containers](https://escapefromtarkov.fandom.com/wiki/Secure_containers)

---

## 6. 성공 보상 구조

### 조사 내용

성공 추출의 보상은 단순 골드 획득이 아니다. 플레이어는 들고 나온 전리품을 스태시에 보관하고, 상인에게 팔고, 퀘스트에 제출하고, 은닉처 업그레이드나 제작에 사용한다. Found in raid 상태는 퀘스트와 경제에 중요하다. 공식 위키 기준 found in raid는 레이드에서 발견하고 Survived 상태로 종료한 물품, 은닉처에서 제작한 물품, 퀘스트 보상 등에 붙는다. Run Through, KIA, MIA 등은 이 상태를 잃을 수 있다.

퀘스트는 경험치, 상인 평판, 돈, 아이템, 구매 잠금 해제를 제공한다. Hideout은 버려진 방공호를 모듈식 거점으로 확장하는 시스템이며, 제작소, 추가 저장, 사격장, 체력 회복 보너스 등 장기 성장을 제공한다. Looting 문서는 스태시와 컨테이너를 장기 보관/정리의 핵심으로 다룬다.

### 핵심 메커니즘

- 성공 추출은 장비, 돈, 퀘스트, 제작, 거점 성장으로 분기된다.
- found in raid는 "살아서 가져왔다"는 인증으로 쓰인다.
- 스태시 제한은 정리와 선택의 압박을 만든다.
- 은닉처는 레이드 밖 성장 목표를 제공한다.

### 디자인 의도 추정

보상 구조는 레이드 한 판을 장기 성장으로 연결한다. 플레이어가 작은 잡템도 "나중에 쓸 수 있다"고 느끼면 루팅의 의미가 넓어진다. 동시에 스태시 공간 제한은 모든 것을 가져오지 못하게 해 선택을 강제한다.

### Project D 적용점

- Project D의 거점은 `움브라데 은신처` 또는 `불칸의 공방`으로 만든다.
- 전리품 분류:
  - 생존 자원: 식량, 약초, 해독제 재료
  - 제작 자원: 금속, 목재, 수정, 천, 가죽
  - 마법 지식: 고대 문헌, 룬 파편, 잃어버린 주문 기록
  - 오염 연구품: 부패 마력 샘플, 변이 조직, 테네비라 실험 기록
  - 판매 가치품: 장신구, 전쟁 유물, 귀금속
- "레이드 생환품" 상태를 두어 퀘스트/연구/상위 제작에는 생환 인증이 붙은 아이템만 사용하게 할 수 있다.

출처: [Found in raid](https://escapefromtarkov.fandom.com/wiki/Found_in_raid), [Quests](https://escapefromtarkov.fandom.com/wiki/Quests), [Hideout](https://escapefromtarkov.fandom.com/wiki/Hideout), [Looting](https://escapefromtarkov.fandom.com/wiki/Looting)

---

## 7. 레이드 시간 제한과 긴장감 형성 방식

### 조사 내용

Tarkov의 각 레이드는 제한 시간이 있다. 공식 가이드는 레이드 카운트다운의 시간 흐름은 실제 시간과 같고, 게임 세계의 낮밤 시간은 7배 빠르게 흐른다고 설명한다. Customs는 35분, Factory는 더 짧은 식으로 맵별 레이드 길이가 다르다. 제한 시간 안에 추출하지 못하면 MIA가 되어 장비 손실과 보험 손실 위험이 커진다.

시간 제한은 단순 종료 타이머가 아니라 루트 압박이다. 플레이어는 "더 루팅할 것인가, 지금 빠질 것인가"를 계속 계산한다. 부상, 과적, 잘못된 추출 선택, 늦은 치료는 모두 남은 시간을 갉아먹는다. 시간은 게임 전반의 긴장을 만드는 보이지 않는 적이다.

### 핵심 메커니즘

- 타이머는 장기 캠핑과 무한 파밍을 방지한다.
- 레이드 후반에는 열린 추출 지점, 남은 거리, 부상 상태가 긴장을 만든다.
- MIA는 사망과 다른 형태의 실패 페널티다.
- 낮밤/날씨는 시야와 루트 선택에 영향을 준다.

### 디자인 의도 추정

시간 제한은 플레이어에게 탐욕의 한계를 묻는다. "조금만 더"가 가장 위험한 선택이 되도록 만들어야 익스트랙션 루프의 맛이 산다.

### Project D 적용점

- Project D에서는 단순 시계보다 세계관형 타이머가 좋다.
- 예시:
  - 밤이 되면 감염자 밀도가 급증한다.
  - 부패 마력 안개가 숲 안쪽부터 퍼진다.
  - 마법 지뢰가 일정 시간이 지나면 불안정해진다.
  - 테네비라 정찰대가 후반부에 진입한다.
  - 귀환 결계의 유지 시간이 줄어든다.
- UI는 Canvas로 남은 시간, 위험 단계, 열린 탈출 조건을 명확히 표시한다.

출처: [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov), [Customs](https://escapefromtarkov.fandom.com/wiki/Customs), [Insurance](https://escapefromtarkov.fandom.com/wiki/Insurance)

---

## 8. Scav/PMC 이중 플레이 구조

### 조사 내용

PMC는 본 캐릭터다. 플레이어는 자기 스태시 장비를 들고 들어가고, 퀘스트를 진행하고, 사망 시 장비 손실을 감수한다. 반면 Scav는 랜덤 장비로 레이드 중간에 스폰하며, 기본 AI Scav와 중립 관계다. Scav로 죽어도 메인 PMC의 소유물은 잃지 않고, 살아 나가면 주운 물품을 스태시에 옮길 수 있다.

Scav는 별도 성장, 쿨다운, Scav karma를 가진다. Scav karma는 차량 추출 비용, Scav 추출 수, Scav 장비 품질, AI Scav 협조 가능성 등에 영향을 준다. Hideout의 Intelligence Center는 Scav 모드 쿨다운을 줄인다.

### 핵심 메커니즘

- PMC는 고위험/고보상 메인 진행이다.
- Scav는 저위험/불완전 통제/랜덤 장비 기반의 보조 루프다.
- Scav는 맵 학습, 경제 회복, 전투 연습, 손실 스트레스 완화 기능을 한다.
- 중립/배신/평판 구조로 PvP 사회적 긴장을 만든다.

### 디자인 의도 추정

Scav 모드는 하드코어 손실 게임이 너무 가혹해지는 것을 막는 완충재다. 동시에 "랜덤 장비로 시작하는 즉흥 생존"이라는 별도 재미를 준다. 플레이어가 망해도 다시 일어설 수 있는 경제적 숨구멍이다.

### Project D 적용점

- 싱글 플레이어 Project D에도 Scav에 해당하는 저위험 루프가 필요하다.
- 후보:
  - 디아나 본인이 아닌 `고용 정찰자`를 보내는 짧은 탐색
  - 불칸이 만든 임시 장비 세트로만 들어가는 `회수 임무`
  - 장비 반입 없이 주변 자원만 챙기는 `정찰 출정`
  - 위험은 낮지만 희귀 전리품과 메인 퀘스트 진행은 제한되는 `보급 루트`
- 이 모드는 실패 스트레스를 낮추고, 맵 학습과 기본 자원 회복을 담당해야 한다.

출처: [Scavs](https://escapefromtarkov.fandom.com/wiki/Scavs), [Game modes](https://escapefromtarkov.fandom.com/wiki/Game_modes), [Hideout](https://escapefromtarkov.fandom.com/wiki/Hideout)

---

## 9. 반복 플레이를 유도하는 불확실성

### 조사 내용

Tarkov의 반복성은 완전 절차 생성보다 "고정된 맵 위의 변동성"에서 나온다. 맵 구조, 주요 랜드마크, 추출 후보, 고가치 지역은 학습 가능하다. 하지만 스폰 위치, 사용 가능한 추출, 전리품, Scav 웨이브, 플레이어 Scav 난입, 다른 PMC 동선, 보스 출현, 시간대, 날씨, 전투 소음은 매 판 다르다.

공식 Scavs 문서는 모든 위치가 Scav로 시작하고, 레이드 중 웨이브로 추가 Scav가 들어오며, 일부 웨이브에는 플레이어 Scav도 들어온다고 설명한다. 공식 추출 가이드는 추출 지점이 스폰과 역할에 따라 다르며 일부는 항상 열리지 않는다고 설명한다. Looting과 Found in raid 구조는 전리품의 위치/가치/생환 여부를 반복 목표로 만든다.

### 핵심 메커니즘

- 맵은 고정되어 학습 가능하지만, 상황은 매번 다르다.
- 플레이어는 정보를 축적할수록 불확실성을 줄인다.
- 완전 랜덤보다 "예측 가능한 후보 중 하나"가 긴장과 숙련을 동시에 만든다.
- 반복 플레이는 보상 테이블, 퀘스트 요구품, 추출 변동성, AI/플레이어 동선이 합쳐져 생긴다.

### 디자인 의도 추정

좋은 익스트랙션 루프는 플레이어에게 "이번 판은 다르지만, 내 지식은 쓸모 있다"고 느끼게 한다. 랜덤이 너무 크면 억울하고, 너무 작으면 암기 게임이 된다.

### Project D 적용점

- Project D 맵은 완전 랜덤 던전보다 고정 랜드마크와 변동 이벤트의 조합이 좋다.
- 변동 요소 후보:
  - 진입 지점과 귀환 지점 후보
  - 희귀 자원 스폰
  - 감염자 무리 이동 방향
  - 마력 지뢰 활성 상태
  - 날씨/안개/밤 위험도
  - 테네비라 잔당 순찰
  - 생존자 흔적과 회수 가능한 시체
  - 오염 샘플의 품질
- 반복 목표는 "돈 벌기"만이 아니라 거점 강화, 디아나 연구, 불칸 제작, 숲 방어선 구축으로 분산한다.

출처: [Scavs](https://escapefromtarkov.fandom.com/wiki/Scavs), [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov), [Looting](https://escapefromtarkov.fandom.com/wiki/Looting), [Found in raid](https://escapefromtarkov.fandom.com/wiki/Found_in_raid)

---

## 10. 싱글 플레이어 Project D로 옮길 때 PvP 대신 필요한 대체 긴장 요소

### 조사 내용

Tarkov의 핵심 긴장은 다른 플레이어가 만든다. 누군가 먼저 고가치 루팅 지점을 털 수 있고, 매복할 수 있고, 소리를 듣고 접근할 수 있고, 내가 보험 받을 장비를 가져갈 수 있다. 싱글 플레이어 Project D는 이 인간 변수 없이도 "예측 불가능하지만 납득 가능한 위협"을 만들어야 한다.

공식 PvE 모드는 AI controlled PMCs로 PvP 일부를 대체한다고 설명한다. 하지만 Project D는 판타지 좀비 아포칼립스이므로 단순 총 든 AI보다 세계관에 맞는 위협 층이 필요하다. 좀비 무리, 오염, 마법 지뢰, 적대 세력, 생존자 경쟁, 시간대 변화, 장비 파손, 소모품 부족이 PvP의 압박을 나눠 맡아야 한다.

### 핵심 메커니즘

- PvP가 빠지면 "누군가 보고 있을지도 모른다"는 긴장이 사라진다.
- 이를 대체하려면 감지/추적/매복/소리 반응/루트 차단 시스템이 필요하다.
- 적 AI는 단순 체력벽보다 플레이어의 계획을 방해해야 한다.
- 환경이 점점 나빠져야 퇴각 판단이 살아난다.

### 디자인 의도 추정

싱글 플레이어 익스트랙션은 PvP를 흉내 내기보다 "상황이 망가지는 속도"를 설계해야 한다. 플레이어가 완벽히 통제할 수 없는 사건이 있어야 하지만, 사후에는 왜 위험했는지 이해할 수 있어야 한다.

### Project D 적용점

- PvP 대체 긴장 요소:
  1. 소리 기반 감염자 유인
  2. 부패 마력 오염 누적
  3. 후반부 감염자 밀도 상승
  4. 테네비라 잔당 또는 약탈자 정찰대
  5. 마법 지뢰 오작동과 연쇄 폭발
  6. 장비 내구도와 소모품 고갈
  7. 귀환 지점 폐쇄/조건 변화
  8. 고가치 전리품 획득 시 추적 이벤트
  9. 부상으로 이동/전투/수색 속도 저하
  10. 거점 방어 상태와 출정 결과의 연결

출처: [Game modes](https://escapefromtarkov.fandom.com/wiki/Game_modes), [Scavs](https://escapefromtarkov.fandom.com/wiki/Scavs), [Health system](https://escapefromtarkov.fandom.com/wiki/Health_system), [How to Play Guide](https://escapefromtarkov.fandom.com/wiki/How_to_Play_Guide_for_Escape_from_Tarkov)

---

## Project D에 적용 가능한 설계 교훈 10개

1. 익스트랙션 루프의 핵심은 전투 승리가 아니라 "살아서 가져오기"다.
2. 레이드 전 준비 화면은 장비창이 아니라 판돈을 정하는 의사결정 공간이어야 한다.
3. 사망 손실은 강해야 하지만, 보존 주머니/회수 계약/저위험 정찰 같은 완충 장치가 필요하다.
4. 추출 지점은 단순 출구가 아니라 조건, 지식, 시간, 준비물을 시험하는 마지막 목표여야 한다.
5. 맵은 완전 랜덤보다 고정 랜드마크와 변동 이벤트를 섞는 편이 학습 재미가 크다.
6. 전리품은 판매 가치, 제작 가치, 퀘스트 가치, 거점 가치가 겹쳐야 루팅 판단이 깊어진다.
7. PvP가 없는 싱글 플레이어에서는 소리, 오염, 시간, 부상, 추적 AI, 탈출 조건 변화가 긴장을 분담해야 한다.
8. 저위험 보조 출정은 경제 회복과 맵 학습을 담당하게 하되, 메인 진행 보상은 제한해야 한다.
9. 시간 제한은 숫자 타이머보다 세계 상태 변화로 느껴지게 해야 한다.
10. Project D의 판타지 정체성은 UI 문구보다 시스템 명명에서 살아난다. 보험은 회수 계약, secure container는 보존 주머니, hideout은 움브라데 은신처/불칸의 공방처럼 세계관 언어로 번역한다.
