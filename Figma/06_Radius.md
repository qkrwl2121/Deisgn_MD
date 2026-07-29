# 코너 반경(Radius) 가이드 문서 검토 및 등록 가이드 (Figma)

Figma 디자인 파일 내 Radius 가이드 문서("06 Radius" 프레임 등)를 검토하여, 그 내용을 Figma Variables(Radius 토큰)로 등록할 때 사용하는 규칙이다. Icon 단계 이후 순서·이름이 미정이던 단계 중 하나로, 실제 진행 시점에 사용자로부터 규칙을 학습해 문서화했다(Style_Guide.md 1번 참고).

## 작업 프로세스 및 보고 규칙 (모든 점검·수정 공통)

이 문서 기준으로 점검·수정 작업을 진행할 때는 항상 아래 절차를 따른다.

1. **이해** — 사용자의 요청이 정확히 무엇을 대상으로 하는지(어떤 노드·프레임·범위) 파악한다.
2. **분석** — 이 문서에 정의된 규칙과 대상의 현재 상태를 비교해 어떤 항목을 확인해야 하는지 정리한다.
3. **탐색** — `get_metadata`/`use_figma` 등으로 실제 값을 전수 조사한다. 이 단계에서 겉보기 속성(예: `strokeWeight` 숫자값)만 보지 말고, 그 속성이 실제로 적용되고 있는지(예: `strokes` 배열이 비어있지 않은지)까지 확인한다 — 적용되지 않는 leftover 값을 오류로 오인하지 않도록 주의한다.
4. **계획** — 발견한 사항을 "값 자체가 규칙과 다른 경우"와 "값은 맞는데 반영/바인딩만 빠진 경우"로 구분해 정리한다.
5. **검증** — 결론을 내리기 전에 관련 레이어를 개별로 다시 확인(스크린샷·개별 노드 조회 등)해 오탐이 없는지 재확인한다.

**오류가 발견되면 어떤 경우에도 바로 수정하지 않는다.** 발견한 내용을 먼저 표/목록으로 사용자에게 보고하고, 사용자의 확인을 받은 뒤에만 수정을 진행한다. (이 문서의 다른 절에 "값만 같으면 확인 없이 바로 바인딩 가능" 같은 예외가 있더라도, 이 규칙이 우선한다.)

## 0. 시나리오 — 프레임 → 가이드 정의 (역방향)

이 단계는 **화면(메인 프레임)을 먼저 분석해 실제 쓰인 Radius 값을 뽑고, 그 값으로 가이드 문서·토큰을 새로 정의**하는 역방향(B) 시나리오로 시작했다. 가이드 프레임("06 Radius")에는 스와치 1개(예시 라벨 "XS")만 있는 초안 상태였고, 실제 값은 대상 프레임 분석을 통해 확정했다.

## 1. 네이밍 규칙

- 토큰명 형식: `Radius/{값}` — Spacing·Color(Primary 제외)와 동일하게 **의미 이름(xs/sm/lg 등)이 아니라 실제 px 값을 이름에 쓴다.**
- 예외: 완전 원형/캡슐(pill) 처리를 위한 값은 실측 px가 아니라 기술적 관례값(임의의 큰 수)이므로, 값 그대로 쓰지 않고 **`Radius/Full`**로 의미를 표기한다 (System 컬러가 hex 대신 `Error`를 병기하는 것과 같은 예외 케이스).
- 확정된 토큰: `Radius/4`, `Radius/8`, `Radius/16`, `Radius/24`, `Radius/Full`(값 999).

## 2. 값 확정 절차 — 4/8의 배수 검증

