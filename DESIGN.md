---
version: alpha
name: insurance-archive-design-analysis
description: "블루/네이비(#418dff/#25468f) 단일 브랜드 축 위에 세운 모바일 퍼스트, 카드 기반 B2B 지식 포털. 2026-07-29 디자이너 Figma 스타일가이드(fileKey HiZkjwReW7N7ajS1DPOUTP)를 기준으로 구 청록(#1BABB4) 브랜드에서 전면 리브랜딩했다. 토큰 체계는 Foundations(팔레트 원색 스케일)와 Semantic(용도별 별칭) 2층 구조로 바뀌었고, 키 이름도 Figma 원본 명명(Primary/Point → primary-point, Font/Strong → font-strong 등)을 그대로 따른다. 카드 radius 는 12px→16px(Figma 지정값), 타이포는 ExtraBold(800)이 새 스케일에 없어 Bold(700)가 최고 굵기로 낮아졌다. success/warning/chart 팔레트는 Figma 스타일가이드에 정의가 없어 Foundations 의 Functional 색상에서 동일한 tint 공식(color·N = white·(1-N/100) + base·N/100)으로 추론했다 — 사람 승인 완료, 디자이너 확인 대기 항목은 Known Gaps 참조."

colors:
  gray-01: "#2d2d2d"

  blue-10: "#eaedf4"
  blue-20: "#d3dae9"
  blue-30: "#bec8de"
  blue-40: "#a8b5d2"
  blue-50: "#91a2c6"
  blue-60: "#7c90bc"
  blue-70: "#677eb1"
  blue-80: "#516ba5"
  blue-90: "#3b599b"
  blue-100: "#25468f"

  navy-10: "#e8e9ec"
  navy-20: "#d0d3d9"
  navy-30: "#babdc6"
  navy-40: "#a2a7b2"
  navy-50: "#8a909e"
  navy-60: "#737b8c"
  navy-70: "#5c6579"
  navy-80: "#454f65"
  navy-90: "#2e3953"
  navy-100: "#16233f"

  sky-10: "#ecf4ff"
  sky-20: "#d9e8ff"
  sky-30: "#c6ddff"
  sky-40: "#b3d1ff"
  sky-50: "#a0c6ff"
  sky-60: "#8dbbff"
  sky-70: "#7aafff"
  sky-80: "#67a4ff"
  sky-90: "#5498ff"
  sky-100: "#418dff"

  functional-red: "#ff453a"
  functional-orange: "#ffbb3a"
  functional-yellow: "#cdff3a"
  functional-green: "#56ff3a"
  functional-teal: "#3aff94"
  functional-cyan: "#3af4ff"
  functional-blue: "#3a7eff"
  functional-indigo: "#6c3aff"
  functional-purple: "#e33aff"
  functional-pink: "#ff3aa5"

  neutral-1a1a1a: "#1a1a1a"
  neutral-444444: "#444444"
  neutral-666666: "#666666"
  neutral-999999: "#999999"
  neutral-cccccc: "#cccccc"
  neutral-dddddd: "#dddddd"
  neutral-eeeeee: "#eeeeee"

  cool-neutral-10: "#f6f7fa"
  cool-neutral-20: "#e4e5e7"
  cool-neutral-30: "#c9cbcf"
  cool-neutral-40: "#afb1b6"
  cool-neutral-50: "#94979e"
  cool-neutral-60: "#797d86"
  cool-neutral-70: "#61646b"
  cool-neutral-80: "#494b50"
  cool-neutral-90: "#303236"
  cool-neutral-100: "#18191b"

  white-10: "#ffffff1a"
  white-20: "#ffffff33"
  white-30: "#ffffff4d"
  white-40: "#ffffff66"
  white-50: "#ffffff80"
  white-60: "#ffffff99"
  white-70: "#ffffffb2"
  white-80: "#ffffffcc"
  white-90: "#ffffffe5"
  white-100: "#ffffff"

  line-01: "#d6d7db"

  primary-normal: "{colors.blue-100}"
  primary-heavy: "{colors.navy-100}"
  primary-point: "{colors.sky-100}"

  font-strong: "{colors.neutral-1a1a1a}"
  font-secondary: "{colors.neutral-444444}"
  font-tertiary: "{colors.neutral-666666}"
  font-subtle: "{colors.neutral-999999}"
  font-disabled: "{colors.neutral-999999}"
  font-white: "{colors.white-100}"

  label-bg-normal: "{colors.blue-10}"
  label-bg-heavy: "{colors.blue-50}"
  label-bg-sky: "{colors.sky-100}"
  label-font-normal: "{colors.neutral-444444}"
  label-font-blue: "{colors.blue-100}"
  label-font-white: "{colors.white-100}"

  background-normal: "{colors.white-100}"
  background-point: "{colors.cool-neutral-10}"
  background-disabled: "{colors.neutral-dddddd}"
  background-heavy: "{colors.blue-80}"

  line-normal: "{colors.neutral-dddddd}"
  line-neutral: "{colors.neutral-eeeeee}"
  line-heavy: "{colors.neutral-cccccc}"

  system-error: "{colors.functional-red}"

  success: "{colors.functional-green}"
  success-bg: "#eeffeb"
  danger: "{colors.functional-red}"
  danger-bg: "#ffeceb"
  warning: "{colors.functional-orange}"
  warning-bg: "#fff8eb"
  overlay-scrim: "#000000"

  chart-1: "{colors.sky-100}"
  chart-2: "{colors.blue-100}"
  chart-3: "{colors.sky-40}"
  chart-4: "{colors.navy-100}"
  chart-5: "{colors.sky-20}"
  chart-6: "{colors.functional-green}"
  chart-grid: "{colors.neutral-eeeeee}"

