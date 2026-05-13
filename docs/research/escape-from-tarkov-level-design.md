# Escape from Tarkov 맵/레벨 디자인 조사

조사일: 2026-05-13 KST  
목적: Project D의 판타지 + 좀비 아포칼립스 + 생존 + 추출형 루팅 구조 설계 참고  
주요 기준: 공식 Escape from Tarkov Wiki, 맵/키/보스/루팅/트랜짓 문서, 현재 공개 자료

> 주의: Escape from Tarkov는 라이브 서비스 성격이 강하고, 맵 접근 조건/탈출 조건/보스 스폰/루팅 밸런스가 패치마다 바뀔 수 있다. 아래 내용은 2026-05-13 기준 공개 위키와 현재 접근 가능한 자료를 바탕으로 정리했다.

## 1. 주요 맵들의 역할 분화: Customs, Woods, Interchange, Reserve, Shoreline, Streets 등

### 조사 내용

Tarkov의 맵들은 단순히 배경만 다른 것이 아니라 플레이 목적과 위험 곡선이 다르게 설계되어 있다.

- Customs는 공장지대, 터미널, 연료 저장고, 사무실, 기숙사, 가스 스테이션 등이 섞인 산업형 관문 맵이다. 길이 비교적 선형이고 Dorms, New Gas, Construction, Scav Base 같은 충돌 지점이 명확해서 퀘스트, PvP, 중간급 루팅이 자주 겹친다.
- Woods는 자연보호구역 기반의 넓은 숲 맵이다. Sawmill, USEC camp, village, bunker, logging camp처럼 야외 랜드마크가 퍼져 있고, 장거리 교전/저격선/은닉 루팅이 강하다.
- Interchange는 ULTRA 쇼핑몰과 외곽 도로/주차장/전력소가 결합된 대형 실내 복합 맵이다. 매장별 기능이 뚜렷하고 전력, 경보, KIBA/ULTRA medical 같은 잠긴 고가치 지점이 중심 동기를 만든다.
- Reserve는 군사 예비기지로 지상 병영/창고/기관총/유탄발사기/지뢰/지하 벙커가 결합된다. 열쇠 방, 지하 동선, 레버, 열차, 레이더 돔, 벙커 탈출이 목표성을 만든다.
- Shoreline은 큰 외곽 맵 안에 Health Resort라는 고밀도 실내 고가치 구역을 배치한 구조다. 해변, 마을, 발전소, 기상관측소, 별장, 리조트가 위험 밀도를 다르게 만든다.
- Streets of Tarkov는 도심 맵으로 은행, 쇼핑몰, 호텔, 아파트, 지하/골목/도로가 얽힌 고밀도 도시형 구조다. Kaban, Kollontay, BTR, 클레이모어/스나이퍼 경계가 도시 탐색을 압박한다.
- Factory는 작은 실내 공장 맵으로 짧은 시간, 좁은 거리, 다층 구조, 즉시 교전 중심의 압축형 전투 맵이다.
- Ground Zero는 TerraGroup 본사 지역이자 초반/숙련자 매칭 분리 구조를 갖는 도심 튜토리얼형 핫존이다.

### 핵심 메커니즘

맵마다 “무엇을 하러 가는 곳인지”가 분명하다. 예를 들어 Woods는 넓은 야외 탐색과 은닉 루팅, Interchange는 매장 중심 실내 침투, Reserve는 군사 보급품과 조건부 탈출, Shoreline은 외곽 이동 후 리조트 고위험 루팅, Streets는 도시 밀집 탐색에 가깝다.

### 디자인 의도 추정

Tarkov는 맵을 난이도 순서로만 나누지 않고, 서로 다른 플레이 습관을 요구하는 공간으로 분화한다. 이 덕분에 플레이어는 장비, 퀘스트, 위험 감수 성향, 시간에 따라 맵을 선택하게 된다.

### Project D 적용점

Project D도 “숲 맵”, “전쟁터 맵”, “성채 맵”, “오염지대 맵”을 단순 테마 차이가 아니라 목적 차이로 나눠야 한다.

