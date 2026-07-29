# 레이아웃(그리드) 적용 절차 및 기록

`Figma/02_Layout.md`(그리드 원칙)를 기반으로, 실제 프레임을 분석해 스타일 가이드에 등록하고 적용한 절차와 이력을 기록한다.

> Division Spacing(여백·간격) 관련 절차·이력은 `Figma/05_Spacing.md`로 분리되어 있다.

## 1. 절차 개요

1. 대상 메인 프레임(예: 361:2446 "Main")의 실제 `layoutGrids`를 스캔해 분석한다.
2. 결과를 가이드 문서("02 Layout" 프레임)의 `01_Grid` 섹션과 비교한다.
3. 가이드 문서에 불일치가 있으면(설명 텍스트와 실제 도형 수치가 다른 경우 등) 실제 프레임 값을 기준으로 가이드 문서를 수정한다.
4. 분석된 값을 Figma Grid Style(`PC_12C`)로 등록하고, 대상 프레임에 연결한다.
5. 전체 과정과 결과를 아래 "적용 이력"에 기록한다.

## 2. Figma 반영 방법

- **Grid Style**: `figma.createGridStyle()`로 생성 후 `node.gridStyleId`로 대상 프레임에 연결한다. 스타일 값은 `Figma/02_Layout.md` 1번 규칙(COLUMNS, count 12, gutterSize 24, offset 360, STRETCH)을 그대로 따른다.
- 기존에 규칙에 맞지 않는 스타일이 있으면 전량 삭제 후 재등록한다.
- 가이드 문서 자체의 수치가 실제 프레임과 어긋나 있으면(캐시된 `get_metadata` 결과와 라이브 값이 다를 수 있음에 주의), 라이브 노드 값을 기준으로 가이드 문서의 좌표·라벨 텍스트를 함께 수정한다.

## 3. 적용 이력

| 대상 | 내용 |
|---|---|
| 프로젝트 파일 / node-id 361:2446 ("Main") | 실제 그리드(COLUMNS, count 12, gutterSize 24, offset 360)를 전수 분석. 컬럼 분할이 4/8/3/12컬럼 단위(최근 묻는 질문 4col·자주 묻는 질문 8col, Main banner 8col·Quick 4col, News item 3×4col, Notice item 4×3col)로 정확히 재사용되고 있음을 확인 |
| 프로젝트 파일 / node-id 610:5082 ("02 Layout" 가이드) | Grid(PC) 섹션이 실제 값과 불일치 확인 — 그리드는 1280px 기준(컬럼 84.67px)으로 그려져 있었는데 설명 텍스트는 1200px로 남아 있었고, 거터 라벨 하나는 오타값 "2334"였음. 361:2446 실측값(1200px 컨텐츠, 78px 컬럼, 24px 거터) 기준으로 컬럼 좌표·폭, 상단 치수 라벨("1200px"), 거터 라벨을 정정 |
| Figma Grid Styles | `PC_12C` 스타일 등록(COLUMNS, count 12, gutterSize 24, offset 360, STRETCH), 361:2446에 연결(`gridStyleId`). 테스트로 삭제 후 동일 값으로 재등록 확인 완료 |
| 테스트 파일(bIyDhzsS9vim4jsSc8BDcn) / node-id 0:59 ("Ctype_01App_14") | 실제 `layoutGrids` 확인 결과 COLUMNS, count 6, gutterSize 16, offset 20 (360px 모바일 화면) — "02 Layout" 가이드(8:194)의 Grid 섹션은 PC 기준(1920/12컬럼/78px/거터24)으로만 되어 있어 근본적으로 불일치. 사용자에게 확인한 결과 "PC 섹션을 Mobile 값으로 교체" 선택 → 라벨("Grid (PC)"→"Grid (Mobile)")·설명 텍스트(기준 해상도 360, 컨텐츠 320px, 6Columns, Gutter 16px) 갱신, 컬럼 다이어그램을 12→6개로 재작도(실제 40px 폭·16px 거터로 1:1 스케일, 1920 캔버스 중앙 정렬), 기존 PC용 치수 라벨 장식 요소는 제거 |
| Figma Grid Styles (테스트 파일) | `Mobile_6C` 스타일 신규 등록(COLUMNS, count 6, gutterSize 16, offset 20, STRETCH), 0:59에 연결(`gridStyleId`) |
| 프로젝트 파일 / Header(GNB, 484:4897)·Footer(514:6033) 마스터 컴포넌트 | Variables 바인딩 작업 중, 여러 프레임에 반복 배치된 Header/Footer 인스턴스에 **인스턴스별로 개별** 바인딩되어 있던 것을 발견 — 마스터가 아닌 인스턴스에 바인딩하면 마스터 변경이 전파되지 않아 Variables를 쓰는 의미가 없다는 사용자 피드백에 따라 재작업(각 인스턴스의 `getMainComponentAsync()`로 원본을 찾아 마스터 쪽에 재바인딩, 인스턴스의 로컬 오버라이드는 해제). 이 사례를 계기로 `Style_Guide.md` 0번 공통 규칙에 "인스턴스가 아닌 마스터에 바인딩" 원칙을 추가(Grid Style 자체에는 해당 사례가 직접 적용되지 않았으나, 같은 파일에서 작업하며 함께 발견됨. 실제 Spacing Variables 재바인딩 상세는 `05_Spacing.md` 참고) |
