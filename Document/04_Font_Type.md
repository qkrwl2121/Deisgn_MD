# Text Style Type(역할/계층) 분류 및 스타일가이드 적용 기록

`Figma/04_1Font.md`(크기·줄간격 보정 규칙), `Figma/04_2Font_Name.md`(Name 네이밍·정렬 규칙)를 기반으로 등록된 Text Style에 **Type(역할/계층)** 을 부여하고, 이를 Figma 스타일가이드 문서("03 Font", node-id `396:4508`)에 실제로 반영한 절차와 기준을 기록한다.

## 1. Type 분류 기준

- **Title**: 헤드라인, 섹션 타이틀, 카드/리스트 제목, 네비게이션·버튼 라벨, 태그/칩, 배지 등 **본문(문단)이 아닌 모든 짧은 텍스트**.
- **Sub**: 실제 문단·설명·메타정보 등 **본문으로 사용되는 텍스트**(예: 서브카피, 목록 요약문, 날짜, 약관, 안내문).
- 판단 기준은 스타일 이름이 아니라 **실제 프레임에서의 쓰임**이다. 하나의 Text Style이 라벨과 본문 양쪽에 걸쳐 쓰이는 경우, 더 빈번하거나 본질적인 쓰임(본문 여부)을 기준으로 하나의 Type만 부여한다.
  - 예: `PC_16_M`은 "인기 검색어" 라벨과 뉴스카드 요약문에 모두 쓰였으나, 실제로는 카드 요약(본문) 역할이 본질이라 **Sub**로 분류.
- 로고/워드마크 텍스트는 Type 분류 대상에서 제외한다 (`Figma/04_1Font.md` 4번 참고).

### 1-1. 혼용 스타일 판단 방법 (빈도 기준)

하나의 Text Style이 여러 문맥(라벨/버튼/태그 vs 문단/안내문/메타정보)에 걸쳐 쓰일 경우, 아래 절차로 Type을 하나만 확정한다.

1. 해당 Text Style이 바인딩된 모든 텍스트 노드를 나열하고, 각 노드를 문맥별로 **본문(Sub) 성격** 또는 **비본문(Title) 성격**으로 1건씩 분류한다.
   - 본문(Sub) 성격: 안내문·설명문·서브카피·메타정보(날짜, 저작권, 약관 등) — 완결된 문장/정보 전달이 목적
   - 비본문(Title) 성격: 헤드라인·섹션 타이틀·카드/리스트 제목·버튼·네비게이션·태그/칩·배지·폼 라벨·데이터 값 표시 등 — 짧은 라벨/트리거 성격
2. 두 성격의 **건수를 센다.** 건수가 더 많은 쪽을 채택한다. 동률이면 "더 본질적인 쓰임"(그 스타일이 화면에서 맡는 대표 역할)을 기준으로 판단하고, 이 경우 근거를 적용 이력에 남긴다.
3. 판단 결과와 근거(건수)를 반드시 적용 이력에 기록한다.

**적용 예 (etqQe4Zek7kYTq3O01U9j1 파일 검증)**

| Name | 비본문(Title) 건수 | 본문(Sub) 건수 | 결과 |
|---|---|---|---|
| `PC_16_M` | 7 (카드 조직명 4, 폼 라벨 2, 버튼 1) | 2 (placeholder 안내문 2) | **Title** (7 > 2) |
| `PC_14_M` | 10 (조직명·태그·유효기간·날짜값·체크박스/링크 라벨 등) | 2 (안내 문장 2) | **Title** (10 > 2) |
| `PC_20_R` (G9NRbcQBUYi3bkPOYle4da 파일) | 8 (Header/Footer 네비게이션 라벨 Shop/About/Promotion/Membership Card, 2개 인스턴스 × 4) | 3 (프로모션·문의·제품 소개 설명문 3건) | **Title** (8 > 3) |

## 2. Type 번호 부여 규칙