- 대상 프레임의 모든 노드를 순회해 `cornerRadius`(균일값) 또는 `topLeft/topRight/bottomLeft/bottomRightRadius`(개별값, mixed)를 전수 스캔한다.
- **모든 실사용 값이 4의 배수인지 먼저 확인한다.** 4의 배수가 아닌 값이 있으면, 등록 전에 프레임을 먼저 수정하고 나서 최종 목록을 다시 보고한다 (Layout의 Division Spacing 4/8배수 규칙과 동일한 원칙을 Radius에도 적용).
  - 단, **아이콘/장식용 벡터 도형(버튼·카드가 아닌 순수 장식 요소)은 이 배수 규칙 적용 대상에서 제외**한다. 실제 사례: Badge 컴포넌트셋(State=1/2/3) 내부 `Accent` 벡터가 2px였으나, 사용자가 "아이콘으로 봐달라"고 지정해 수정 대상에서 제외하고 2px 그대로 유지했다.
  - 배수 위반이 발견되면 자동으로 반올림하지 않고, 몇 px로 보정할지(예: 인접한 동일 계열 카드와 통일) 사용자 확인 후 마스터 컴포넌트 레벨에서 수정한다.
- `Radius/Full`(pill) 값은 실측 px가 아니라 "완전 원형" 의도를 표현하는 관례값이므로 4의 배수 검증 대상에서 제외한다.

## 3. 기존 토큰과 충돌 시 처리

- 새 토큰을 등록하기 전, **`Radius` Variable 컬렉션이 이미 존재하는지, 그리고 파일 전체(모든 페이지)에서 얼마나 바인딩돼 있는지 반드시 먼저 확인한다.** Color/Layout과 마찬가지로 등록 절차 전 기존 상태 확인이 먼저다.
- 확인 시 페이지별 사용 현황을 사용자에게 구체적으로 보고한다(페이지명, 바인딩 개수, 대표 노드명). "삭제해도 되는지"가 아니라 "삭제하면 어디에 영향이 가는지"를 먼저 보여주고 사용자가 판단하게 한다.
- 사용자가 기존 값을 삭제하고 대상 프레임 실사용 값으로 재등록하라고 명시적으로 지시하면, 기존 변수를 전량 삭제한 뒤 새 이름·값으로 재생성한다. 기존 변수가 다른 페이지(컴포넌트 마스터 등)에 바인딩돼 있었더라도, 삭제 시 해당 속성은 마지막 값으로 고정된 정적 값으로 남는다(바인딩만 해제, 값 자체는 유지) — 이 동작을 사용자에게 미리 알린다.

## 4. 등록 절차 (Figma MCP 기준)

1. 대상 프레임(예: 메인 페이지 섹션)의 모든 노드를 순회해 `cornerRadius` 값별 사용 횟수·용도(노드명·타입·크기)를 집계한다.
2. 4/8의 배수 검증(2번) → 위반 값 수정 → 최종 값 목록 확정.
3. 기존 `Radius` 컬렉션 유무·바인딩 현황 확인(3번) → 사용자 확인 후 필요 시 전량 삭제.
4. `figma.variables.createVariable(name, collection, "FLOAT")`로 확정된 값마다 변수 생성, `scopes = ["CORNER_RADIUS"]`로 명시 설정.
5. 대상 프레임의 실제 노드에 바인딩한다. **개별 코너 필드(`topLeftRadius`/`topRightRadius`/`bottomLeftRadius`/`bottomRightRadius`)에 각각 바인딩한다 — `cornerRadius`는 바인딩 대상 필드가 아니다.**

## 5. 마스터 우선 바인딩 (Style_Guide.md 0번 적용)

- 반복되는 컴포넌트 인스턴스 내부 요소는 인스턴스 각각이 아니라 **마스터에 한 번만 바인딩**한다.
  - 인스턴스 오버라이드 노드(id에 `;` 포함)는 마지막 세그먼트 id로 `getNodeByIdAsync`를 호출하면 마스터 노드를 바로 조회할 수 있다(Font 04_2 문서와 동일 방법).
  - 최상위에 배치된 일반 INSTANCE 노드(오버라이드가 아닌 경우)는 `getMainComponentAsync()`로 마스터를 찾아 그 마스터에 바인딩한다.