- 움브라데 숲: 은닉 자원, 약초, 마법 지뢰, 길 잃음, 저시야 탐색.
- 옛 전쟁터: 군수품, 잔해, 지뢰, 시체, 열린 저격선, 위험한 경유지.
- 성채/요새: 잠긴 방, 열쇠, 레버, 보스급 감염체, 고가치 제작 재료.
- 오염지대: 감염 누적, 제한 시간, 보호 장비, 희귀 재료, 후반부 루팅.

### 출처 링크

- [Customs - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Customs)
- [Woods - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Woods)
- [Interchange - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Reserve - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Shoreline - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Shoreline)
- [Streets of Tarkov - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)
- [Factory - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Factory)
- [Ground Zero - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Ground_Zero)

## 2. 랜드마크와 길찾기: 지도 없이도 기억 가능한 구조를 만드는 방식

### 조사 내용

Tarkov의 주요 맵은 방위표시보다 랜드마크 암기에 의존한다. Customs의 Dorms, Big Red, New Gas, Old Gas, Construction, Sniper Roadblock, ZB-013, Woods의 Sawmill, lake, mountain, village, USEC camp, Reserve의 chess-piece 건물명과 radar dome, Interchange의 IDEA/OLI/Goshan/KIBA/Power Station, Shoreline의 Resort/Power Station/Pier/Cottages/Weather Station, Streets의 Pinewood Hotel/Concordia/Klimov Mall/Beluga/arch/cinema 같은 식이다.

특히 실내 맵은 “상점명/건물명/층/전력/경보”가 길찾기 단위가 된다. Interchange의 ULTRA 쇼핑몰은 매장 이름이 곧 지역 구분이 되고, Reserve는 흑백 체스말 이름이 군사 건물을 구분한다. Streets는 대형 도심 랜드마크와 골목, 지하, 아파트 입구가 복합적으로 작동한다.

### 핵심 메커니즘

플레이어가 “동서남북”보다 “보이는 것”으로 위치를 이해한다. 큰 랜드마크, 독특한 실루엣, 소리, 조명, 지형 장벽, 건물명, 위험 신호가 길찾기 언어가 된다.

### 디자인 의도 추정

처음에는 길을 잃게 만들되, 반복 플레이 후에는 “내가 어디서 죽었고 어디로 나가야 하는지”가 몸에 남게 하는 방식이다. 지도 없이도 기억되는 구조는 추출형 게임에서 숙련도를 강하게 체감하게 만든다.

### Project D 적용점

움브라데 숲은 UI 미니맵보다 눈에 띄는 지형 기억을 우선해야 한다.

- 거대한 흰 고목, 부서진 엘프 석문, 전쟁 지뢰 표식, 마력 고갈 늪, 붉은 오염 안개, 전차 잔해, 성채 첨탑 같은 강한 실루엣이 필요하다.
- 같은 숲이라도 “약초숲”, “지뢰숲”, “부패 시체 계곡”, “옛 전투 진지”, “버려진 감시탑”처럼 기능과 생김새가 달라야 한다.
- 싱글 플레이어이므로 NPC 대사/디아나의 혼잣말/Canvas 지도 표식은 보조로 쓰되, 핵심 길찾기는 레벨 자체가 제공해야 한다.

### 출처 링크

- [Map:Woods - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Map:Woods)
- [Interchange - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Reserve - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Streets of Tarkov - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)

## 3. 루팅 포인트 배치: 고가치 지역, 저위험 지역, 경유지의 차이

### 조사 내용

Tarkov의 루팅은 “어디든 보상이 있다”가 아니라 보상 등급과 접근 위험이 지역별로 달라진다.

- 고가치 지역: Interchange의 KIBA, ULTRA medical, Customs의 Dorm 314 Marked Room, Woods의 Shturman stash, Shoreline의 Health Resort, Reserve의 다수 RB 키 방, Streets의 아파트/사무실/상점 키 방.
- 저위험/저밀도 지역: Woods의 은닉 캐시, Shoreline 외곽 마을/농장/해변, Customs 외곽 창고와 사무실 일부처럼 빠르게 훑고 빠질 수 있는 구역.
- 경유지: Customs의 다리/도로/철길, Interchange 외곽 도로와 주차장, Reserve의 지상-지하 연결부, Shoreline의 발전소/가스 스테이션/피어, Streets의 골목과 지하 통로.