- Title, Sub 각각 **독립적으로 번호를 매긴다** (Title 1, 2, 3… / Sub 1, 2, 3…).
- 번호는 **Size 내림차순 → 동일 Size 내 Weight 내림차순**으로 부여한다 (`04_2Font_Name.md`의 정렬 규칙과 동일한 기준).
  - 즉 폰트가 크고 굵을수록 낮은 번호(Title 1에 가까움).
- 동일 Size에 여러 Weight가 있으면, 더 무거운 Weight가 더 낮은(먼저 나오는) 번호를 받는다.
  - 예: Size 20에 Bold·SemiBold가 있으면 Bold → Title 3, SemiBold → Title 4.

## 3. 스타일가이드 문서 내 행(row) 정렬 규칙

Figma 문서의 표는 아래 순서로 배치한다.

1. **Title 그룹 전체를 번호 오름차순(Title 1 → 마지막 번호)으로 먼저 나열**
2. 그다음 **Sub 그룹 전체를 번호 오름차순(Sub 1 → 마지막 번호)으로 나열**

> Text Style 패널 자체의 정렬(`04_2Font_Name.md`의 Size 내림차순)과, 스타일가이드 문서 표의 행 정렬(Title 그룹 → Sub 그룹, 각각 번호 오름차순)은 **서로 다른 기준**이니 혼동하지 않는다.

## 4. 표 컬럼별 작성 규칙

| 컬럼 | 값 | 비고 |
|---|---|---|
| Name | Text Style의 실제 이름(약어) | 예: `PC_40_B`. `04_2Font_Name.md` 네이밍 규칙 그대로 |
| Type | `Title N` 또는 `Sub N` | 위 1~2번 기준 |
| Typeface | 미리보기 텍스트 | 실제 등록된 Text Style에 **바인딩**(`setTextStyleIdAsync`)하여 스타일 변경 시 문서가 자동 반영되도록 함. 문자 내용은 브랜드명/프로젝트명이 아니라 **`프로젝트명 노출 영역`** 문구를 표준 placeholder로 사용한다 (특정 프로젝트에 종속되지 않도록) |
| Device | `PC` 등 디바이스 구분자 | Name의 Device와 동일 |
| Size | 폰트 크기(px, 숫자만) | Name의 Size와 동일 |
| Weight | Figma 폰트 Style **풀네임** | 약어 아님 (예: `SemiBold`, `Bold`) — Name은 약어를 쓰지만 표의 Weight 컬럼만 예외적으로 풀네임 사용 |
| Line Height | px 숫자만 | Text Style의 실제 lineHeight 값 |
| Spacing | %(현재 전부 `0%`) | Text Style에 등록된 letterSpacing 값 그대로. 별도 보정 공식 없음 |

## 5. Figma 반영 절차 (실제 적용 방법)

> **주의 — 템플릿은 파일마다 별도로 필요하다.** `StyleGuide_Hader` 컴포넌트는 로컬(파일 내부) 컴포넌트라 **다른 Figma 파일에서는 자동으로 재사용할 수 없다** (Plugin API로 파일 간 컴포넌트를 직접 복사할 방법이 없음, 팀 라이브러리로 퍼블리시된 경우만 `importComponentByKeyAsync`로 가져올 수 있음). 새 파일에서 작업할 때는 아래 5-A(템플릿 있음) / 5-B(템플릿 없음) 중 해당하는 절차를 따른다.

### 5-A. 템플릿 컴포넌트가 이미 파일에 있는 경우