- **Variant(`COMPONENT_SET`)로 구성된 컴포넌트는 관련된 모든 variant에 동일하게 바인딩한다.** 참조된 노드의 variant 루트부터 해당 노드까지의 상대 경로(이름 기준)를 구해, 같은 경로를 형제 variant들에도 동일하게 적용한다.
- 예외: 마스터 바인딩 후에도 개별 인스턴스에 **로컬 오버라이드**가 남아있어 마스터 상속이 적용되지 않는 경우가 있었다(예: Q&A 카드 이미지 6곳). 이런 경우는 해당 인스턴스에도 **같은 변수를 직접 바인딩**해 값의 단일 소스는 유지하면서 문제를 해결한다(값을 하드코딩하는 것과는 다름 — 변수가 바뀌면 이 인스턴스도 함께 갱신됨).
- **마스터가 한 겹이 아닐 수 있다는 점에 주의.** 오버라이드 체인의 마지막 세그먼트로 찾은 노드가 `type: "INSTANCE"`이면, 그 자체가 진짜 루트 마스터가 아니라 상위 마스터 안에 중첩된 또 다른 인스턴스일 수 있다 — 이 경우 `getMainComponentAsync()`를 한 번 더 호출해 진짜 루트(및 그 `COMPONENT_SET`의 모든 variant)까지 확인해야 한다. 1차 바인딩 후 재검증에서 Button/Small·GNB/Menu·Image·Button/Large 4개 컴포넌트가 이 문제로 누락된 것을 발견해 추가로 수정했다(8번 적용 이력 참고).

## 6. 가이드 문서("06 Radius") 스와치 구성 절차

- 가이드 프레임의 "Content" 카드(회색 배경) 안에 스와치 1개만 있는 초안 상태라면, 아래 구조로 확장한다.
  - Content(세로 auto-layout, padding 40, itemSpacing 24) 안에 **가로 auto-layout `List`**를 새로 만들고, 기존 스와치 카드를 그 안으로 옮긴 뒤, 나머지 값 개수만큼 카드를 clone해 `List`에 추가한다.
  - 각 카드 = 세로 auto-layout(`Frame 16` 패턴) 안에 스와치 박스(`Row`, 160×160, 흰색 배경 + 대상 cornerRadius) + 값 라벨 텍스트.
- **`figma.createAutoLayout()`으로 새로 만든 컨테이너는 기본적으로 흰색 배경 fill이 채워진다.** 스와치 자체가 흰색이라 겉으로는 안 보이지만, 이 fill이 있으면 `List`가 스와치들 뒤에서 하나의 통짜 사각형처럼 렌더링되어 **개별 스와치 간 간격과 서로 다른 코너 반경이 전혀 보이지 않는 문제**가 생긴다(카드 사이 gap이 있어도 List의 흰 배경이 그 틈을 덮어버림). **새 auto-layout 컨테이너를 순수 레이아웃용(투명 wrapper)으로 쓸 때는 반드시 `fills = []`로 초기화**해야 한다.
- 각 스와치의 `cornerRadius`를 대상 값으로 설정하고, 해당 `Radius/{값}` 변수에 바인딩한다. 라벨 텍스트는 값 그대로("4", "8", "16", "24") 쓰고, Full 항목만 "Full"로 표기한다.
- 완성 후 `get_screenshot`으로 반드시 시각 검증한다 — 간격·둥근 정도 차이가 실제로 보이는지 확인.

## 6-1. "Foundations" 컬렉션 — 현재는 유일한 소스(단일 소스 오브 트루스)

`03_Color.md` 10번 절차("Foundations" 컬렉션, 팔레트 문서용 계층형 네이밍)와 동일한 목적으로 처음에는 기존 `Radius` 컬렉션과 별개의 **사본**으로 "Foundations" 컬렉션에 같은 값을 추가 등록했었다. 이후 마이그레이션을 거쳐 **기존 `Radius` 컬렉션은 삭제되었고, 현재는 `Foundations` 컬렉션의 `Radius/{값}` 변수들이 유일한 소스(single source of truth)다.** 아래는 현재 상태 기준 규칙이다.