typography:
  FONT_TIT_T_SB_32:
    fontFamily: Pretendard
    fontSize: 32px
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: -2px
    fontFeature: kern
  FONT_TIT_T_SB_20:
    fontFamily: Pretendard
    fontSize: 20px
    fontWeight: 600
    lineHeight: 1.40
    letterSpacing: 0px
    fontFeature: kern
  FONT_BODY_B_R_18:
    fontFamily: Pretendard
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: 0px
    fontFeature: kern
  PC_40_B:
    fontFamily: Pretendard
    fontSize: 40px
    fontWeight: 700
    lineHeight: 1.50
    letterSpacing: 0px
    fontFeature: kern
  PC_32_SB:
    fontFamily: Pretendard
    fontSize: 32px
    fontWeight: 600
    lineHeight: 1.50
    letterSpacing: 0px
    fontFeature: kern
  PC_20_B:
    fontFamily: Pretendard
    fontSize: 20px
    fontWeight: 700
    lineHeight: 1.60
    letterSpacing: 0px
    fontFeature: kern
  PC_20_SB:
    fontFamily: Pretendard
    fontSize: 20px
    fontWeight: 600
    lineHeight: 1.60
    letterSpacing: 0px
    fontFeature: kern
  PC_18_SB:
    fontFamily: Pretendard
    fontSize: 18px
    fontWeight: 600
    lineHeight: 1.55
    letterSpacing: 0px
    fontFeature: kern
  PC_18_M:
    fontFamily: Pretendard
    fontSize: 18px
    fontWeight: 500
    lineHeight: 1.55
    letterSpacing: 0px
    fontFeature: kern
  PC_16_SB:
    fontFamily: Pretendard
    fontSize: 16px
    fontWeight: 600
    lineHeight: 1.50
    letterSpacing: 0px
    fontFeature: kern
  PC_16_M:
    fontFamily: Pretendard
    fontSize: 16px
    fontWeight: 500
    lineHeight: 1.50
    letterSpacing: 0px
    fontFeature: kern
  PC_16_R:
    fontFamily: Pretendard
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0px
    fontFeature: kern
  PC_14_B:
    fontFamily: Pretendard
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.43
    letterSpacing: 0px
    fontFeature: kern
  PC_14_M:
    fontFamily: Pretendard
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.43
    letterSpacing: 0px
    fontFeature: kern
  PC_14_R:
    fontFamily: Pretendard
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.43
    letterSpacing: 0px
    fontFeature: kern
  PC_12_B:
    fontFamily: Pretendard
    fontSize: 12px
    fontWeight: 700
    lineHeight: 1.67
    letterSpacing: 0px
    fontFeature: kern
  PC_12_SB:
    fontFamily: Pretendard
    fontSize: 12px
    fontWeight: 600
    lineHeight: 1.67
    letterSpacing: 0px
    fontFeature: kern
  PC_12_M:
    fontFamily: Pretendard
    fontSize: 12px
    fontWeight: 500
    lineHeight: 1.67
    letterSpacing: 0px
    fontFeature: kern
  PC_12_R:
    fontFamily: Pretendard
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.67
    letterSpacing: 0px
    fontFeature: kern
  code-badge:
    fontFamily: mono
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.67
    letterSpacing: 0px
    fontFeature: kern

rounded:
  4: 4px
  8: 8px
  16: 16px
  24: 24px
  999: 999px
  card: "{rounded.16}"
  tag: "{rounded.4}"

spacing:
  4: 4px
  8: 8px
  12: 12px
  16: 16px
  20: 20px
  24: 24px
  28: 28px
  32: 32px
  40: 40px
  48: 48px
  60: 60px
  64: 64px
  72: 72px
  80: 80px
  100: 100px
  120: 120px

