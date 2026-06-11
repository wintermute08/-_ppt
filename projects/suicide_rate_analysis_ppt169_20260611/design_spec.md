# 전세계 자살률 분석 (1985–2016) - Design Spec

> Machine-readable execution contract: `spec_lock.md`.

## I. Project Information

| Item | Value |
| ---- | ----- |
| **Project Name** | 전세계 자살률 분석 프로젝트 (1985–2016) |
| **Canvas Format** | PPT 16:9 (1280×720) |
| **Page Count** | 14 |
| **Design Style** | B) General Consulting + 모던 에디토리얼 데이터 리포트 |
| **Target Audience** | 비전문가 포함 일반 청중 (수업/팀 발표) — 발표자도 도메인 비전문가, 상세 발표 대본 필수 |
| **Use Case** | 데이터 분석 프로젝트 결과 발표 |
| **Created Date** | 2026-06-11 |

---

## II. Canvas Specification

| Property | Value |
| -------- | ----- |
| **Format** | PPT 16:9 |
| **Dimensions** | 1280×720 |
| **viewBox** | `0 0 1280 720` |
| **Margins** | 좌우 60px, 상하 50px |
| **Content Area** | 1160×620 (제목영역 1160×90, 본문영역 1160×490, 푸터 1160×30) |

---

## III. Visual Theme

### Theme Style

- **Style**: 컨설팅 데이터 리포트 + 모던 에디토리얼
- **Theme**: Light theme
- **Tone**: 차분함, 신뢰감, 절제된 진지함 (민감한 보건 주제에 적합)

### Color Scheme

| Role | HEX | Purpose |
| ---- | --- | ------- |
| **Background** | `#F5F7FA` | 페이지 배경 (오프화이트) |
| **Secondary bg** | `#FFFFFF` | 카드 배경 |
| **Primary** | `#1E3A5F` | 딥 네이비 — 제목, 핵심 섹션, 아이콘 |
| **Accent** | `#E63946` | 코랄 레드 — 위험·핵심 수치 강조 |
| **Secondary accent** | `#457B9D` | 스틸 블루 — 보조 강조, 그라디언트 |
| **Body text** | `#2B2D33` | 본문 |
| **Secondary text** | `#5C6470` | 캡션, 주석 |
| **Tertiary text** | `#9AA3AF` | 푸터, 페이지 번호 |
| **Border/divider** | `#D8DEE6` | 카드 테두리, 구분선 |
| **Success** | `#2A9D8F` | 긍정 지표 (틸 그린) |
| **Warning** | `#E63946` | 위험 지표 |

### Gradient Scheme

```xml
<linearGradient id="titleGradient" x1="0%" y1="0%" x2="100%" y2="100%">
  <stop offset="0%" stop-color="#1E3A5F"/>
  <stop offset="100%" stop-color="#457B9D"/>
</linearGradient>
<radialGradient id="bgDecor" cx="80%" cy="20%" r="50%">
  <stop offset="0%" stop-color="#1E3A5F" stop-opacity="0.12"/>
  <stop offset="100%" stop-color="#1E3A5F" stop-opacity="0"/>
</radialGradient>
```

---

## IV. Typography System

### Font Plan

**Typography direction**: modern Korean sans — 단일 패밀리(맑은 고딕), 굵기 대비(Bold 900 vs Regular)로 위계 형성

| Role | Korean | English | Fallback tail |
| ---- | ------- | ------- | ------------- |
| **Title** | `"Malgun Gothic"` | `Arial` | `sans-serif` |
| **Body** | `"Malgun Gothic"` | `Arial` | `sans-serif` |
| **Emphasis** | `"Malgun Gothic"` | `Arial` | `sans-serif` |
| **Code** | — | `Consolas, "Courier New"` | `monospace` |

**Per-role font stacks**:

- Title: `"Malgun Gothic", "Apple SD Gothic Neo", Arial, sans-serif`
- Body: `"Malgun Gothic", "Apple SD Gothic Neo", Arial, sans-serif`
- Emphasis: same as Body
- Code: `Consolas, "Courier New", monospace`

### Font Size Hierarchy

**Baseline**: Body font size = 18px (데이터 밀도 높은 컨설팅 덱)

| Purpose | Ratio | px |
| ------- | ----- | -- |
| Cover title | 2.5-5x | 56 |
| Section opener | 2-2.5x | 40 |
| Page title | 1.5-2x | 30 |
| Hero number | 1.5-2x | 36-90 (cover/hero에서 확장 슬롯 사용) |
| Subtitle | 1.2-1.5x | 22 |
| **Body** | **1x** | **18** |
| Annotation | 0.7-0.85x | 13-15 |
| Page number | 0.5-0.65x | 10-12 |