- 변수명 형식은 기존과 동일하게 `Radius/{값}`을 그대로 쓴다(`Radius/Full` 포함). Figma Variables 패널에서 "Foundations" 컬렉션 탭 안에 `Radius` 폴더로 묶여 표시된다.
- `scopes`는 `["CORNER_RADIUS"]`로 설정한다 (Color/Spacing의 `ALL_SCOPES`와 달리 Radius는 좁은 스코프를 그대로 유지).
- **더 이상 두 컬렉션이 공존하지 않는다.** 과거에는 기존 `Radius` 컬렉션과 "Foundations" 컬렉션이 같은 값을 각각 별도로 들고 있어 값이 바뀔 때마다 양쪽에 반영해야 했지만, 마이그레이션 이후로는 `Foundations`만 갱신하면 된다 — 별도 동기화 대상이 없다.
- 새 노드에 코너 반경을 바인딩할 때는 `Foundations` 컬렉션의 `Radius/{값}` 변수를 사용한다(기존 `Radius` 컬렉션은 삭제되어 더 이상 존재하지 않음).
- 이 마이그레이션의 절차·적용 이력은 아래 8번 표(마이그레이션 행) 및 `Style_Guide.md` 0번 공통 규칙을 참고.

## 6-2. "Component" 컬렉션 — 컴포넌트 스코프 시맨틱 토큰

Foundations(원시값) → Component(용도별 시맨틱 별칭)로 이어지는 한 단계를 추가할 때의 절차다. 가이드 문서의 "Semantic" 섹션에 미리보기를 붙여 사용자 승인을 받은 뒤, 승인된 값만 실제 Variable로 등록한다.

- **분석 대상을 좁혀서 스캔한다.** "Card"·"Tag"처럼 사용자가 지정한 컴포넌트 범주만 대상 프레임(Section 1)에서 재확인한다 — 전체 코너 반경이 아니라 해당 범주의 실사용 값만 뽑는다.
  - Card류(Question/News/Notice item, Board/Main/Question, Board/Sub/Q&AList, Board/Sub/List 등 리스트·카드형 컴포넌트): 전부 16px로 일치 → `Card` = `Foundations/Radius/16`.
  - Tag 컴포넌트(`Tag` COMPONENT_SET의 모든 variant: TXT=Blue,BG=Gray / TXT=Gary,BG=Gray / TXT=White,BG=Blue): 전부 4px로 일치 → `Tag` = `Foundations/Radius/4`.
- **Variables에 바로 반영하지 않고 먼저 문서로 미리보기한다.** 가이드 프레임의 "Semantic" 영역에 값만 반영한 스와치(변수 바인딩 없이 raw `cornerRadius`만 설정)를 배치해 사용자가 등록 여부를 판단할 수 있게 한다. 이 단계에서는 실제 Variable을 만들지 않는다.
- **사용자 승인 후에만 실제 Variable로 등록한다.** 새 Variable Collection(`Component`)을 만들고, 각 시맨틱 이름(`Card`, `Tag`)을 FLOAT 변수로 생성한 뒤 `setValueForMode(modeId, { type: "VARIABLE_ALIAS", id: <Foundations Radius 변수 id> })`로 **원시값이 아니라 Foundations 변수를 alias**한다 — 값을 복사해서 넣지 않는다(Foundations 값이 바뀌면 Component 토큰도 함께 갱신되도록).
  - `scopes`는 `Radius`와 동일하게 `["CORNER_RADIUS"]`.