components:
  button-primary:
    backgroundColor: "{colors.primary-point}"
    textColor: "{colors.font-white}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.8}"
    padding: 8px 12px
  button-primary-hover:
    backgroundColor: "{colors.primary-normal}"
    textColor: "{colors.font-white}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.8}"
    padding: 8px 12px
  button-ghost:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.8}"
    padding: 8px 12px
  input:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.8}"
    padding: 8px 12px
  card:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.card}"
    padding: 16px
  qa-card:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-strong}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_16_SB}"
    rounded: "{rounded.card}"
    padding: 16px
  insurer-card:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-strong}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.card}"
    padding: 16px
  solve-card:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.label-bg-heavy}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.card}"
    padding: 16px
  stat-card:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-strong}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.card}"
    padding: 16px
  badge-category:
    backgroundColor: "{colors.label-bg-normal}"
    textColor: "{colors.primary-normal}"
    typography: "{typography.PC_12_B}"
    rounded: "{rounded.999}"
    padding: 2px 10px
  freshness-badge-fresh:
    backgroundColor: "{colors.success-bg}"
    textColor: "{colors.success}"
    typography: "{typography.PC_12_B}"
    rounded: "{rounded.999}"
    padding: 2px 10px
  freshness-badge-stale:
    backgroundColor: "{colors.danger-bg}"
    textColor: "{colors.danger}"
    typography: "{typography.PC_12_B}"
    rounded: "{rounded.999}"
    padding: 2px 10px
  category-chip:
    backgroundColor: "{colors.label-bg-normal}"
    textColor: "{colors.primary-normal}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.999}"
    padding: 4px 12px
  tab-filter-active:
    backgroundColor: "{colors.primary-point}"
    textColor: "{colors.font-white}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.999}"
    padding: 4px 12px
  tab-filter-inactive:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.999}"
    padding: 4px 12px
  pagination-item:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.8}"
    size: 36px
  ranking-table-header:
    backgroundColor: "{colors.label-bg-normal}"
    textColor: "{colors.primary-normal}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.4}"
    padding: 10px 12px
  quick-link-tile:
    backgroundColor: "{colors.label-bg-normal}"
    textColor: "{colors.primary-normal}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.999}"
    padding: 4px 12px
  header-nav:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.primary-point}"
    typography: "{typography.PC_12_B}"
    rounded: "{rounded.4}"
    height: 56px
  hero-banner:
    backgroundColor: "{colors.primary-point}"
    textColor: "{colors.font-white}"
    typography: "{typography.FONT_TIT_T_SB_32}"
    rounded: "{rounded.card}"
    padding: 40px 24px
  fab:
    backgroundColor: "{colors.primary-point}"
    textColor: "{colors.font-white}"
    typography: "{typography.PC_14_B}"
    rounded: "{rounded.999}"
    size: 56px
  modal:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-secondary}"
    borderColor: "{colors.line-normal}"
    typography: "{typography.PC_14_R}"
    rounded: "{rounded.card}"
    padding: 16px 20px
  toast:
    backgroundColor: "{colors.font-strong}"
    textColor: "{colors.font-white}"
    typography: "{typography.PC_14_M}"
    rounded: "{rounded.8}"
    padding: 10px 16px
  footer:
    backgroundColor: "{colors.background-normal}"
    textColor: "{colors.font-subtle}"
    typography: "{typography.PC_12_R}"
    borderColor: "{colors.line-normal}"
    rounded: "{rounded.4}"
    padding: 24px 16px
---

## Overview

핀게이트 보험 아카이브는 보험 설계사를 위한 데일리 지식 포털이다. **2026-07-29, 디자이너가 공유한 Figma
스타일가이드(fileKey `HiZkjwReW7N7ajS1DPOUTP`, "Style Guide" 페이지)를 기준으로 토큰 체계를 전면
재생성**했다 — 이전 버전(청록 `#1BABB4` 단일축, flat 1층 토큰)은 git 이력에 남아 있다.

