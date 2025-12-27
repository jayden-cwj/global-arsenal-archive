# Data Schema

This document describes the data structure for all content types in the Strategic Wisdom Archive.

---

## Wars

Wars serve as the top-level organizing principle, showing how defensive structures and strategies were utilized in historical conflicts.

### YAML Structure

```yaml
---
layout: war-template
id: "war-identifier"
title_en: "English War Title"
title_ko: "한국어 전쟁 제목"
summary_en: "English summary"
summary_ko: "한국어 요약"
era: "ancient|medieval|modern|contemporary"
year: 645  # Primary year for sorting

# War Information
war_info:
  period_en: "645-668 CE"
  period_ko: "645-668년"
  location_en: "Korean Peninsula and Manchuria"
  location_ko: "한반도 및 만주"
  result_en: "Strategic outcome"
  result_ko: "전략적 결과"

# Participants
participants:
  - side_en: "Allied Forces"
    side_ko: "동맹군"
    nations:
      - name_en: "Nation Name"
        name_ko: "국가 이름"
        leader_en: "Commander Name"
        leader_ko: "지휘관 이름"

  - side_en: "Enemy Forces"
    side_ko: "적군"
    nations:
      - name_en: "Enemy Nation"
        name_ko: "적국"
        leader_en: "Enemy Commander"
        leader_ko: "적군 지휘관"

# Defensive Structures Used
defensive_structures:
  - name_en: "Fortress Name"
    name_ko: "요새 이름"
    url: "/fortifications/fortress-name/"
    role_en: "Strategic role in the war"
    role_ko: "전쟁에서의 전략적 역할"

# Strategies Employed
strategies_employed:
  - name_en: "Strategy Name"
    name_ko: "전략 이름"
    url: "/strategies/strategy-name/"  # Optional
    description_en: "How this strategy was used"
    description_ko: "이 전략이 어떻게 사용되었는지"

# Major Battles
major_battles:
  - name_en: "Battle Name"
    name_ko: "전투 이름"
    date: "645 CE"
    location_en: "Battle location"
    location_ko: "전투 장소"
    result_en: "Battle outcome"
    result_ko: "전투 결과"
    significance_en: "Why this battle mattered"
    significance_ko: "이 전투가 중요한 이유"

# Casualties
casualties:
  - side_en: "Allied Forces"
    side_ko: "동맹군"
    casualties_en: "Estimated 50,000"
    casualties_ko: "약 50,000명"

# Strategic Significance
strategic_significance_en: "Overall strategic importance..."
strategic_significance_ko: "전반적인 전략적 중요성..."

# Modern Relevance
modern_relevance_en:
  - "Application to modern military doctrine"
  - "Lessons for cybersecurity"
modern_relevance_ko:
  - "현대 군사 교리에 대한 적용"
  - "사이버 보안에 대한 교훈"
---

# Main content in markdown...
```

---

## Fortifications

Defense structures (castles, walls, fortresses) with detailed metrics and attribution.

### Metrics

- **deterrence_level** (0-100): Psychological impact on potential attackers
- **communication_efficiency** (0-100): Signal network effectiveness
- **defensive_durability** (0-100): Physical resistance to assault
- **terrain_advantage** (0-100): Use of natural geography
- **resource_cost** (0-100): Construction and maintenance burden
- **strategic_utility** (0-100): Overall strategic value and effectiveness

### YAML Structure

```yaml
---
layout: fortification-template
id: "fortification-id"
title_en: "English Title"
title_ko: "한국어 제목"
summary_en: "English description"
summary_ko: "한국어 설명"
location: [latitude, longitude]
era: "ancient|medieval|modern|contemporary|future|scifi|fantasy"
year: 500  # For sorting

# Special attributes (optional)
special_attributes:
  - tag: "unesco-world-heritage"
    label_en: "UNESCO World Heritage Site"
    label_ko: "유네스코 세계문화유산"
  - tag: "scientific-design"
    label_en: "Scientific Design Methodology"
    label_ko: "과학적 설계 방법론"

# Attribution - Who built it and who commissioned it (optional)
attribution:
  - phase_en: "Initial Construction (1400-1450)"
    phase_ko: "초기 건설 (1400-1450년)"
    commissioner_en: "King Name"
    commissioner_ko: "왕 이름"
    commissioner_role_en: "Ordered construction for border defense"
    commissioner_role_ko: "국경 방어를 위해 건설 명령"
    chief_architect_en: "Architect Name"
    chief_architect_ko: "건축가 이름"
    architect_role_en: "Designed the fortification system"
    architect_role_ko: "요새 시스템 설계"
    workforce_en: "10,000 workers over 5 years"
    workforce_ko: "5년 동안 10,000명의 노동자"

  - phase_en: "Expansion Phase (1500-1550)"
    phase_ko: "확장 단계 (1500-1550년)"
    # ... additional phases

# Numeric metrics
metrics:
  deterrence_level: 85
  communication_efficiency: 70
  defensive_durability: 90
  terrain_advantage: 75
  resource_cost: 60
  strategic_utility: 80

# Famous sieges (optional)
famous_siege:
  year: 645
  duration_en: "3 months (60+ days)"
  duration_ko: "3개월 (60일 이상)"
  defender_en: "Commander Name"
  defender_ko: "지휘관 이름"
  attacker_en: "Enemy Commander"
  attacker_ko: "적군 지휘관"
  outcome_en: "Victory/Defeat"
  outcome_ko: "승리/패배"
---

# Content in markdown...
```

