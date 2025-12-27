# Site Structure

The Strategic Wisdom Archive is organized into six main sections and three interactive tools.

## Main Sections

### 1. Military History
A comprehensive overview page showing all wars and conflicts organized by historical era. This serves as the main entry point to explore the archive chronologically, from ancient conflicts to contemporary warfare.

**Key Features:**
- Wars organized by era (Ancient, Medieval, Modern, Contemporary)
- Each war shows defensive structures utilized
- Era filter for quick navigation
- Links to detailed war pages

[Explore Military History →](/military-history/)

---

### 2. Defense Structures (Fortifications)
Individual fortifications, walls, and defensive architecture with detailed attribution (who built it, who commissioned it), metrics, and historical context.

**Key Features:**
- Detailed metrics (deterrence, durability, communication, terrain)
- Construction attribution (commissioners, architects, workforce)
- Special attributes badges (UNESCO sites, ancient wonders, etc.)
- Era and location filters
- Related wars reference section

[Browse Defense Structures →](/fortifications/)

---

### 3. Strategies
Tactical systems and defensive strategies with historical applications showing who used them, when, and against whom. Includes outcomes and strategic lessons learned.

**Key Features:**
- Historical applications (commander, threat, outcome)
- Strategic metrics and analysis
- Cross-references to related fortifications
- Era-based organization

[Browse Strategies →](/strategies/)

---

## Interactive Tools

### 1. Strategic Logic Simulator
An interactive calculator where you adjust defense system variables to see their impact on survival probability.

**Variables:**
- Deterrence Level
- Communication Efficiency
- Defensive Durability
- Terrain Advantage
- Resource Cost
- Strategic Utility

**Learn by experimentation:** How do different factors interact? What's the optimal resource allocation?

[Try the Simulator →](/simulator/)

---

### 2. Interactive Defense Map
A global visualization showing where and why humanity built its greatest defensive systems. Geographic patterns reveal strategic thinking about terrain, trade routes, communication networks, and threat vectors.

**Features:**
- Interactive Leaflet.js map
- Color-coded by era
- Popup information for each structure
- Geographic clustering

[Explore the Map →](/map/)

---

### 3. Wisdom Chronicles (Bilingual Insights)
Monthly insights connecting historical defensive strategies to modern challenges:
- Leadership & decision-making
- System design & resilience
- Innovation under constraints
- Peace studies & conflict prevention

Each post analyzes a specific fortification or strategy and extracts principles applicable to:
- **Business:** Crisis management, organizational resilience
- **Technology:** Cybersecurity, system architecture
- **Policy:** Public safety, strategic planning

[Read the Latest Insights →](/insights/)

---

## Bilingual Support

All content is available in both English (EN) and Korean (KO):
- **Military History:** 군사 역사
- **Defense Structures:** 방어 구조
- **Strategies:** 전략
- **Insights:** 인사이트

The language toggle preserves user preference via localStorage.

---

## Repository Structure

```
strategic-wisdom-archive/
├── _config.yml                    # Jekyll configuration
├── _wars/                         # Wars collection
│   └── [war-name]/
│       └── [war-name].md
├── _fortifications/               # Defense structures collection
│   └── [item-name]/
│       └── [item-name].md
├── _strategies/                   # Tactical systems collection
│   └── [item-name]/
│       └── [item-name].md
├── _insights/                     # Newsletter posts collection
│   └── YYYY-MM-title.md
├── _layouts/                      # HTML templates
│   ├── default.html               # Base layout
│   ├── war-template.html
│   ├── fortification-template.html
│   ├── strategy-template.html
│   └── insight-template.html
├── assets/
│   ├── css/
│   │   └── style.css              # Main stylesheet
│   └── images/
│       ├── fortifications/
│       └── strategies/
├── docs/                          # Documentation
│   ├── site-structure.md
│   ├── data-schema.md
│   └── getting-started.md
├── index.md                       # Homepage
├── military-history.md            # Military history overview page
├── fortifications.md              # Fortifications collection page
├── strategies.md                  # Strategies collection page
├── insights.md                    # Insights index
├── simulator.md                   # Logic simulator
├── map.md                         # Interactive map
└── README.md                      # Project overview
```

---

## Educational Use

This archive is designed for:
- **Students:** Learning about strategic thinking and historical decision-making
- **Leaders:** Understanding crisis management and organizational resilience
- **Designers:** Studying system architecture and sustainable design principles
- **Researchers:** Exploring peace studies and conflict prevention strategies

### Case Studies Included:
- **Great Wall of China:** Information networks as defense
- **Hwaseong Fortress:** Scientific methodology in defensive design
- **Goguryeo Fortress Network:** Defense in depth and asymmetric warfare
- *More coming soon...*