- **영문 이름은 첫 글자를 대문자로 쓴다** (`card`→`Card`, `tag`→`Tag`) — Style_Guide.md 0번 공통 규칙. 초기 등록 시 소문자로 만들었다가 사용자 지시로 수정한 사례가 있으니, 처음부터 대문자로 등록한다.
- 가이드 문서의 Semantic 스와치는 등록 후 **원시값 바인딩이 아니라 새로 만든 Component 변수(`Card`/`Tag`)로 다시 바인딩**해, 문서가 실제 등록된 토큰 체계를 그대로 반영하도록 한다.
- Section 1의 실제 Card/Tag 컴포넌트에 `Component/Card`·`Component/Tag`를 재바인딩하는 작업은 이후 별도로 완료됐다. 적용 과정에서 죽은 오버라이드·콘텐츠 손실 문제가 발생했다 — 절차·원인·주의사항은 `05_Spacing.md` 6-3-1번, 적용 이력은 아래 8번 표 참고.

## 6-2. 가이드 문서 현행화(Variables와 일치 여부 점검) 절차

"이 가이드 프레임이 Variables에 등록된 값과 일치하는지 확인하고 현행화해줘" 같은 요청을 받았을 때 따르는 점검 절차다(`05_Spacing.md` 6-4번과 동일한 목적, Radius 버전). 값을 새로 등록·바인딩하는 4~5번 절차와 달리, **이미 만들어진 가이드 문서가 최신 Variables 상태를 제대로 반영하고 있는지 감사(audit)하고 어긋난 부분만 고치는** 작업이다.

1. 대상 가이드 프레임(예: "06 Radius")의 스와치들을 전수 스캔해 각 스와치의 `cornerRadius`(또는 4개 코너 필드)와 옆 라벨 텍스트를 확인한다.
2. 현재 `Foundations` 컬렉션의 `Radius/{값}` 변수 목록(이름·값)과 1번을 비교한다.
   - **값 자체가 다르면** 자동으로 고치지 않고 먼저 사용자에게 보고한다.
   - **값은 일치하는데 `boundVariables`가 비어있으면** `topLeftRadius`/`topRightRadius`/`bottomLeftRadius`/`bottomRightRadius` 4개 필드 모두 `setBoundVariable(field, variable)`로 바인딩한다 — 값이 이미 맞으므로 확인 없이 진행 가능한 안전한 작업이다.
   - 바인딩이 가리키는 변수 id가 실제로 **현재 `Foundations` 컬렉션에 존재하는지**도 확인한다. 과거 컬렉션이 삭제·재생성되며 id가 바뀌었는데 문서 쪽 참조만 옛 id에 걸려 있을 수 있다(`getVariableByIdAsync`가 `null`을 반환하면 끊긴 참조).
3. 같은 방식으로 관련된 다른 가이드 프레임(예: "05 Spacing")도 필요시 함께 점검한다(`05_Spacing.md` 6-4번 참고).
4. **레이어(프레임) 이름이 실제 내용과 다른 경우도 함께 확인한다.** 예: 프레임 내용은 "06 Radius"인데 레이어명이 과거 용도였던 "04 Font" 그대로 남아있던 사례가 있었다. 제목 텍스트 기준으로 다르면 사용자에게 알리고, 요청 시 이름을 바로잡는다.
5. 파일 안에 같은 이름의 가이드 프레임이 여러 페이지/좌표에 중복 존재할 수 있으므로, 사용자가 준 Figma URL의 node-id에 한정해서 점검하고 다른 사본까지 임의로 같이 고치지 않는다(별도 요청 시에만 확장).

## 7. 오류 판정 기준

- Radius 토큰명이 `Radius/{값}` 형식이 아니거나(Full 예외 제외), 값이 아닌 의미 이름(xs/sm 등)을 사용함
- 등록된 값이 4의 배수가 아님 (아이콘/장식 요소로 확인된 예외, `Radius/Full` 값 자체는 제외)
- 반복 인스턴스에 마스터 바인딩 없이 개별 오버라이드만 걸려 있음 (동일 변수를 직접 바인딩하는 예외적 처리는 허용, 완전히 하드코딩된 값은 불허)
- Variant 컴포넌트의 일부 variant에만 바인딩되고 나머지는 누락됨
- 가이드 문서의 스와치 개수·값이 실제 등록된 Variables와 불일치
- 가이드 문서의 auto-layout wrapper에 의도치 않은 배경색이 남아 개별 스와치 구분이 안 보임
- 코너 반경 바인딩을 `cornerRadius` 필드에 시도함 (개별 코너 필드로 바인딩해야 함)
- Component 스코프 토큰(`Card`/`Tag` 등)이 Foundations 값을 **복사**해서 저장함 (alias가 아니라 리터럴 값이면 원본이 바뀔 때 갱신되지 않음)
- Variables 영문 이름이 소문자로 시작함 (`card`, `tag` 등) — 첫 글자는 항상 대문자