공식 위키의 Looting 문서는 컨테이너 종류가 명확히 분화되어 있음을 보여준다. 금고는 화폐/귀중품, 의료 가방은 의료품, 기술 상자는 산업/전자 아이템, 무기 상자는 무기와 부착물을 제공한다. 즉 컨테이너의 외형과 위치가 루팅 기대값을 만든다.

### 핵심 메커니즘

고가치 루팅은 키, 전력, 경보, 보스, 중심부 위치, 탈출 난이도와 묶인다. 반대로 저위험 루팅은 수익은 낮지만 경로 안정성이 높고, 경유지는 목적지가 아니어도 충돌이 생긴다.

### 디자인 의도 추정

플레이어가 “지금 안전하게 작게 벌 것인가, 위험한 중심부를 찌를 것인가”를 매번 판단하게 하는 구조다. 고가치 방은 보상 자체보다 그 방까지 접근하고 빠져나오는 과정이 게임을 만든다.

### Project D 적용점

Project D의 루팅 포인트는 다음처럼 등급화하면 좋다.

- 고가치: 오염된 연구실, 마법 지뢰 보관고, 성채 무기고, 고대 마법서고, 감염체 둥지 중심부.
- 중간 위험: 전쟁터 야전병원, 부서진 보급마차, 폐허 마을, 드워프 작업장 잔해.
- 저위험: 숲속 약초, 사냥꾼 은닉함, 버려진 야영지, 얕은 폐허.
- 경유지 보상: 다리 밑, 부서진 문루, 좁은 계곡, 지하 배수로에 소량 보상을 두어 이동 중 판단을 만들기.

### 출처 링크