1. 표 행 템플릿(`StyleGuide_Hader` 등, Name/Type/Typeface/Device/Size/Weight/LineHeight/Spacing 필드 포함)을 찾는다. 예시 행 인스턴스에서 `await instance.getMainComponentAsync()`로 마스터를 역추적하면 안전하다.
2. 이 마스터 컴포넌트는 표 영역 밖으로 옮기고(`visible = false`) 실제 표에는 **인스턴스만** 배치한다 — 마스터를 직접 표에 두고 편집하지 않는다.
   - 단, **다른 파일에서 복사·붙여넣기로 가져온 마스터는 read-only 내부 노드로 취급될 수 있다** (`visible`, `x`/`y` 등 속성 수정 시 "Cannot write to internal and read-only node" 에러, `parent` 체인도 페이지 트리에서 조회되지 않을 수 있음). `createInstance()` 자체는 정상 동작하므로 표 제작에는 지장이 없지만, 파일이 외부 파일에 계속 의존하는 상태로 남는다.
   - **이 파일 소유의 로컬 컴포넌트로 완전히 독립시키려면(권장):**
     1. 인스턴스 중 하나를 `instance.detachInstance()`로 분리한다 (외부 마스터와의 연결이 끊어지고 평범한 프레임이 됨. 내용·바인딩은 그대로 유지).
     2. `figma.createComponentFromNode(detachedFrame)`으로 분리된 프레임을 **이 파일의 새 로컬 컴포넌트**로 변환한다.
     3. 이 새 마스터는 표에서 빼내어 문서 상단(예: `Con`의 첫 번째 자식으로 `insertChild(0, ...)`)에 "Master Component (source)" 같은 라벨과 함께 배치해 눈에 보이게 둔다 — 더 이상 숨길 필요 없음, 이제 이 파일이 소유한 노드라 자유롭게 수정 가능.
     4. 나머지 행들은 삭제 후, 새 로컬 마스터의 `createInstance()`로 다시 만들어 데이터를 채운다.
     5. 검증: 새 마스터의 `parent` 체인이 `Document`까지 정상적으로 조회되는지, `visible` 등 속성이 에러 없이 쓰기 가능한지 확인 — 정상이면 외부 의존성이 완전히 해소된 것.
3. 등록된 Text Style 개수만큼 `component.createInstance()`로 인스턴스를 생성해 표 컨테이너(auto-layout 세로 스택)에 `appendChild`.
4. 각 인스턴스의 필드를 채운다.
   - Name/Type/Device/Size/Weight/LineHeight/Spacing 텍스트는 `loadFontAsync`로 해당 필드의 폰트를 로드한 뒤 `characters`를 직접 수정.
   - Typeface 미리보기 텍스트는 대상 Text Style의 `fontName`을 `loadFontAsync`로 로드한 뒤 `setTextStyleIdAsync(style.id)`로 바인딩(문자 내용은 수정하지 않고 스타일만 적용).
5. 정렬 규칙(3번)에 맞는 순서로 인스턴스를 `appendChild` 재호출하여 행 순서를 재배치(Figma는 append 순서 = 화면상 표시 순서).

### 5-B. 템플릿 컴포넌트가 파일에 없는 경우 (신규 파일)

디자이너가 원본 템플릿(예: 프로젝트 파일의 `StyleGuide_Hader`)을 대상 파일에 직접 복사해 붙여넣어 주면 5-A 절차를 그대로 쓸 수 있다. 그렇지 않으면 아래 스펙으로 표를 처음부터 생성한다 (기존 템플릿과 시각적으로 유사하되 완전히 동일하지는 않음).

- 표 컨테이너: `figma.createAutoLayout("VERTICAL")`, 행 간격(itemSpacing) 20px 내외
- 각 행: `figma.createAutoLayout("HORIZONTAL")`, 컬럼 간격(itemSpacing) 24px, 컬럼 폭은 `Name 130 / Type 90 / Typeface 300(가변 가능) / Device 70 / Size 60 / Weight 110 / Line Height 100 / Spacing 80`(px) 기준
- 라벨 텍스트(Name/Type/Device/Size/Weight/Line Height/Spacing): Pretendard Regular 또는 Medium, 14px
- Typeface 셀: 문자 내용은 **`프로젝트명 노출 영역`** 고정(브랜드명 등 특정 프로젝트 문구 금지), 실제 Text Style에 `setTextStyleIdAsync`로 바인딩
- 헤더 행: 컬럼명 텍스트(Pretendard SemiBold, 14px) + 하단 구분선(strokeBottomWeight)
- **주의**: 이 5-B 절차는 최소 기능(정보 정확성)을 보장할 뿐 브랜드 비주얼(정확한 컬러 토큰, 폰트 크기, 구분선 두께 등)은 원본 템플릿과 다를 수 있다. 완전히 동일한 비주얼이 필요하면 원본 템플릿을 대상 파일에 붙여넣어 5-A로 진행해야 한다.