확장 슬롯: `cover_title: 56`, `hero_number: 90`, `chart_annotation: 13`

---

## V. Layout Principles

### Page Structure

- **Header area**: 상단 50–110px — 페이지 제목 + 네이비 액센트 바
- **Content area**: 110–660px — 본문/차트/카드
- **Footer area**: 660–700px — 페이지 번호, 출처 표기

### Layout Patterns

- 표지/결론: 단일 컬럼 중앙 + 네거티브 스페이스
- 차트 페이지: 비대칭 분할 (7:3 — 차트 vs 테이크어웨이 박스)
- 인사이트 히어로: 빅넘버 중심 negative-space-driven
- 기대효과/활용/리스크: 카드 그리드

### Spacing

- Safe margin 60px / 블록 간격 28px / 아이콘-텍스트 12px
- 카드 간격 24px, 패딩 24px, 라운드 12px

---

## VI. Icon Usage Specification

### Source

- Built-in: `phosphor-duotone` (단일 라이브러리, 혼용 금지)
- Usage: `<use data-icon="phosphor-duotone/<name>" .../>`

### Recommended Icon List

| Purpose | Icon Path | Page |
| ------- | --------- | ---- |
| 글로벌 데이터 | `phosphor-duotone/globe` | P03 |
| 데이터셋 | `phosphor-duotone/database` | P03 |
| 인구/집단 | `phosphor-duotone/users` | P03, P10 |
| 캘린더(기간) | `phosphor-duotone/calendar` | P03 |
| 탐색 분석 | `phosphor-duotone/magnifying-glass` | P02, P04 |
| 차트 | `phosphor-duotone/chart-bar` | P02, P08 |
| 추세 | `phosphor-duotone/chart-line` | P04 |
| ML/모델 | `phosphor-duotone/brain` | P02, P06, P08 |
| 전처리 | `phosphor-duotone/gear` | P06 |
| 군집 | `phosphor-duotone/chart-scatter` | P07 |
| 변수 중요도 | `phosphor-duotone/chart-bar-horizontal` | P09 |
| 핵심 타깃 | `phosphor-duotone/target` | P10, P12 |
| 인사이트 | `phosphor-duotone/lightbulb` | P02, P10, P11 |
| 상승 추세 | `phosphor-duotone/trend-up` | P11 |
| 하락 추세 | `phosphor-duotone/trend-down` | P04 |
| 위험/경고 | `phosphor-duotone/warning` | P13 |
| 보호/정책 | `phosphor-duotone/shield-check` | P12 |
| 균형/윤리 | `phosphor-duotone/scales` | P13 |
| 보건 | `phosphor-duotone/heartbeat` | P12, P14 |
| 지원 | `phosphor-duotone/hand-heart` | P14 |
| 확인 | `phosphor-duotone/check-circle` | P12, P14 |
| 전략 | `phosphor-duotone/strategy` | P12 |
| 남성 | `phosphor-duotone/gender-male` | P10 |
| 발표 개요 | `phosphor-duotone/presentation-chart` | P02 |
| 실험 | `phosphor-duotone/flask` | P06 |

---

## VII. Visualization Reference List

Catalog read: 71 templates

| Page | Template | Path | Summary-quote (verbatim) | Usage |
| ---- | -------- | ---- | ------------------------ | ----- |
| P02 | agenda_list | `templates/charts/agenda_list.svg` | "Pick for table of contents, meeting agendas, or presentation roadmap — numbered items + brief description + duration / owner per row. Skip for substantive content lists (use vertical_list) or single-page section dividers (use a cover layout)." | 발표 목차 |
| P03 | kpi_cards | `templates/charts/kpi_cards.svg` | "Pick for 4-8 standalone numeric metrics shown as overview cards (2x2 or 1x4) — exec summary opener, dashboard headline, quarterly recap, results-at-a-glance. Skip if metrics have target baselines (use bullet_chart) or single hero number (use gauge_chart)." | 데이터셋 개요 KPI (27,820 레코드 / 101개국 / 32년 / 12변수) |
| P06 | pipeline_with_stages | `templates/charts/pipeline_with_stages.svg` | "Pick for 3-5 horizontal pipeline stages, each = title + 1-line description + output artifact, connected by arrows (data pipelines, ETL, build pipelines). Skip if any stage lacks an artifact (use process_flow or numbered_steps)." | 분석 파이프라인 (전처리→PCA→군집→분류, 각 단계 산출물 명시) |
| P12 | icon_grid | `templates/charts/icon_grid.svg` | "Pick for 4-9 parallel features/capabilities/services as icon cards — feature grid, service lineup, benefits matrix, brand values, product highlights. Skip for sequential ordering (use numbered_steps) or hierarchical layers (use pyramid_chart)." | 기대효과 3 + 활용방안 3 아이콘 카드 |
| P13 | vertical_list | `templates/charts/vertical_list.svg` | "Pick for 3-6 numbered key points each with a short description — design principles, core tenets, action items, key takeaways, recommendations, executive summary points. Skip for icon-style cards (use icon_grid) or sequential steps (use numbered_steps)." | 리스크 및 한계 6개 항목 |