시스템의 골격은 이전과 동일하게 세 가지로 요약된다: **흰 카드 그리드**, **블루 단일 포인트**, **고대비
타이포**. 다만 각 층의 값과 이름이 바뀌었다. 모든 콘텐츠는 `{components.card}` — radius
`{rounded.card}`(16px, 기존 12px에서 상향), 1px `{colors.line-normal}` 보더, 이중 미세 그림자 — 위에
얹히고, 페이지 배경 `{colors.background-point}`와의 대비만으로 위계가 성립한다. 포인트 컬러는
`{colors.primary-point}`(#418dff, Sky/100) 하나이며 primary 버튼, 활성 탭, 헤더 하단 2px 라인, FAB, 코드
칩(mono), PWA theme-color·앱 아이콘 배경까지 관통한다. hover는 `{colors.primary-normal}`(#25468f, Blue/100 —
버튼 hover)와 `{colors.label-bg-normal}`(#eaedf4 — 면 hover)의 두 갈래로 통일된다.

타이포는 Pretendard 단일 패밀리를 유지하지만 **스케일 자체가 바뀌었다** — Figma 스타일가이드에는
ExtraBold(800)가 없다. 이전 시스템의 정체성이던 "bold/extrabold로 위계를 끈다"는 원칙은 이제 **최고
굵기가 Bold(700)**로 낮아진 상태로 재해석해야 한다(Typography § Migration 참조). 상태 표현은 신선도
뱃지(fresh=`{colors.success}` / stale=`{colors.danger}`)와 피드백(검토중=`{colors.warning}`)의 파스텛
배경+진한 텍스트 페어를 유지하되, 세 색 모두 **Figma 미정의 — Foundations Functional 색상에서 tint
공식으로 추론**한 값이다(Known Gaps 참조, 디자이너 확인 대기).

레이아웃(최대폭 1152px, sm 분기 중심 모바일 퍼스트)과 컴포넌트 구조는 색·타이포 값 변경과 독립적이라
그대로 유지된다.

**Key Characteristics (갱신):**
- 단일 브랜드 축: `{colors.primary-point}`(#418dff) → hover `{colors.primary-normal}`(#25468f) → 다크
  변형 `{colors.primary-heavy}`(#16233f)의 3단 블루 계열이 인터랙션 전체를 지배. 청록 단일축은 폐기.
- 카드 표준: `{rounded.card}` **16px**(기존 12px) + `{colors.line-normal}` 1px + 이중 미세 그림자 + 내부
  패딩 `{spacing.16}`. 버튼·인풋·탭 등 컨트롤류는 `{rounded.8}` — "컨트롤 8px / 카드 16px" 2단 규칙 유지,
  절대값만 상향.
- 타이포 압축: 기존 18개 시맨틱 역할이 Figma 원본 스케일(19종, ExtraBold 없음)에 재매핑되며 다수가
  합쳐졌다 — 예: `nav-tab`·`caption-bold`·`micro`가 전부 `PC_12_B`로 수렴. 상세는 Typography § Migration.
- 상태 뱃지 5 variant(blue/green/orange/red/gray)는 유지되나 green/orange/red 세 값은 디자이너 확인
  대기 상태(Known Gaps).
- 선택 = 반전, hover = 틴트 원칙은 유지 — 적용 색만 블루 축으로 교체.
- 그라디언트 홈 히어로 1곳, 그림자 2단계(`shadow-fg`/`shadow-fg-md`) 원칙 유지.
- 데이터 주도 색상(보험사 brand_color)은 로고 칩 폴백에만 허용 — 정책 유지.

## Colors

> 근거: Figma 스타일가이드(fileKey `HiZkjwReW7N7ajS1DPOUTP`, 노드 `0:510`·`0:410`) — Foundations(`03-1`)
> + Semantic(`03-2`). 앱 코드(`frontend/src/index.css` 등)는 아직 이 값으로 갱신 전이다 — Do's/Don'ts와
> 프론트매터가 정본이고, 코드 반영은 별도 구현 작업으로 남아 있다(Known Gaps).

### Foundations — Palette

Figma 원본 그대로: **Blue**(`blue-10`~`blue-100`) · **Navy**(`navy-10`~`navy-100`) ·
**Sky**(`sky-10`~`sky-100`) 3종 10단 램프, **Functional** 10색(단일 스와치, 카테고리·차트용),
**Neutral**(7단, 이름=hex) · **Cool Neutral**(10단) · **White**(알파 10단) 그레이스케일 3종.
각 램프는 `color·N = white·(1 − N/100) + base·N/100` 공식으로 100(원색)에서 10(옅은 틴트)까지 보간된다
(`blue-50` = blue-100과 white의 50:50 혼합 — Figma 실측치와 오차 ±1 이내로 검증됨).

### Semantic — Primary & Accent

- **Primary Point** (`{colors.primary-point}`, #418dff = Sky/100): 시스템 유일의 포인트. primary 버튼,
  헤더 하단 라인, 활성 탭/세그먼트 배경, FAB, PWA theme-color·앱 아이콘 배경.
- **Primary Normal** (`{colors.primary-normal}`, #25468f = Blue/100): primary 버튼 hover, 강조 텍스트,
  랭킹 점수, 링크 강조.
- **Primary Heavy** (`{colors.primary-heavy}`, #16233f = Navy/100): 다크 변형 — 딥 대비가 필요한 표면(추가
  구현 시 헤더 다크 모드 등 예약).

### Semantic — Surface & Background

- **Background Normal** (`{colors.background-normal}`, #ffffff): 카드·모달·헤더·인풋 배경.
- **Background Point** (`{colors.background-point}`, #f6f7fa = Cool Neutral/10): 페이지 배경(body), 회색
  패널·중립 칩 배경.
- **Background Disabled** (`{colors.background-disabled}`, #dddddd)
- **Background Heavy** (`{colors.background-heavy}`, #516ba5 = Blue/80)
- **Line Normal** (`{colors.line-normal}`, #dddddd): 기본 1px 보더·링·구분선.
- **Line Neutral** (`{colors.line-neutral}`, #eeeeee) · **Line Heavy** (`{colors.line-heavy}`, #cccccc)

### Semantic — Text (Font)

- **Font Strong** (`{colors.font-strong}`, #1a1a1a): 제목·헤딩·카드 타이틀.
- **Font Secondary** (`{colors.font-secondary}`, #444444): 본문 기본색.
- **Font Tertiary** (`{colors.font-tertiary}`, #666666): 보조 텍스트.
- **Font Subtle** (`{colors.font-subtle}`, #999999) / **Font Disabled** (동일값): 캡션·메타·빈 상태·비활성.
- **Font White** (`{colors.font-white}`, #ffffff): 블루·다크 면 위의 역상 텍스트.

### Semantic — Label

Label 그룹은 카테고리 뱃지·칩 전용 배경/텍스트 페어다: `{colors.label-bg-normal}`(#eaedf4, 뱃지 표준
배경) · `{colors.label-bg-heavy}`(#91a2c6, 강조 배경) · `{colors.label-bg-sky}`(#418dff) ·
`{colors.label-font-normal}`(#444444) · `{colors.label-font-blue}`(#25468f) ·
`{colors.label-font-white}`(#ffffff).

### 앱 전용 상태색 (System — Figma 부분 정의 + 추론)

`{colors.system-error}`(#ff453a = Functional/Red)만 Figma에 명시돼 있다. success/warning과 각 `-bg` 페어,
차트 팔레트, `overlay-scrim`은 **Figma 스타일가이드에 대응 토큰이 없어** Foundations의 Functional
색상에서 위 tint 공식(N=10)으로 추론했다(사람 승인 완료 — Known Gaps에 디자이너 확인 요청 남김).

- **Success** (`{colors.success}` #56ff3a = Functional/Green) / **Success Bg** (`{colors.success-bg}`
  #eeffeb, 10% tint): 신선도 뱃지 "최신 정보".
- **Danger** (`{colors.danger}` #ff453a = Functional/Red = system-error) / **Danger Bg**
  (`{colors.danger-bg}` #ffeceb, 10% tint): 신선도 뱃지 "정보 변경됨".
- **Warning** (`{colors.warning}` #ffbb3a = Functional/Orange) / **Warning Bg** (`{colors.warning-bg}`
  #fff8eb, 10% tint): 피드백 상태 "검토중".
- **Overlay Scrim** (`{colors.overlay-scrim}` #000000): Figma에 대응 토큰 없음 — 브랜드 색상과 무관한
  중립 상수라 값 변경 없이 유지.

### Chart Palette (통계실 전용 — Figma 미정의, Foundations 재사용)

`{colors.chart-1}`~`{colors.chart-6}` — Sky/Blue/Navy 램프 조합 5단 + 대비용 Green 1단:
`{colors.chart-1}`(#418dff) → `{colors.chart-2}`(#25468f) → `{colors.chart-3}`(#b3d1ff) →
`{colors.chart-4}`(#16233f) → `{colors.chart-5}`(#d9e8ff) → `{colors.chart-6}`(#56ff3a, 대비 강조).
그리드는 `{colors.chart-grid}`(#eeeeee).

### 비토큰 색상 (Out-of-Token — Figma 변환 시 로컬 스타일 처리)

이전과 동일하게 유지: 서드파티 브랜드 고정색(카카오톡 `#FEE500`/`#3A1D1D`, NAVER `#03C75A`), 고객카드
스튜디오 전용 프리셋 팔레트, Tailwind 기본 팔레트 잔존 3건, `transparent`. 상세는 이전 버전 git 이력 참조
— 이번 리브랜딩은 이 항목들에 영향을 주지 않는다.

### 데이터 주도 색상 정책 (보험사 brand_color)

정책 변경 없음 — 보험사 44곳 중 23곳 `brand_color` 보유, 로고 이미지 로드 실패 시 폴백 칩 배경 단 한
곳에만 사용, null이면 `{colors.primary-point}`로 폴백. 상세 목록은 `data/insurers.json` 참조.

## Typography

### Font Family

- **Pretendard** — 폴백 스택 동일 유지: `Pretendard, -apple-system, BlinkMacSystemFont, "Malgun Gothic",
  sans-serif`. 폰트 파일 로딩은 소비 앱 책임.
- 코드 표기(`code-badge`)만 `font-mono` 예외 — Figma 스타일가이드에 대응 스타일이 없어 기존 값(12px/400)을
  그대로 유지한 로컬 예외 토큰이다.

### Hierarchy (Figma 원본 스케일 — 19종)

| Token | Size | Weight | Line Height |
|---|---|---|---|
| `{typography.PC_40_B}` | 40px | 700 | 1.50 |
| `{typography.FONT_TIT_T_SB_32}` | 32px | 600 | 1.25 |
| `{typography.PC_32_SB}` | 32px | 600 | 1.50 |
| `{typography.PC_20_B}` | 20px | 700 | 1.60 |
| `{typography.PC_20_SB}` / `{typography.FONT_TIT_T_SB_20}` | 20px | 600 | 1.60 / 1.40 |
| `{typography.FONT_BODY_B_R_18}` | 18px | 400 | 1.55 |
| `{typography.PC_18_SB}` | 18px | 600 | 1.55 |
| `{typography.PC_18_M}` | 18px | 500 | 1.55 |
| `{typography.PC_16_SB}` | 16px | 600 | 1.50 |
| `{typography.PC_16_M}` | 16px | 500 | 1.50 |
| `{typography.PC_16_R}` | 16px | 400 | 1.50 |
| `{typography.PC_14_B}` | 14px | 700 | 1.43 |
| `{typography.PC_14_M}` | 14px | 500 | 1.43 |
| `{typography.PC_14_R}` | 14px | 400 | 1.43 |
| `{typography.PC_12_B}` | 12px | 700 | 1.67 |
| `{typography.PC_12_SB}` | 12px | 600 | 1.67 |
| `{typography.PC_12_M}` | 12px | 500 | 1.67 |
| `{typography.PC_12_R}` | 12px | 400 | 1.67 |
| `{typography.code-badge}`(mono, Figma 미정의) | 12px | 400 | 1.67 |

### Migration — 기존 18개 시맨틱 역할 → Figma 원본 키

기존 앱 코드는 아직 시맨틱 역할명(`display`, `title-page` 등)으로 구현돼 있다. 이 표는 코드 반영 시
참조할 매핑이다 — **값이 바뀌었거나(사이즈·굵기) 여러 역할이 하나로 합쳐진 항목**을 굵게 표시했다.

| 기존 역할 | 기존 값 | 새 토큰 | 새 값 | 비고 |
|---|---|---|---|---|
| `display` | 30px/800 | `PC_32_SB`* | 32px/600 | 최근접값. 800 폐지 |
| `title-page` | 24px/800 | `PC_20_B` | 20px/700 | 24px 스텝 없음 |
| `title-section` | 20px/800 | `PC_20_SB` | 20px/600 | 굵기만 하향 |
| `title-sub` | 18px/800 | `PC_18_SB` | 18px/600 | 굵기만 하향 |
| `title-card` | 16px/700 | `PC_16_SB` | 16px/600 | |
| `body-bold` | 14px/700 | `PC_14_B` | 14px/700 | 정확 일치 |
| `body` | 14px/400 | `PC_14_R` | 14px/400 | 정확 일치 |
| `body-medium` | 14px/500 | `PC_14_M` | 14px/500 | 정확 일치 |
| **`panel-title`** | 14px/800 | `PC_14_B` | 14px/700 | **body-bold와 병합** |
| **`nav-tab`** | 13px/700 | `PC_12_B` | 12px/700 | **caption-bold·micro와 병합** |
| **`caption-bold`** | 12px/700 | `PC_12_B` | 12px/700 | **nav-tab·micro와 병합** |
| `caption` | 12px/400 | `PC_12_R` | 12px/400 | `meta`와 병합 |
| `tag` | 12px/500 | `PC_12_M` | 12px/500 | `micro-label`과 병합 |
| **`micro`** | 11px/700 | `PC_12_B` | 12px/700 | **11px 스텝 폐지, caption-bold와 병합** |
| `meta` | 11px/400 | `PC_12_R` | 12px/400 | 11px 스텝 폐지 |
| **`micro-label`** | 10px/700 | `PC_12_M` | 12px/500 | **10px 스텝 폐지, 굵기 하향, tag와 병합** |
| **`wordmark`** | 15px/800 | `PC_16_SB` | 16px/600 | **15px 국소값 폐지** |
| `code-badge` | 12px/400 mono | `code-badge` | 12px/400 mono | 변경 없음(Figma 미정의 예외) |

\* `display`는 `FONT_TIT_T_SB_32`(32px/600/-2 tracking)도 후보였다 — 히어로 H1은 자간 압축이 없는
`PC_32_SB` 채택.

### Principles (갱신)

- **ExtraBold(800)가 폐지됐다.** 이전 "크기가 아니라 weight가 위계다"는 이제 Bold(700)를 상한으로
  재해석한다. 제목은 700, 본문 강조는 700에서 그대로 멈춘다(변경 없음), 다만 이전에 800이던 제목들은
  전부 600~700으로 낮아졌다 — 시각적 대비가 약해질 수 있어 구현 시 실렌더 확인 필요(Known Gaps).
  본문·버튼·메타가 14px 안에서 400/700의 대비로 구분되는 원칙은 유지.
- **11px·10px·13px·15px·24px 스텝이 전부 폐지됐다.** Figma 스케일은 {12,14,16,18,20,32,40}만 제공한다.
  세부 위계가 필요하던 자리(nav-tab/caption-bold/micro, tag/micro-label, wordmark)는 위 표처럼 인접값에
  흡수됐다 — 시각적으로 이전보다 위계 단이 줄어든다.
- **행간·자간**: Figma 스타일가이드에 실측 lineHeight가 있는 스타일만 그 값을 썼고(FONT_TIT 계열), 나머지
  PC_* 계열은 값이 없어 기존 시스템의 역할별 관행(본문 1.43~1.67, 제목 1.50~1.60)을 그대로 이식했다 —
  **이 열은 디자이너 실측치가 아니라 추정치**임을 표기(Known Gaps).
- **mono는 코드 전용.** 변경 없음.

## Shapes

### Border Radius Scale (Figma 원본)

| Token | Value | 비고 |
|---|---|---|
| `{rounded.4}` / `{rounded.tag}` | 4px | Figma "Tag" 명시값 |
| `{rounded.8}` | 8px | 컨트롤 표준(버튼·인풋·탭·행) — 기존 `md`와 동일 |
| `{rounded.16}` / `{rounded.card}` | 16px | Figma "Card" 명시값 — **기존 12px에서 상향** |
| `{rounded.24}` | 24px | 스튜디오 대형 요소 |
| `{rounded.999}` | 999px | 뱃지·칩·아바타·FAB(사실상 pill) — 기존 `9999px`에서 Figma 실측치로 조정 |

> 이전 7단(xs/sm/md/card/lg/xl/full)이 Figma 원본 5단(4/8/16/24/999 + 별칭 card/tag)으로 압축됐다.
> 기존 `sm`(6px)은 스텝 자체가 폐지돼 `{rounded.8}`로 흡수, `lg`(16px)는 `card`와 값이 같아져 그대로
> `{rounded.16}`을 직접 참조하도록 통합했다.

## Spacing

Figma 스타일가이드는 명명된 역할 없이 **숫자 스케일 하나**만 제공한다(4의 배수 원칙: "사이즈 및 간격은
4 또는 8의 배수로 지정, 그 외 필요 시 4/8의 배수로 유연 적용"): `{spacing.4}` · `{spacing.8}` ·
`{spacing.12}` · `{spacing.16}` · `{spacing.20}` · `{spacing.24}` · `{spacing.28}` · `{spacing.32}` ·
`{spacing.40}` · `{spacing.48}` · `{spacing.60}` · `{spacing.64}` · `{spacing.72}` · `{spacing.80}` ·
`{spacing.100}` · `{spacing.120}`.

기존 시맨틱 이름(xxs~section)은 폐지하고 컴포넌트에서 숫자 키를 직접 참조한다 — Figma가 이름을 붙이지
않았으므로 임의로 새 이름을 만들지 않는다는 원칙(전면 Figma 명명 교체)을 따른 것이다. 옛 `xs`(6px)만
스텝 자체가 없어 `{spacing.8}`로 근사했다.

- 카드 내부 패딩 표준: `{spacing.16}`(기존 `lg`와 동일값 유지).
- 버튼 패딩 표준: `{spacing.12}` 수평 × `{spacing.8}` 수직(기존과 동일값).
- 섹션 리듬: 홈 섹션 간 `{spacing.32}`, 푸터 상단 `{spacing.48}`(기존과 동일값 — 그대로 존재하는 스텝).

### Grid & Container (변경 없음)

전 화면 공통 셸: Header → `main` 콘텐츠 최대폭 1152px(max-w-6xl), 좌우 `{spacing.16}`, 상하
`{spacing.24}` → Footer → 우하단 FAB. 카드 그리드·반응형 분기·헤더 sticky 동작은 이전과 동일 — 토큰
이름/값 변경은 색·타이포·radius 층에 국한된다.

## Components

컴포넌트 프리미티브 목록(button/card/badge/tab/modal 등)과 조립 규칙은 이전과 동일 구조를 유지하며,
참조 토큰만 새 키로 갱신했다(frontmatter `components:` 참조). 이 섹션은 생성기가 소비하지 않는 순수
문서용 프리미티브 정의다(`tools/gen-tokens.mjs`: "components 등 그 외 섹션은 무시").

## Do's and Don'ts (갱신)

### Do

- 포인트가 필요하면 `{colors.primary-point}` 축(point/normal/heavy) 안에서 해결하라 — 이 시스템의
  액센트는 블루 하나다.
- 선택 상태는 반전으로: 활성 탭·현재 페이지·세그먼트는 `{colors.primary-point}` 배경 +
  `{colors.font-white}` 글자.
- hover는 용도로 구분하라: 카드 전체가 링크면 배경 `{colors.label-bg-normal}`, 카드 안에 버튼이 있으면
  shadow-fg-md 상승.
- radius는 2단만: 컨트롤 `{rounded.8}`, 카드·모달 `{rounded.card}`(16px). 뱃지·칩·FAB만 `{rounded.999}`.
- 상태 표현은 뱃지 5 variant로 환원하라 — success/warning/danger 값은 디자이너 확인 전까지 임의 변경
  금지(추론값이므로).
- 굵기는 700을 상한으로 써라 — 800(ExtraBold)은 새 스케일에 없다.

### Don't

- 보험사 `brand_color`를 로고 칩 폴백 밖으로 유출하지 마라.
- 새 그라디언트를 추가하지 마라 — 홈 히어로 1곳이 전부다.
- Figma에 없는 굵기(800)나 사이즈(11/10/13/15/24px)를 새로 만들지 마라 — Migration 표의 인접값으로
  흡수하라.
- success/warning/chart 색을 "확정값"으로 취급하지 마라 — Foundations에서 추론한 값이며 디자이너 확인
  대기 상태다.

## Known Gaps

- **[미결] success/warning/chart 팔레트 디자이너 확인 필요**: Figma 스타일가이드에 정의가 없어
  Foundations Functional 색상 + tint 공식(N=10)으로 추론했다(2026-07-29, 사람 승인 완료). 디자이너가
  실제 지정값을 주면 그 값으로 교체해야 한다.
- **[미결] 타이포 lineHeight 추정치**: `PC_*` 계열 lineHeight는 Figma 실측값이 없어 기존 시스템 관행을
  이식한 추정치다. Pretendard 실렌더 기준 재검증 필요.
- **[미결] 앱 코드 미반영**: `frontend/src/index.css`의 CSS 변수·컴포넌트는 여전히 구 청록 값이다. 이번
  갱신은 `DESIGN.md`(정본) + `packages/design-token` 생성물까지이며, 실제 앱 화면 리스킨은 별도 구현
  작업이다.
- **Figma 파일 2원화**: 토큰 소스는 신규 파일(fileKey `HiZkjwReW7N7ajS1DPOUTP`, Style Guide 페이지)이고,
  기존 registry(`agents/plugins/ia/registry/registry.json`)에 등록된 fileKey
  `Ks7Ux7FMYLIFG36d8MRsQc`("보험 아카이브 디자인 시스템")는 컴포넌트/Code Connect 용으로 별도 존재한다.
  두 파일이 같은 프로젝트의 다른 산출물인지, 어느 쪽이 최종 정본인지 디자이너 확인 필요.
- **design-token-fetch 자동화 미구축**: `registry/registry.json`의 `tokens.snapshotPath`·
  `tokens.mappingTableRel`은 아직 비어 있다 — 이번 갱신은 사람이 직접 Figma MCP로 값을 읽어 반영한
  1회성 작업이며, 향후 지속 동기화(스냅샷·매핑표·`sotSplit` 소유권 재배정)는 별도 결정 사항으로 남는다.
- **Radius/Spacing 압축에 따른 시각 변화**: radius 7단→5단, spacing named role 폐지가 기존 화면에 미치는
  시각적 영향(특히 카드 12→16px, pill 9999→999px)은 실제 리스킨 전 스크린샷 대조 권장.
- 이전 버전에 있던 세부 실측 데이터(색상별 등장 횟수, 컴포넌트별 조립 프리미티브 전수표 등)는 git 이력의
  이전 `DESIGN.md`에서 확인 가능하다 — 이번 리브랜딩 문서는 새 토큰 체계 정의에 집중했다.