- [Looting - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Looting)
- [KIBA Arms inner grate door key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Kiba_Arms_inner_grate_door_key)
- [ULTRA medical storage key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/ULTRA_medical_storage_key)
- [Dorm room 314 marked key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Dorm_room_314_marked_key)
- [Shturman's stash key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Shturman%27s_stash_key)

## 4. 위험 밀도 설계: 병목, 열린 공간, 건물 내부, 저격선, 소리 노출

### 조사 내용

Tarkov의 위험은 적 배치만으로 생기지 않는다. 공간 유형이 위험을 만든다.

- 병목: Customs의 다리/강변/공장 관문, Reserve의 지하 벙커 입구와 D-2, Interchange의 에스컬레이터/계단/매장 입구, Shoreline Resort의 복도와 계단.
- 열린 공간: Woods의 벌목장 주변, Shoreline의 해변/들판, Reserve의 헬기장과 야외 병영 사이, Streets의 대로.
- 건물 내부: Interchange, Shoreline Resort, Reserve bunker, Streets 아파트/상가 내부는 코너, 문, 층간 소리, 제한 시야가 핵심이다.
- 저격선: Woods/Reserve/Shoreline은 장거리 시야와 고지대가 위험을 만든다.
- 환경 경계: Woods/Reserve/Interchange/Streets/Ground Zero는 지뢰, 클레이모어, Border Snipers 같은 맵 외곽 위험이 있다.
- 소리 노출: Tarkov는 문, 금속, 유리, 계단, 사격, 경보, 사이렌, 전력 스위치 같은 소리 이벤트가 위치 노출을 만든다. Reserve의 Hermetic Door는 사이렌과 Raider 스폰 가능성이 붙고, Interchange는 KIBA/상점 경보와 전력 스위치가 공간 전체에 영향을 준다.

### 핵심 메커니즘

위험 밀도는 “적 수”보다 “보고 들리는 방식”에서 나온다. 열린 곳은 발견 위험, 실내는 매복 위험, 병목은 충돌 위험, 고지대는 제압 위험, 소리 이벤트는 추적 위험을 만든다.

### 디자인 의도 추정

공간마다 다른 긴장 방식을 제공하려는 설계로 보인다. 같은 적을 상대해도 들판, 복도, 지하, 계단, 쇼핑몰 중앙에서 체감 난이도가 달라진다.

### Project D 적용점

Project D의 좀비/감염체는 PvP 대신 위험 밀도 장치로 사용해야 한다.

- 숲의 열린 초원: 멀리 보이는 대신 엄폐가 적고, 오염 안개나 활쏘는 감염체가 압박.
- 전쟁터 참호: 병목과 소리 반향, 지뢰, 시체더미 속 잠복 감염체.
- 성채 내부: 좁은 문, 계단, 무너진 홀, 잠긴 방, 보스 감염체 순찰.
- 오염지대: 시야 차단, 감염 게이지 상승, 보호 장비 내구도 감소.
- 소리 기반 AI: 상자 파괴, 금속 문 개방, 마법 장치 작동, 함정 해제 실패가 감염체를 끌어오도록 설계.

### 출처 링크

- [Woods - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Woods)
- [Reserve - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Interchange - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Streets of Tarkov - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)
- [Ground Zero - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Ground_Zero)

## 5. 탈출 지점 배치와 맵 횡단 압력

### 조사 내용

Tarkov의 탈출 지점은 대부분 스폰 위치와 반대편/다른 권역에 배치되어 맵 횡단 압력을 만든다. 또한 탈출은 항상 같은 난이도가 아니다.

- 기본 탈출: Crossroads, Trailer Park, ZB-1011, Outskirts, Road to Customs 등.
- 조건부 탈출: 차량 탈출(V-Ex), 플레어 탈출, 열쇠 필요 탈출, 레버/전력 필요 탈출, 특정 장비 필요 탈출.
- 협동 탈출: PMC + Scav 조건.
- 위험 신호 탈출: Reserve의 Armored Train은 도착 시간과 경적, Raider 스폰 가능성으로 주변 충돌을 만든다. Bunker Hermetic Door는 레버와 사이렌이 붙는다.
- 트랜짓: 최근 구조에서는 맵을 완전히 끝내지 않고 다른 맵으로 이동하는 시스템도 있다. 트랜짓은 레이드 시작 1분 뒤 사용 가능하고, 사용 시 일반 탈출을 닫으며, 아이템 배송 시스템까지 연결된다.

### 핵심 메커니즘

탈출은 단순 종료 버튼이 아니라 레벨의 후반부 목적지다. 가방이 찰수록 이동속도/위험회피/동선 선택이 달라지고, 탈출 지점은 플레이어를 다시 위험 지대 근처로 끌어당긴다.

### 디자인 의도 추정

루팅의 쾌감만으로 끝내지 않고 “살아서 가져나가는 과정”을 게임의 절반으로 만들려는 의도다. 조건부 탈출은 준비물과 정보의 가치를 높인다.

### Project D 적용점

싱글 플레이어인 Project D도 탈출을 단순 포털로 두면 안 된다.

- 기본 탈출: 숲 경계, 안전 야영지, 드워프 수송로.
- 조건부 탈출: 마법 지뢰 해제, 신호화살, 성문 레버, 정화 수정 사용, 불칸이 수리한 승강기.
- 위험 탈출: 탈출 장치를 켜면 감염체가 몰려오거나 오염 폭풍이 시작됨.
- 선택형 탈출: 빠른 탈출은 보상 일부 포기, 깊은 탈출은 추가 루팅/보스 위험.
- 장기 구조: 여러 소규모 지역을 이어서 탐사하는 “연속 원정”을 후반 시스템으로 확장 가능.

### 출처 링크

- [Customs - Extractions/Transits](https://escapefromtarkov.fandom.com/wiki/Customs)
- [Reserve - Extractions/Transits](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Interchange - Extractions/Transits](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Shoreline - Extractions/Transits](https://escapefromtarkov.fandom.com/wiki/Shoreline)
- [Streets of Tarkov - Extractions/Transits](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)
- [Transits - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Transits)

## 6. 수직성, 실내/실외 전환, 시야 차단물의 쓰임

### 조사 내용

Tarkov는 실내/실외 전환과 수직성을 위험 전환 장치로 쓴다.

- Reserve는 지상 병영/헬기장/창고/돔과 지하 벙커가 결합되어, 위에서 내려다보는 저격선과 아래로 숨는 벙커 동선이 공존한다.
- Interchange는 외곽 주차장/전력소/도로에서 거대 쇼핑몰 내부로 들어가는 구조다. 쇼핑몰은 매장, 에스컬레이터, 중앙홀, 지하 주차장이 연결된다.
- Shoreline은 넓은 야외를 지나 Health Resort라는 다층 실내 고위험 구조로 들어간다.
- Streets는 도로, 아파트, 호텔, 쇼핑몰, 지하/하수로, 골목, 옥내 통로가 얽혀 도심형 수직/수평 레이어를 만든다.
- Factory는 작은 공간 안에 1층, 지하, catwalk, 사무실, 계단이 압축되어 있다.

### 핵심 메커니즘

수직성은 단순히 층을 늘리는 것이 아니라 “위에서 보이는 위험”, “아래로 숨는 위험”, “계단/문에서 들키는 위험”, “건물 밖으로 나가는 순간 노출되는 위험”을 만든다.

### 디자인 의도 추정

플레이어가 한 가지 전투 리듬에 안주하지 못하게 하기 위한 설계다. 야외에서는 관측/엄폐, 실내에서는 청각/코너 체크, 지하는 길 기억과 병목 관리가 중요해진다.

### Project D 적용점

Project D의 레벨은 3인칭 액션이므로 수직성이 캐릭터 실루엣과 카메라에 잘 맞아야 한다.

- 숲: 언덕, 쓰러진 거목, 나무 위 감시대, 계곡 아래 지뢰길.
- 전쟁터: 참호 지하, 무너진 탑, 포대 고지, 지하 대피소.
- 성채: 외벽, 성문, 안뜰, 지하감옥, 마법서고, 왕좌홀.
- 오염지대: 지하 실험실, 균열난 지표, 독 안개가 낮게 깔린 저지대.
- 시야 차단물: 마차 잔해, 거대 뿌리, 시체더미, 천막, 부서진 방패벽, 오염 결정.

### 출처 링크

- [Reserve - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Interchange - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Shoreline - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Shoreline)
- [Streets of Tarkov - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)
- [Factory - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Factory)

## 7. AI Scav와 보스/강적 배치가 동선에 주는 영향

### 조사 내용

Scav는 기본적으로 모든 맵에 분포하고, 레이드 중 웨이브로 추가되며, 랜드마크나 중요 지점 주변에 머무는 경향이 있다. 단독 Scav는 큰 위협이 아니지만, 그룹/위치/소리/플레이어 상태와 결합하면 통행세 같은 역할을 한다.

보스는 특정 권역의 의미를 바꾼다.

- Customs의 Reshala는 Dorms, New Gas, Scav Base 같은 주요 충돌 지점을 강화한다.
- Woods의 Shturman은 Sawmill을 고위험/고보상 중심지로 만든다.
- Interchange의 Killa는 IDEA/OLI/Goshan/중앙 매장을 위협 권역으로 만든다.
- Reserve의 Glukhar는 병영/창고/지하 저장고 등 군사 보급 지점의 위험을 높인다.
- Shoreline의 Sanitar는 Resort, Pier, Cottages에 의료/보스 위험을 붙인다.
- Streets의 Kaban, Kollontay는 도심 일부를 강적 점령 구역처럼 만든다.

### 핵심 메커니즘

AI는 빈 공간을 채우는 잡몹이 아니라 동선을 조절하는 압력이다. Scav는 랜드마크를 통과할 때 소모전을 만들고, 보스는 특정 구역을 “갈까 말까” 고민하게 만드는 고위험 목표로 만든다.

### 디자인 의도 추정

보스 배치는 루팅 포인트와 결합되어 목표성을 만든다. “저기 가면 좋은 게 있다”와 “저기 가면 죽을 수 있다”가 같은 위치에 묶인다.

### Project D 적용점

Project D는 싱글 플레이어이므로 PvP의 예측불가능성을 감염체 AI와 지역 보스가 대신해야 한다.

- 일반 좀비: 길목, 마을, 시체더미, 보급품 주변을 느슨하게 점유.
- 특수 감염체: 소리에 반응, 문을 부숨, 지붕/나무에서 기습, 오염 장판 생성.
- 지역 보스: 벌목장 괴수, 성채 기사 감염체, 마족 실험체, 오염 늪의 마력흡수체.
- 강적은 반드시 전용 보상/열쇠/경로 단축/제작 재료와 연결한다.

### 출처 링크

- [Scavs - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Scavs)
- [Bosses - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Bosses)
- [Customs - Bosses](https://escapefromtarkov.fandom.com/wiki/Customs)
- [Woods - Bosses](https://escapefromtarkov.fandom.com/wiki/Woods)
- [Interchange - Bosses](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Reserve - Bosses](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Shoreline - Bosses](https://escapefromtarkov.fandom.com/wiki/Shoreline)
- [Streets of Tarkov - Bosses](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)

## 8. 열쇠/잠긴 방/조건부 접근이 만드는 목표성

### 조사 내용

Tarkov의 열쇠 시스템은 단순 잠금 해제가 아니라 목표의 레이어를 만든다.

- Customs Dorm 314 Marked Room은 기숙사 3층이라는 고위험 위치, 희귀 열쇠, 매우 희귀한 루팅 기대값이 결합된다.
- Interchange KIBA는 외부/내부 키가 필요하고, 쇼핑몰 중앙부라는 노출 위치와 경보/전력 시스템이 결합된다.
- ULTRA medical storage는 Interchange 2층 약국 내부의 잠긴 방이며 전력소 스위치가 켜져야 사용할 수 있다.
- Reserve는 RB 계열 열쇠가 많아 군사기지 각 건물/방을 반복 목표로 만든다.
- Shoreline Resort는 동관/서관의 방별 열쇠가 매우 많아 리조트 전체가 고위험 방 탐색 콘텐츠가 된다.
- 일부 탈출도 키/레버/장비/플레어/금전/협동 조건이 붙어 접근성을 조절한다.

### 핵심 메커니즘

열쇠는 “루팅 권한”이면서 “동선 선택권”이다. 좋은 열쇠를 얻으면 새 목표가 생기고, 새 목표는 맵 중심부로 플레이어를 다시 끌어들인다.

### 디자인 의도 추정

반복 플레이의 장기 목표를 만들기 위한 구조다. 같은 맵이라도 오늘 가진 열쇠, 장비, 퀘스트, 탈출 조건에 따라 다른 루트가 된다.

### Project D 적용점

Project D의 판타지 세계관에서는 키를 물리 열쇠뿐 아니라 다양하게 바꿀 수 있다.

- 고대 엘프 룬석: 봉인된 서고/마법 연구실 접근.
- 드워프 제작 열쇠: 무기고/대장간/승강기 작동.
- 오염 샘플: 실험실 안쪽 문 개방, 대신 감염 위험 증가.
- 보스 전리품: 성채 지하 보물실, 지름길, 탈출 장치 작동.
- 마법 지뢰 해제 도구: 위험 루트를 안전 루트로 변환.

### 출처 링크

- [Dorm room 314 marked key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Dorm_room_314_marked_key)
- [KIBA Arms inner grate door key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Kiba_Arms_inner_grate_door_key)
- [ULTRA medical storage key - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/ULTRA_medical_storage_key)
- [Reserve - Usable Keys](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Shoreline - Usable Keys](https://escapefromtarkov.fandom.com/wiki/Shoreline)

## 9. 환경 스토리텔링과 폐허/군사/도시 공간의 기능성

### 조사 내용

Tarkov의 맵 설명은 공간의 기능과 세계관을 함께 설명한다.

- Customs는 산업단지, 세관 터미널, 연료 저장고, 사무실, 기숙사 등 “물류/산업” 기능이 살아있는 폐허다.
- Woods는 자연보호구역이 전쟁과 생존의 공간으로 변한 맵이다.
- Interchange는 항구와 산업 외곽을 연결하는 교통 중심지이자 EMERCOM 대피 작전의 거점이었던 쇼핑몰이다.
- Reserve는 핵전쟁에도 버틸 만큼 보급품이 있다는 도시전설이 붙은 비밀 군사기지다.
- Shoreline은 항구 외곽의 마을/리조트/발전소/기상관측소가 섞이며, TerraGroup 관련 인물 대피 숙소였다는 배경을 가진다.
- Streets는 은행, 쇼핑몰, 호텔 등 도시 인프라가 붕괴 후에도 루팅/매복/탈출 구조로 기능한다.
- Ground Zero는 TerraGroup 본사가 있던 “사건의 시작점”이다.

### 핵심 메커니즘

환경 스토리텔링이 장식으로 끝나지 않고 루팅 종류와 위험 배치에 직접 연결된다. 병원에는 의료품, 무기점에는 무기, 은행에는 금고, 군사기지에는 탄약/보급품, 숲에는 은닉 캐시와 저격선이 어울린다.

### 디자인 의도 추정

플레이어가 “왜 여기에 이런 아이템이 있는지”를 직관적으로 받아들이게 하려는 설계다. 세계관의 설득력이 루팅 학습 속도를 높인다.

### Project D 적용점

Project D는 마법/전쟁/감염이 결합된 세계라 환경과 보상을 강하게 맞춰야 한다.

- 엘프 폐서고: 마법 이론서, 룬 파편, 디아나의 과거 단서.
- 전쟁터 야전병원: 붕대, 해독제, 오염 기록, 부패한 마력 샘플.
- 마족 실험실: 고위험 오염 재료, 변이체, 생체실험 기록.
- 드워프 작업장: 무기 개조 재료, 금속 부품, 방어구 수리 도구.
- 성채 무기고: 희귀 무기, 방패, 잠긴 보관함, 보스 순찰.
- 숲속 은둔지: 생존 식량, 약초, 함정, 자연 회복 포인트.

### 출처 링크

- [Customs - Description](https://escapefromtarkov.fandom.com/wiki/Customs)
- [Woods - Description](https://escapefromtarkov.fandom.com/wiki/Woods)
- [Interchange - Description](https://escapefromtarkov.fandom.com/wiki/Interchange)
- [Reserve - Description](https://escapefromtarkov.fandom.com/wiki/Reserve)
- [Shoreline - Description](https://escapefromtarkov.fandom.com/wiki/Shoreline)
- [Streets of Tarkov - Description](https://escapefromtarkov.fandom.com/wiki/Streets_of_Tarkov)
- [Ground Zero - Description](https://escapefromtarkov.fandom.com/wiki/Ground_Zero)

## 10. Project D의 판타지 숲/전쟁터/성채/오염지대 맵에 적용할 변환 아이디어

### 조사 내용

Tarkov식 추출형 공간 설계의 핵심은 “입장 목적, 중간 목표, 위험한 중심부, 탈출 경로, 장기 보상”을 한 레이드 안에 넣는 것이다. Project D는 싱글 플레이어이므로 PvP 대신 AI, 환경 위험, 감염, 장비 내구도, 시간 압박, 소리 유도, 동료 제작 시스템을 이용해야 한다.

### 핵심 메커니즘

Project D의 맵은 다음 4축으로 설계하면 Tarkov식 장점을 가져오면서 장르를 변환할 수 있다.

- 위험 축: 좀비 밀도, 특수 감염체, 보스, 마법 지뢰, 오염 안개, 저격/투사체 위협.
- 보상 축: 생존 자원, 제작 재료, 마법 연구 자료, 무기/방어구 부품, 해금 아이템.
- 접근 축: 열쇠, 룬, 레버, 정화 장비, 불칸 제작 도구, 시간대/날씨 조건.
- 탈출 축: 안전 야영지, 수송로, 성문, 마법진, 지하 승강기, 신호 장치.

### 디자인 의도 추정

Tarkov의 설계는 “죽으면 잃는다”는 멀티플레이 압력에 크게 기대지만, Project D는 “무리하면 더 깊이 갈 수 있지만 잃을 것도 커진다”는 싱글 플레이 의사결정으로 바꾸는 것이 적합하다.

### Project D 적용점

추천 맵 초안:

1. 움브라데 외곽 숲
   - 역할: 초반 탐색/생존/은닉 루팅 학습.
   - 핵심 랜드마크: 흰 고목, 사냥꾼 오두막, 지뢰 표식, 마른 계곡.
   - 고위험 목표: 감염 시체 무리의 둥지.
   - 탈출: 숲길 귀환, 불칸의 수레, 신호 연기.

2. 움브라데 전투 잔해
   - 역할: 마법 지뢰/전쟁 폐허/고위험 보급품.
   - 핵심 랜드마크: 무너진 포대, 참호, 부서진 깃발, 마법 지뢰밭.
   - 고위험 목표: 봉인된 야전 창고.
   - 탈출: 해제한 지뢰길, 참호 지하 통로.

3. 폐성채
   - 역할: 수직 실내 전투, 열쇠방, 보스, 중후반 루팅.
   - 핵심 랜드마크: 성문, 무너진 탑, 지하감옥, 왕좌홀.
   - 고위험 목표: 성채 무기고와 고대 서고.
   - 탈출: 성벽 리프트, 지하 수로, 마법진.

4. 마족 오염 연구지대
   - 역할: 후반 고위험 고보상, 감염 누적, 스토리 핵심.
   - 핵심 랜드마크: 폭발한 연구동, 생체 탱크, 오염 결정, 폐쇄 격리문.
   - 고위험 목표: 실험체 보스와 오염 샘플.
   - 탈출: 정화 장치 가동 후 제한 시간 탈출.

### 출처 링크

- [Looting - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Looting)
- [Transits - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Transits)
- [Bosses - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Bosses)
- [Scavs - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Scavs)
- [Locations category - Official Escape from Tarkov Wiki](https://escapefromtarkov.fandom.com/wiki/Category:Locations)

## Project D에 적용 가능한 레벨 디자인 교훈 10개

1. 맵은 테마가 아니라 목적별로 나눠라.
   - 숲은 생존/은닉, 전쟁터는 위험한 보급품, 성채는 수직 실내 루팅, 오염지대는 후반 고위험 재료처럼 역할을 분리한다.

2. 좋은 보상은 반드시 위험한 이동과 연결하라.
   - 상자 안 보상보다 “거기까지 가고, 열고, 살아서 나오는 과정”이 핵심이다.

3. 랜드마크는 기능을 가져야 한다.
   - 흰 고목은 길찾기, 성채 첨탑은 원거리 기준점, 붉은 오염탑은 위험 신호, 부서진 포대는 저격선과 루팅 지점이 되어야 한다.

4. 저위험 루팅도 반드시 필요하다.
   - 모든 보상을 고위험 중심부에 몰면 플레이어가 초반에 망가진다. 안전한 약초/식량/소재 루트가 있어야 원정 준비 루프가 산다.

5. 병목은 전투보다 선택을 만들 때 좋다.
   - 좁은 다리는 무조건 싸우는 곳이 아니라, 우회할지, 함정을 해제할지, 빠르게 돌파할지 판단하게 해야 한다.

6. 탈출 지점은 레벨 후반부 콘텐츠다.
   - 출구는 맵 끝의 문이 아니라, 조건/위험/시간/소리/장비를 요구하는 마지막 의사결정이어야 한다.

7. 열쇠는 문을 여는 아이템이 아니라 다음 원정의 목표다.
   - 룬석/보스 전리품/제작 도구가 새 방, 새 탈출, 새 지름길, 새 제작법을 열어야 한다.

8. AI는 공간의 주인처럼 배치하라.
   - 좀비를 랜덤으로 흩뿌리지 말고, 시체더미, 오염원, 보급품, 의식장, 성채 홀처럼 이유 있는 장소에 배치한다.

9. 환경 스토리텔링과 루팅 테이블을 일치시켜라.
   - 야전병원에는 의료품, 드워프 작업장에는 금속/개조 재료, 엘프 서고에는 마법 연구 자료가 나와야 플레이어가 맵을 배운다.

10. 싱글 플레이어 추출형은 PvP 대신 누적 압력으로 긴장을 만든다.
    - 감염 게이지, 장비 내구도, 소리 유도, 귀환 시간, 어두워지는 날씨, 배낭 무게, 특수 감염체 추격을 조합한다.