**Runners-up considered**:

- `numbered_steps` | rejected for P06: 각 단계가 명시적 산출물(정제 데이터, 2D 좌표, 군집 라벨, 분류 모델)을 가지므로 pipeline_with_stages가 더 적합
- `vertical_pillars` | rejected for P12: 기대효과/활용방안은 카테고리별 불릿 목록이 아닌 6개 병렬 아이콘 카드 구조
- `pros_cons_chart` | rejected for P13: 양면 비교가 아니라 단일 리스트(한계점만 나열)이므로 vertical_list가 적합

P04/P05/P07/P08/P09/P11은 노트북에서 생성한 matplotlib 차트 PNG를 그대로 사용 (no-template-match — 데이터 차트가 이미 이미지로 존재, SVG 재구현 시 수치 왜곡 위험).

---

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Layout pattern | Acquire Via | Status | Reference | text_policy | page_role |
| -------- | --------- | ----- | ------- | ---- | -------------- | ----------- | ------ | --------- | ----------- | --------- |
| 01_eda_overview.png | 2085x1477 | 1.41 | P04 EDA 4분할 차트 | Diagram | #2 left-two-thirds image + right text rail | user | Existing | 성별/연령/연도/GDP 4분할 EDA | | |
| 02_pca.png | 1185x885 | 1.34 | P07 PCA 산점도 | Diagram | #48 side-by-side comparison | user | Existing | PCA 2D 분포 | | |
| 03_elbow.png | 1035x585 | 1.77 | (보조 — 미사용 가능) | Diagram | #5 top band image | user | Existing | 엘보우 곡선 | | |
| 04_kmeans.png | 1185x885 | 1.34 | P07 군집 산점도 | Diagram | #48 side-by-side comparison | user | Existing | K-Means K=3 군집 | | |
| 05_model_compare.png | 1185x735 | 1.61 | P08 모델 성능 비교 | Diagram | #2 left-two-thirds image + right text rail | user | Existing | 4개 모델 정확도 비교 | | |
| 06_confusion.png | 791x660 | 1.20 | P08 혼동행렬 | Diagram | #48 side-by-side comparison | user | Existing | 결정트리 혼동행렬 | | |
| 07_feature_importance.png | 1335x885 | 1.51 | P09 변수 중요도 | Diagram | #2 left-two-thirds image + right text rail | user | Existing | 결정트리 변수 중요도 상위 15 | | |
| 08_insights.png | 2085x742 | 2.81 | P11 인사이트 듀얼 차트 | Diagram | #5 top full-width band + bottom text | user | Existing | 연령×성별 + HDI 구간 차트 | | |
| 09_country_top10.png | 1335x735 | 1.82 | P05 국가별 TOP10 | Diagram | #2 left-two-thirds image + right text rail | user | Existing | 국가 평균 자살률 순위 | | |