### 5-C. 공통 검증

완료 후 각 행의 Name 기준으로 실제 Text Style 값(fontSize/fontName.style/lineHeight)과 표 텍스트 값이 일치하는지, Typeface의 `textStyleId`가 올바른 스타일을 가리키는지 전수 검증한다.

### 5-D. 대형 사이즈 Typeface 프리뷰 캡핑 (셀 높이 초과 시)

Typeface 미리보기 셀은 폭이 고정(예: 395px)되고 높이만 자동으로 늘어나는 텍스트 노드다. 등록된 Text Style의 `fontSize`가 크면(대략 100px 이상) 고정 폭 안에서 글자 단위로 줄바꿈되며 행 높이가 수백~수천 px까지 폭증해 표 전체 레이아웃이 깨질 수 있다.

- **감지 기준**: Typeface 노드의 실제 렌더 높이(`node.height`)가 약 260px를 넘는 경우.
- **처리 절차**:
  1. Typeface 텍스트는 기존과 동일하게 실제 Text Style에 `setTextStyleIdAsync`로 바인딩한다 (패밀리·굵기는 계속 스타일과 연동 유지).
  2. 바인딩 후 `fontSize`만 로컬로 오버라이드해 4px 단위 등으로 점진적으로 낮추면서, 매번 `node.height`를 재측정해 목표 높이(약 240px, 허용 상한 약 260px)에 도달할 때까지 반복한다.
  3. `lineHeight`도 낮아진 `fontSize` 기준으로 `04_1Font.md`의 4pt 보정 공식(`Math.round(fontSize*1.5/4)*4`, 단위 PIXELS)에 맞춰 함께 갱신한다.
  4. 이 오버라이드는 **미리보기 셀에만** 적용한다. 실제 등록된 Text Style 값이나 본문(main 프레임 등)에 쓰인 폰트 크기는 변경하지 않는다.
  5. 표를 감싸는 최상위 프레임이 auto-layout이 아닌 경우(`layoutMode: NONE`), 행 높이 조정 후 자식 노드들의 최대 bottom(`y + height`) + 여백(기본 100px)으로 프레임 `height`를 수동 계산해 `resize`한다. 표 행 스택·`Con` 등 auto-layout 컨테이너는 자식이 줄어들면 자동으로 줄어들므로 별도 처리가 필요 없다.

## 6. Weights 섹션(02_weights) 동기화

- 표 상단 "Weights" 설명·샘플은 **실제 등록된 Text Style에서 쓰이는 굵기만** 나열한다.
- 로고 전용으로만 쓰이던 굵기(예: ExtraBold)는 로고 스타일 삭제와 함께 샘플에서 제외한다.
- 새로 쓰이게 된 굵기가 있으면 샘플 텍스트("Pretendard")를 해당 굵기로 복제 추가하고, 설명 문구("Regular, Medium, SemiBold, Bold를 사용합니다." 형태)를 갱신한다.

## 7. 오류 판정 기준

- Title/Sub 번호가 Size 내림차순·Weight 내림차순 규칙과 어긋남
- 표의 행 순서가 "Title 그룹(번호순) → Sub 그룹(번호순)" 순서를 따르지 않음
- 로고로 분류된 텍스트가 표에 포함되어 있거나 Type이 부여되어 있음
- Typeface 미리보기 셀이 실제 Text Style에 바인딩되어 있지 않음(수동으로 값만 맞춰놓은 상태)
- Weight 컬럼이 약어로 표기됨(약어는 Name에만 허용)
- Name/Size/Weight/Line Height 표시값이 실제 등록된 Text Style 값과 다름
- 02_weights 섹션에 실제 미사용 굵기가 남아있거나, 실제 사용 굵기가 누락됨
- 혼용 스타일(라벨/버튼 vs 본문 양쪽에 쓰이는 스타일)의 Type을 건수 비교 없이 임의로 정함, 또는 판단 근거(건수)를 적용 이력에 기록하지 않음
- Typeface 미리보기 셀 높이가 비정상적으로 커서(약 260px 초과) 표 레이아웃이 깨짐 — 대형 사이즈 스타일의 프리뷰가 5-D 절차로 캡핑되지 않음