### Special Attribute Tags

Available tag types:
- **unesco-world-heritage**: UNESCO World Heritage Site
- **ancient-wonder**: Ancient Wonder of the World
- **scientific-design**: Scientific Design Methodology
- **communication-innovation**: Revolutionary Communication System
- **hybrid-architecture**: East-West Architectural Synthesis
- **longest-structure**: Longest Structure Ever Built
- **legendary-siege**: Famous Historical Siege
- **impregnable-defense**: Never Conquered Fortress
- **mega-construction**: Major Construction Project
- **network-component**: Part of Larger Defensive Network

---

## Strategies

Historical defensive tactics and innovations with metrics and applications.

### Metrics

- **deterrence_level** (0-100): Conflict prevention effectiveness
- **communication_efficiency** (0-100): Information flow
- **innovation_index** (0-100): Technological advancement
- **defensive_durability** (0-100): Structural strength
- **strategic_utility** (0-100): Overall strategic value

### YAML Structure

```yaml
---
layout: strategy-template
id: "strategy-id"
title_en: "English Strategy Title"
title_ko: "한국어 전략 제목"
summary_en: "English description"
summary_ko: "한국어 설명"
location: [latitude, longitude]
era: "ancient|medieval|modern|contemporary|future|scifi|fantasy"
year: 1200  # For sorting

# Historical Applications - Who used this strategy, when, and against whom
historical_applications:
  - period_en: "1200-1250: First Implementation"
    period_ko: "1200-1250년: 최초 적용"
    commander_en: "General Name"
    commander_ko: "장군 이름"
    threat_en: "Invading army from neighboring kingdom"
    threat_ko: "인접 왕국의 침략군"
    outcome_en: "Successfully repelled invasion"
    outcome_ko: "침략을 성공적으로 격퇴"
    strategic_notes_en: "Strategy proved effective due to terrain"
    strategic_notes_ko: "지형으로 인해 전략이 효과적임이 입증됨"

  - period_en: "1300-1350: Later Application"
    period_ko: "1300-1350년: 후기 적용"
    # ... additional applications

# Numeric metrics
metrics:
  deterrence_level: 80
  communication_efficiency: 75
  innovation_index: 90
  defensive_durability: 70
  strategic_utility: 85
---

# Content in markdown...
```

---

## Insights (Blog Posts)

Monthly insights connecting historical defensive strategies to modern challenges.

### YAML Structure

```yaml
---
layout: insight-template
id: "2025-01-insight-title"
title_en: "English Insight Title"
title_ko: "한국어 인사이트 제목"
summary_en: "Brief summary in English"
summary_ko: "한국어 간단한 요약"
publish_date: "2025-01-15"
author_en: "Author Name"
author_ko: "저자 이름"

# Related entries (optional)
related_fortifications:
  - "fortification-id"
related_strategies:
  - "strategy-id"

# Modern applications
modern_applications:
  - category_en: "Business Strategy"
    category_ko: "비즈니스 전략"
    application_en: "How this applies to business"
    application_ko: "비즈니스에 적용되는 방법"

  - category_en: "Cybersecurity"
    category_ko: "사이버 보안"
    application_en: "Security lessons"
    application_ko: "보안 교훈"
---

# Content in markdown...
```

---

## Era Categories

All entries use these era classifications:

- **ancient** - Before 500 CE (고대)
- **medieval** - 500-1500 (중세)
- **modern** - 1500-1900 (근대)
- **contemporary** - 1900-Present (현대)
- **future** - Conceptual designs (미래)
- **scifi** - Science fiction (공상 과학)
- **fantasy** - Fantasy settings (판타지)

---

## Data Validation

### Required Fields (All Types)
- `layout`
- `id`
- `title_en` / `title_ko`
- `summary_en` / `summary_ko`
- `era`
- `year`

### Optional but Recommended
- `special_attributes` (fortifications)
- `attribution` (fortifications)
- `historical_applications` (strategies)
- `defensive_structures` (wars)
- `major_battles` (wars)

### Location Format
```yaml
location: [latitude, longitude]
# Example: [37.7749, -122.4194]
```

### URL Format
Internal links should use relative URLs:
```yaml
url: "/fortifications/fortress-name/"
url: "/strategies/strategy-name/"
url: "/wars/war-name/"
```

---

## Bilingual Content

Every text field must have both English (`_en`) and Korean (`_ko`) versions:

```yaml
title_en: "Great Wall of China"
title_ko: "만리장성"

summary_en: "Ancient defensive fortification system"
summary_ko: "고대 방어 요새 시스템"
```

This ensures complete bilingual support throughout the site.