> 모든 행이 `user`(분석 차트 PNG)이므로 Step 5 생략. 차트는 전부 데이터 이미지이므로 spec_lock에서 `no-crop` 처리. image-as-canvas(#38–46) 미적용 사유: 전 이미지가 데이터 차트(축·수치 보존 필수)로 풀블리드 배경 사용이 부적합.

---

## IX. Content Outline

### Part 1: 도입

#### Slide 01 - 표지 (P01)

- **Layout**: 단일 컬럼 중앙, 네이비 풀배경 + 그라디언트 데코
- **Title**: 전세계 자살률 데이터 분석
- **Subtitle**: 1985–2016, 101개국 27,820건 데이터가 말해주는 것
- **Info**: 데이터 분석 프로젝트 발표 · 2026.06

#### Slide 02 - 목차 (P02)

- **Layout**: agenda_list 변형 — 좌측 번호 + 우측 설명
- **Title**: 오늘 발표의 흐름
- **Core message**: 데이터 탐색에서 정책 제언까지 5단계로 전개한다.
- **Visualization**: agenda_list
- **Content**:
  - 01 데이터와 분석 개요 / 02 탐색적 데이터 분석 / 03 머신러닝 분석 / 04 핵심 인사이트 / 05 기대효과·활용·한계

#### Slide 03 - 데이터 & 분석 개요 (P03)

- **Layout**: kpi_cards 1×4 + 하단 분석 목표 박스
- **Title**: 어떤 데이터로, 무엇을 분석했나
- **Core message**: 32년간 101개국의 자살률 데이터로 고위험 집단의 특성을 기계학습으로 규명한다.
- **Visualization**: kpi_cards
- **Content**:
  - KPI: 27,820 레코드 / 101개국 / 32년(1985–2016) / 12개 변수
  - 분석 목표: 10만명당 자살률 중앙값(5.99) 기준 고위험(1)/저위험(0) 분류 — GDP·HDI·성별·연령의 영향 규명

### Part 2: 탐색적 데이터 분석

#### Slide 04 - EDA 종합 (P04)

- **Layout**: 좌측 2/3 차트 이미지 + 우측 테이크어웨이 레일
- **Title**: 데이터가 보여주는 네 가지 큰 그림
- **Core message**: 자살률은 성별·연령에 따라 극명하게 갈리고, 경제력과는 거의 무관하다.
- **Content**:
  - 이미지: 01_eda_overview.png
  - 남성 20.7 vs 여성 5.9 (3.5배) · 75세+ 최고 24.5 · 1995년 정점 후 하락 · GDP 상관 +0.06 (무상관)

#### Slide 05 - 국가별 현황 (P05)

- **Layout**: 좌측 2/3 차트 + 우측 해설
- **Title**: 자살률이 가장 높은 나라들
- **Core message**: 상위권은 구소련·동구권 체제전환기 국가에 집중되어 있다 — 사회적 격변이 핵심 배경.
- **Content**:
  - 이미지: 09_country_top10.png
  - 리투아니아 40.4 1위 · 러시아·헝가리·벨라루스 등 동구권 집중 · 사회 안전망 붕괴 시기와 일치

### Part 3: 머신러닝 분석

#### Slide 06 - 분석 파이프라인 (P06)

- **Layout**: pipeline_with_stages 4단계 가로 흐름
- **Title**: 분석은 이렇게 진행했습니다
- **Core message**: 정제→차원축소→군집→분류의 4단계 파이프라인으로 데이터에서 패턴을 추출했다.
- **Visualization**: pipeline_with_stages
- **Content**:
  - ① 전처리: 결측 대체·인코딩 → 정제 데이터 18변수 / ② PCA: 고차원→2D → 시각화 좌표 / ③ K-Means: 자동 그룹화 → 3개 군집 / ④ 분류 모델: 4개 알고리즘 → 최적 모델

#### Slide 07 - PCA & 군집 분석 (P07)

- **Layout**: 5:5 듀얼 이미지 + 하단 해석 밴드
- **Title**: 라벨 없이도 위험 그룹이 갈라진다
- **Core message**: 인구통계·경제지표만으로 자살률 수준이 뚜렷이 다른 3개 군집이 자동 분리된다.
- **Content**:
  - 이미지: 02_pca.png + 04_kmeans.png
  - 군집3 평균 19.7 / 군집1 12.3 / 군집2 4.4 — 최대 4.5배 차이 · 위험 계층화 가능성 입증

#### Slide 08 - 모델 성능 비교 (P08)

- **Layout**: 좌측 성능 차트 + 우측 혼동행렬 + 하단 지표
- **Title**: 결정 트리, 80.18%로 최고 성능
- **Core message**: 결정 트리가 정확도 80.18%로 4개 모델 중 최고 — 단, 고위험 566건 미탐지가 남은 과제.
- **Content**:
  - 이미지: 05_model_compare.png + 06_confusion.png
  - 결정트리 80.18% > KNN(11) 78.68% > KNN(5) 78.22% > 로지스틱 77.95%
  - 정밀도 0.805 / 재현율 0.797 / F1 0.801 · FN 566건 = 정책 비용 최대 항목

#### Slide 09 - 변수 중요도 (P09)

- **Layout**: 좌측 2/3 차트 + 우측 순위 카드
- **Title**: 무엇이 위험을 가르는가
- **Core message**: 연령과 성별, 즉 인구통계가 중요도의 67%를 차지한다 — 경제 변수는 보조적.
- **Content**:
  - 이미지: 07_feature_importance.png
  - 1위 age_5-14 (0.366) · 2위 sex_male (0.299) · 3위 GDP (0.130) · 인구통계 67% vs 경제 24%

### Part 4: 핵심 인사이트

#### Slide 10 - 인사이트 1: 가장 취약한 집단 (P10)

- **Layout**: 빅넘버 히어로 — negative-space-driven
- **Title**: 75세 이상 남성, 10만명당 38명
- **Core message**: 고령 남성은 같은 연령 여성의 3.8배 — 노인 남성 정신건강 지원이 최우선 과제다.
- **Content**:
  - 히어로 넘버 37.99 · vs 여성 9.92 (3.8배) · vs 전체 평균 12.8 (3.0배)

#### Slide 11 - 인사이트 2: 발전의 역설 (P11)

- **Layout**: 상단 와이드 차트 + 하단 해석
- **Title**: 잘사는 나라가 더 위험하다는 역설
- **Core message**: HDI가 높을수록 자살률이 오히려 상승 — 경제 성장만으로는 자살을 막을 수 없다.
- **Content**:
  - 이미지: 08_insights.png
  - 저개발 8.5 → 중하위 9.9 → 중상위 13.0 → 고개발 13.5 (단조 증가)
  - 시사점: 성장 정책과 정신건강 정책은 별도 트랙 필요

### Part 5: 제언

#### Slide 12 - 기대효과 & 활용방안 (P12)

- **Layout**: icon_grid 2×3 — 좌측 3장 기대효과, 우측 3장 활용방안
- **Title**: 이 분석으로 무엇을 할 수 있나
- **Core message**: 80% 정확도의 위험 식별은 예방 자원의 우선순위 배분 근거가 된다.
- **Visualization**: icon_grid
- **Content**:
  - 기대효과: 고위험군 사전 식별(80%) / 타게팅 효율 극대화 / 국가군별 맞춤 정책
  - 활용방안: 자살예방 정책 우선순위 지표 / 보건 예산 배분 시뮬레이션 / 노인 남성 조기 스크리닝 설계

#### Slide 13 - 리스크 및 분석의 한계 (P13)

- **Layout**: vertical_list 6항목 (2열 3행)
- **Title**: 결과를 읽을 때 주의할 점
- **Core message**: 국가 단위 집계 데이터라는 본질적 한계를 인정해야 결과를 바르게 쓸 수 있다.
- **Visualization**: vertical_list
- **Content**:
  - 생태학적 오류(국가→개인 적용 불가) / HDI 70% 결측 중앙값 대체 / 2016년까지 — 코로나 이후 미반영 / 국가별 신고 기준 차이(과소보고) / 중앙값 이진분류의 임계값 민감성 / 민감 주제의 윤리적 해석 주의

#### Slide 14 - 결론 및 제언 (P14)

- **Layout**: 단일 컬럼 중앙 + 3개 제언 라인
- **Title**: 데이터가 가리키는 방향
- **Core message**: 위험은 예측 가능하다 — 자원을 노인 남성에, 정책을 성장과 분리하라.
- **Content**:
  - 결정 트리 80.18% — 위험은 데이터로 예측 가능하다
  - 제언 1: 노인 남성 자살 예방 프로그램 최우선 강화
  - 제언 2: 경제 성장과 정신건강 지원은 별도 정책 트랙으로
  - 제언 3: 국가별 맞춤 자살 예방 지표 수립에 본 분석 활용

---

## X. Speaker Notes Requirements

- 파일명: SVG와 동일 (`01_cover.svg` → `notes/01_cover.md`)
- 총 발표 시간 10–12분, 스타일: 대화형 + 친절한 설명 (발표자가 도메인 비전문가이므로 용어 풀이 포함)
- 목적: 정보 전달 + 설득 (정책 제언)
- 각 페이지: 핵심 멘트, 용어 설명, 전환 문구, 예상 질문 대비 포인트

---

## XI. Technical Constraints Reminder

1. viewBox: `0 0 1280 720`
2. 배경은 `<rect>`, 줄바꿈은 `<tspan>` (`<foreignObject>` 금지)
3. 투명도 `fill-opacity`/`stroke-opacity` (`rgba()` 금지)
4. 금지: `mask`, `<style>`, `class`, `foreignObject`, `textPath`, `animate*`, `script`
5. HTML named entity 금지 (raw Unicode 사용); `& < >`는 `&amp; &lt; &gt;`로 이스케이프
6. `<g opacity>` 금지 — 자식 요소 개별 지정
7. `clipPath`는 `<image>` 전용