## 8. 적용 이력

| 대상 | 내용 |
|---|---|
| 프로젝트 파일 / node-id 396:4508 ("03 Font") | Title 1~12, Sub 1~4 총 16행 생성 및 바인딩 완료. 마스터 컴포넌트(`StyleGuide_Hader`, 5-A 절차)는 프레임 밖으로 이동 후 숨김 처리 |
| 02_weights | Bold 샘플 추가, 설명 문구를 4개 굵기(Regular/Medium/SemiBold/Bold) 기준으로 갱신 |
| Type 매핑 (프로젝트 파일) | Title: `PC_40_B`(1) · `PC_32_SB`(2) · `PC_20_B`(3) · `PC_20_SB`(4) · `PC_18_SB`(5) · `PC_18_M`(6) · `PC_16_SB`(7) · `PC_14_B`(8) · `PC_14_SB`(9) · `PC_12_B`(10) · `PC_12_SB`(11) · `PC_12_M`(12) / Sub: `PC_16_M`(1) · `PC_16_R`(2) · `PC_14_R`(3) · `PC_12_R`(4) |
| 테스트 파일 / node-id 6:145 ("03 Font") | 최초엔 템플릿 없어 5-B로 임시 제작 → 사용자가 프로젝트 파일의 "04" 프레임을 직접 복사해 붙여넣어줌 → 5-A로 재제작 → 이후 detach + `createComponentFromNode`로 이 파일 소유의 로컬 마스터로 완전 독립시킴(외부 파일 의존 해소). Title 1~6, Sub 1~3 총 9행, 새 마스터는 문서 상단에 라벨과 함께 노출 |
| Type 매핑 (테스트 파일) | Title: `PC_32_SB`(1) · `PC_18_SB`(2) · `PC_16_SB`(3) · `PC_16_M`(4, 빈도 판단) · `PC_14_SB`(5) · `PC_14_M`(6, 빈도 판단) / Sub: `PC_16_R`(1) · `PC_14_R`(2) · `PC_12_SB`(3) |
| 테스트 파일(G9NRbcQBUYi3bkPOYle4da) / node-id 1:432 ("04 Font") | 템플릿(`StyleGuide_Hader`)이 외부 파일에서 붙여넣어진 read-only 마스터였음을 확인 → detach + `createComponentFromNode`로 즉시 로컬 마스터로 독립시킨 뒤 5-A로 진행. Title 1~10, Sub 1~5 총 15행 생성·바인딩. 대형 사이즈 스타일(`PC_240_M`/`160_SB`/`140_SB`/`120_SB`) 프리뷰가 고정폭 셀에서 글자 단위로 줄바꿈되며 행 높이가 최대 1200px까지 폭증하는 문제 발견 → 5-D 절차로 해결(`PC_160_SB`/`140_SB`/`120_SB` 프리뷰 fontSize를 84로 캡핑, 높이 약 256px로 정리; `PC_240_M`은 이미 184px로 정상 범위). 최상위 프레임(`1:432`) height를 3196→4662px로 재조정해 하단 여백 100px 확보 |
| Type 매핑 (테스트 파일 G9NRbcQBUYi3bkPOYle4da) | Title: `PC_240_M`(1) · `PC_160_SB`(2) · `PC_140_SB`(3) · `PC_120_SB`(4) · `PC_60_B`(5) · `PC_60_SB`(6) · `PC_26_B`(7) · `PC_20_R`(8, 빈도 판단 8:3) · `PC_18_R`(9) · `PC_16_B`(10) / Sub: `PC_40_R`(1) · `PC_24_R`(2) · `PC_20_L`(3) · `PC_16_L`(4) · `PC_14_R`(5) |
