# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## colors
- bg: #F5F7FA
- card_bg: #FFFFFF
- primary: #1E3A5F
- accent: #E63946
- secondary_accent: #457B9D
- text: #2B2D33
- text_secondary: #5C6470
- text_tertiary: #9AA3AF
- border: #D8DEE6
- success: #2A9D8F
- primary_dark: #16293F
- text_on_dark_muted: #8DA3BB
- text_on_dark_soft: #B9C6D6
- accent_soft: #F4A7AE

## typography
- font_family: "Malgun Gothic", "Apple SD Gothic Neo", Arial, sans-serif
- code_family: Consolas, "Courier New", monospace
- body: 18
- title: 30
- subtitle: 22
- annotation: 14
- cover_title: 56
- section_title: 40
- hero_number: 90
- chart_annotation: 13
- footnote: 11

## icons
- library: phosphor-duotone
- inventory: globe, database, users, calendar, magnifying-glass, chart-bar, chart-line, brain, gear, chart-scatter, chart-bar-horizontal, target, lightbulb, trend-up, trend-down, warning, shield-check, scales, heartbeat, hand-heart, check-circle, strategy, gender-male, presentation-chart, flask, arrow-right

## images
- eda_overview: images/01_eda_overview.png | no-crop
- pca: images/02_pca.png | no-crop
- elbow: images/03_elbow.png | no-crop
- kmeans: images/04_kmeans.png | no-crop
- model_compare: images/05_model_compare.png | no-crop
- confusion: images/06_confusion.png | no-crop
- feature_importance: images/07_feature_importance.png | no-crop
- insights: images/08_insights.png | no-crop
- country_top10: images/09_country_top10.png | no-crop

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: breathing
- P11: dense
- P12: dense
- P13: dense
- P14: breathing

## page_charts
- P02: agenda_list
- P03: kpi_cards
- P06: pipeline_with_stages
- P12: icon_grid
- P13: vertical_list

## forbidden
- Mixing icon libraries
- rgba()
- `<style>`, `class`, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<script>`, `<iframe>`, `<symbol>`+`<use>`
- `<g opacity>` (set opacity on each child element individually)
- HTML named entities in text — raw Unicode only; escape XML reserved chars as `&amp; &lt; &gt; &quot; &apos;`