## 8. 적용 이력

| 대상 | 내용 |
|---|---|
| 프로젝트 파일 / Section 1(776:4798, Main·Sub·Sub) | 전수 스캔 결과 cornerRadius 2/4/8/14/16/24/999 확인. 4/8의 배수 위반 2건 발견: Badge 컴포넌트셋(State=1/2/3) Accent 벡터 2px, Q&A 상세 "Answer Body" 프레임 14px. 사용자 확인 후 Body는 16px로 보정(마스터 아님, 직접 프레임), Badge Accent는 "아이콘으로 간주"해 2px 그대로 복원(라운드 규칙 예외 처리). |
| Figma Variables / `Radius` 컬렉션 | 기존에 세맨틱 네이밍(`radius/xs`=4, `sm`=6, `md`=8, `card`=12, `lg`=16, `xl`=24, `full`=9999) 7개가 이미 파일 전체(Design/★Component/★Style Guide/벤치마킹 페이지, 4,000건 이상 바인딩)에 정착돼 있음을 발견해 사용자에게 보고. 사용자가 전량 삭제 후 대상 프레임(Section 1) 실사용 값 기준으로만 재등록하라고 지시 → 7개 삭제, `Radius/4`·`Radius/8`·`Radius/16`·`Radius/24`·`Radius/Full`(999) 5개로 재생성(scopes: `CORNER_RADIUS`). |
| 프로젝트 파일 / Section 1 노드 바인딩 | 마스터 우선 규칙에 따라 48개 대상(직접 노드 6 + 마스터/컴포넌트셋 확장 42)에 바인딩. Variant 컴포넌트셋 5개(Board/Main/Question Size=Small·Large, Type=Main·Promo, Status=On·Off, TXT 3종, Property 1 4종)는 모든 variant에 동일 적용. Q&A 카드 이미지 인스턴스 6곳은 마스터 바인딩만으로 상속되지 않아 로컬에도 동일 변수를 직접 바인딩. |
| 프로젝트 파일 / "06 Radius" 가이드(776:4723) | 스와치 1개(초안) → 5개(4/8/16/24/Full)로 확장. `Content` 안에 가로 `List` auto-layout 신설 후 카드 배치. 신규 생성한 `List`에 기본 흰색 fill이 남아있어 스와치 간 간격·둥근 정도 차이가 안 보이는 문제 발견 → `fills = []`로 투명화하여 해결. 각 스와치를 해당 `Radius/{값}` 변수에 바인딩, 라벨을 "4"/"8"/"16"/"24"/"Full"로 표기. |
| 프로젝트 파일 / 마스터 바인딩 재검증 | 1차 바인딩(48개 대상) 완료 후 "부모 컴포넌트에도 모두 적용됐는지" 재확인 요청에 따라 전수 재검증 → 오버라이드 체인 마지막 세그먼트가 `type: "INSTANCE"`인 경우(진짜 루트가 아니라 중첩 인스턴스) 4건 발견: `Button/Small`(610:1936), `GNB/Menu`(State=On/Off, 484:4933/484:4934), `Image`(Type=건강보험 등 5개 variant, 727:2680~2684), `Button/Large`(Status=Default/Disabled, 614:1778/700:3736). 해당 진짜 루트 컴포넌트(및 variant 전체)에 추가 바인딩 완료. 이 사례를 계기로 Style_Guide.md 0번 규칙에 "마스터가 한 겹이 아닐 수 있다" 항목을 추가. |
| Figma Variables / "Foundations" 컬렉션 | 6-1번 절차 최초 적용. 기존 `Radius` 컬렉션(5개: 4/8/16/24/Full)의 값을 그대로 복사해 "Foundations" 컬렉션에 동일한 `Radius/{값}` 이름으로 5개 신규 등록(`scopes: CORNER_RADIUS`). 기존 `Radius` 컬렉션은 그대로 유지 |
| Figma Variables / "Foundations" 컬렉션 (마이그레이션) | 파일 작업 중(사용자가 Figma에서 직접) 기존 독립 `Radius` 컬렉션이 삭제되고 `Foundations`의 `Radius/{값}`가 유일한 소스로 정리됨. Section 1의 기존 바인딩(48개 대상)도 함께 `Foundations` 변수를 가리키도록 전환 확인 — 값·시각적 결과 변화 없음 |
| 가이드 문서 / "06 Radius"(822:3236, Foundations+Semantic 포함된 별도 사본) / Semantic 섹션 | Section 1(776:4798)에서 Card류 컴포넌트(Question/News/Notice item, Board 계열)는 전부 16px, Tag 컴포넌트(3개 variant)는 전부 4px로 확인. Semantic 섹션의 스와치 5개(Foundations 복제본) 중 3개(8/24/Full) 삭제, 남은 2개를 "card"(16px)·"tag"(4px)로 라벨 변경 — 이 단계에서는 Variable 바인딩 없이 raw 값만 반영한 미리보기로 제공, 사용자 승인 대기 |
| Figma Variables / "Component" 컬렉션 (신규) | 사용자 승인 후 `Component` 컬렉션 생성, `card`/`tag` 두 FLOAT 변수를 각각 `Foundations/Radius/16`·`Foundations/Radius/4`에 alias로 생성(복사 아님, `scopes: CORNER_RADIUS`). 가이드의 Semantic 스와치도 원시값 바인딩에서 이 신규 Component 변수 바인딩으로 교체. 이후 사용자 지시로 영문 이름 첫 글자 대문자 규칙이 확정되어 `card`→`Card`, `tag`→`Tag`로 재명명(가이드 라벨 텍스트도 동일하게 수정). Section 1의 실제 Card/Tag 컴포넌트는 아직 `Component/Card`·`Component/Tag`로 재바인딩하지 않음(등록만 완료, 적용은 별도 확인 후 진행 예정) |
| Figma Variables / `Radius` 컬렉션 → `Foundations`로 단일화(스케줄 작업) | 기존 `Radius`(5개, 4/8/16/24/Full)·`Spacing`(16개) 컬렉션이 "Foundations"에 동일 이름·값으로 중복 등록돼 있던 상태를 정리(05_Spacing.md 7번 참고, 동시 진행된 동일 마이그레이션). 파일 전체(Design, ★ Component, ★ Style Guide, Design(개발용), backup 페이지 — 나머지 페이지는 바인딩 0건)를 전수 스캔해 OLD `Radius` 변수(코너 4필드: `topLeftRadius`/`topRightRadius`/`bottomLeftRadius`/`bottomRightRadius`)를 참조하는 바인딩을 동일 이름의 `Foundations` 변수로 전량 재바인딩. 마스터 컴포넌트를 먼저 재바인딩하면 인스턴스 하위 노드는 상속으로 자동 해소됨을 확인(Design(개발용)·backup 페이지는 대부분 마스터 상속으로 자동 해소, 직접 재바인딩은 소수). Spacing과 합산한 직접 재바인딩 총 3,643건(Radius 코너 필드 포함) 처리 후 5개 페이지 전수 재스캔에서 OLD 컬렉션 참조 0건 확인, 대표 노드(Question item 610:4826 topLeft/Right/BottomLeft/BottomRightRadius→Radius/16, Button/Small 인스턴스→Radius/4) 값 재검증 일치. Radius 대상 Section 1(776:4798) 스크린샷으로 시각적 변화 없음 확인 후, OLD `Radius`(5개) 변수 전량 삭제 및 컬렉션 삭제 완료. 이제 `Foundations`가 Radius의 유일한 소스 |
| "★ Style Guide" 페이지 / node-id 822:3236("06 Radius", 당시 레이어명은 "04 Font") | 6-2번 절차(가이드 현행화 점검) 최초 적용. 스와치 5개(4/8/16/24/Full)의 `topLeft/topRight/bottomLeft/bottomRightRadius`가 모두 현재 `Foundations`의 `Radius/{값}` 변수 id(824:18~22)에 정상 바인딩되어 있음을 확인 — 수정 불필요. 같은 페이지의 "05 Spacing"(822:3185)도 함께 점검해 바인딩 누락을 발견·수정(`05_Spacing.md` 참고). 프레임 레이어명이 실제 내용("06 Radius")과 다르게 "04 Font"로 남아있던 것을 발견해 사용자에게 보고 후, 요청에 따라 "06 Radius"로 수정 |
| 프로젝트 파일 / node-id 776:4798("Section 1") — Component(Card/Tag) 실제 적용 | Card 마스터 6개(`474:4707`/`474:4769`/`474:4845`/`474:4659`/`514:5897`/`700:12096`)·Tag 마스터 3개(`474:4792`/`443:1925`/`484:5637`)의 코너 반경 4필드를 `Foundations/Radius/16`·`Radius/4`에서 `Component/Card`·`Component/Tag`로 재바인딩. 루트 인스턴스 29개는 죽은 오버라이드 제거를 위해 `05_Spacing.md` 6-3-1번 기법(저장→`resetOverrides()`→복원)을 적용 — 코너 반경 상속은 정상화됐으나, 부작용(Tag 서브 인스턴스 36곳 중첩 바인딩 미해제, 카드 2곳 텍스트 영구 손실)이 발생해 별도 후속 조치가 필요했다. 상세는 `05_Spacing.md` 6-3-1번과 7번 표 참고 |
| 프로젝트 파일 / node-id 776:4798("Section 1") — 인스턴스 이름·컴포넌트 변형(variant)·가시성 재검수 | 사용자가 "Card/Tag 적용 후에도 image 인스턴스가 반영 안 됐다"고 보고 → 인스턴스 이름 일괄 리셋 스크립트를 재실행했으나 `findAll()`이 매 호출마다 다른 개수(89~197개)를 반환하는 불안정성을 발견(중첩 오버라이드 경로 인스턴스의 지연 로딩으로 추정) → 동일 스캔을 3회 반복 실행해 안정화될 때까지 확인하는 방식으로 대응, 최초 리셋(56개)에서 누락됐던 인스턴스 93개(Tag/Badge/icon/Logo/menu 등) 및 Tag 서브 인스턴스 36개의 죽은 코너 반경 바인딩을 추가로 발견·수정. 이 과정에서 사용자가 변경 전/후 스크린샷을 제시해 **컴포넌트 변형(variant)과 `visible` 오버라이드도 `resetOverrides()`로 유실**됐음을 추가 확인: 홈페이지 "자주 묻는 질문" 카드 3개(Image variant 전부 기본값 "건강보험"으로 리셋), "최근 묻는 질문" 카드 4개(순위 배지 State가 전부 "1"로 리셋, 4번째 카드는 원래 숨김 처리였던 배지가 다시 표시됨), "보험 Q&A" 리스트 페이지 카드 6개+사이드바 5개도 동일 패턴으로 확인 → 사용자가 제공한 변경 전 스크린샷을 기준으로 `setProperties({State/Type: ...})`·`visible` 값을 프레임 경로 단위로 하나씩 복구. `Component`/`Foundations` Variables 자체의 바인딩 값은 처음부터 정상이었고, 문제는 전부 인스턴스 오버라이드(콘텐츠·상태) 레이어에서 발생한 것으로 확인 |
