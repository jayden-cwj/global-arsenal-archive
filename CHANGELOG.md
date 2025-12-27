# Strategic Wisdom Archive - Changelog

## Version 0.0.6 - Wars Collection Architecture (December 28, 2024)

### ⚔️ Major Feature: Wars as Top-Level Organizing Principle

**Purpose:** Restructure the archive to organize content around historical conflicts, showing how defensive structures and strategies were utilized in actual warfare.

**Architectural Change:**
Previously, the archive showed individual fortifications and strategies as standalone entries. Now, wars serve as the primary organizing principle, with defensive structures shown as "utilized" within those conflicts.

**New Hierarchy:**
```
Wars (Top Level)
 └── Defensive Structures Utilized
      └── Individual Fortifications
 └── Strategies Employed
      └── Tactical Systems
```

---

### 🏗️ Implementation

**Wars Collection:**
- Created `_wars` collection in `_config.yml`
- New collection type with permalink structure `/wars/:name/`
- Custom layout `war-template.html` for detailed war pages

**War Template Features:**
- War Information (period, location, result)
- Participants section (multiple sides with leaders)
- Defensive Structures Utilized (links to fortification entries)
- Strategies Employed (tactical systems used)
- Major Battles & Sieges (detailed battle information)
- Casualties & Impact
- Strategic Significance
- Modern Relevance

**Data Schema:**
```yaml
war_info:
  period_en/ko: "Time period"
  location_en/ko: "Geographic location"
  result_en/ko: "Outcome"

participants:
  - side_en/ko: "Allied/Enemy designation"
    nations:
      - name_en/ko: "Nation name"
        leader_en/ko: "Commander/Leader"

defensive_structures:
  - name_en/ko: "Fortress name"
    url: "/link/to/fortification/"
    role_en/ko: "Strategic role in conflict"

major_battles:
  - name_en/ko: "Battle name"
    date: "645 CE"
    location_en/ko: "Battle location"
    result_en/ko: "Battle outcome"
    significance_en/ko: "Historical importance"
```

---

### 📚 First War Entry: Goguryeo-Tang Wars (645-668 CE)

**Historical Context:**
23-year conflict between Goguryeo (Korea) and Tang Dynasty (China), demonstrating sophisticated defensive warfare.

**Content Includes:**
- 5 defensive structures utilized (Ansi, Bisa, Cheonli Jangseong, Baekam, Jeokri)
- 4 major battles documented
- Complete participant information
- Strategic significance analysis
- Modern military applications

**Key Statistics:**
- 300+ lines of historical content
- Complete bilingual support (EN/KO)
- Links to all 5 Goguryeo fortresses from v0.0.5
- Demonstrates network defense principles

---

### 🔄 Military History Page Restructured

**Previous Behavior:**
- Showed both fortifications and strategies as individual cards
- No clear organizing principle

**New Behavior:**
- Shows ONLY war cards organized by era
- Each war card links to detailed war page
- War pages then reference the structures/strategies used

**Visual Design:**
- War cards with red gradient badges (`war-badge`)
- Era-based organization maintained
- Clean separation of wars from individual structures

**User Flow:**
```
Military History → Select War → See Structures Used → Click Structure → View Details
```

---

### 🏰 Cross-Referencing: Wars on Fortifications Page

**New Section Added:**
"Related Wars & Conflicts" reference section on Defense Structures page

**Features:**
- Lists all wars that utilized defensive structures
- Shows era badges (🏛️ Ancient, 🏰 Medieval, etc.)
- Displays war period and fortification count
- Direct links to war detail pages

**Visual Design:**
- Red gradient background with left border accent
- Grid layout for war reference cards
- Hover effects with card elevation
- Responsive design for mobile

**Purpose:**
Allows users browsing fortifications to discover the historical conflicts where those structures played crucial roles.

---

### 🗺️ Navigation Changes

**Wars Menu Removed:**
- No standalone "Wars" navigation item
- Users access wars through "Military History" page
- Prevents duplicate navigation paths

**Final Navigation Structure:**
```
Home → Military History → Defense Structures → Strategies →
Simulator → Map → Insights
```

**Rationale:**
Wars are accessed through Military History (chronological view), while Defense Structures and Strategies remain as browseable collections.

---

### 📁 Files Modified

**Configuration:**
- `_config.yml` - Added wars collection and default layout

**New Files Created:**
- `_layouts/war-template.html` - 400+ lines, comprehensive war display template
- `_wars/goguryeo-tang-wars/goguryeo-tang-wars.md` - 300+ lines, first war entry

**Updated Files:**
- `military-history.md` - Changed to show only wars, added war badge styling
- `fortifications.md` - Added wars reference section with 80+ lines of CSS
- `_layouts/default.html` - Removed Wars from navigation menu

---

### 🎨 Visual Design Elements

**War Badge:**
- Red gradient: `linear-gradient(135deg, #e74c3c, #c0392b)`
- Used on Military History page to distinguish wars from other content types

**Wars Reference Section (Fortifications Page):**
- Background: `linear-gradient(135deg, #e74c3c15, #c0392b15)`
- Left border accent: `#e74c3c` (4px solid)
- Card hover effect: Lift 4px with shadow
- Era badges with emoji icons

**War Detail Pages:**
- Structures Used section: Blue gradient background
- Strategies section: Blue gradient background
- Battles section: Red gradient background
- Significance section: Orange/gold gradient

---

### 📊 Statistics

**New Content:**
- 1 new collection type (wars)
- 1 new layout template (400+ lines)
- 1 comprehensive war entry (300+ lines)
- 80+ lines of new CSS styling
- Complete bilingual support (EN/KO)

**Architecture Changes:**
- Hierarchical content organization (wars → structures → fortifications)
- Cross-referencing between collections (wars ↔ fortifications)
- Centralized access through Military History page

**Code Organization:**
- Modular war template supporting multiple sections
- Reusable card components for cross-references
- Responsive grid layouts throughout

---

### 🎓 Strategic Benefits

**For Users:**
1. **Historical Context:** See how defenses were actually used in warfare
2. **Connected Learning:** Understand relationships between conflicts and structures
3. **Chronological Navigation:** Browse by era to see defensive evolution
4. **Strategic Analysis:** Learn from real-world applications of defensive principles

**For Content:**
1. **Clear Hierarchy:** Wars organize complex military history
2. **Scalability:** Easy to add new wars and link existing structures
3. **Cross-Referencing:** Bidirectional links between wars and fortifications
4. **Flexibility:** Template supports various war types and scales

---

### 💡 Educational Value

**Case Study: Goguryeo-Tang Wars**
Demonstrates:
- **Defense in Depth**: Multiple fortress layers
- **Network Effects**: Integrated defensive systems
- **Asymmetric Warfare**: Small forces defeating larger armies
- **Strategic Planning**: 16-year wall construction project
- **Intelligence Warfare**: Early warning and communication networks

**Modern Applications:**
- Cybersecurity: Defense in depth principles
- Business Strategy: Network defense against competitors
- Military Doctrine: Integrated defensive systems
- Project Management: Long-term strategic infrastructure

---

### 🔮 Future Expansion Ready

**Supported War Types:**
- Ancient conflicts (Greek, Roman, Persian wars)
- Medieval sieges (Crusades, Mongol invasions)
- Modern warfare (World Wars, fortified lines)
- Contemporary conflicts (Modern defensive systems)

**Template Flexibility:**
- Supports multiple participants (coalition warfare)
- Handles various battle types (sieges, field battles, naval)
- Accommodates different strategic systems
- Scales from small battles to world wars

---

### ✨ Key Innovations

1. **Wars as Organizing Principle:** Shifted from structure-centric to conflict-centric view
2. **Bidirectional Cross-Referencing:** Wars → Structures AND Structures → Wars
3. **Integrated Timeline:** Maintains chronological view while adding depth
4. **Modular Template Design:** Reusable sections for different war types
5. **Educational Focus:** Emphasizes strategic lessons and modern applications

---

*Strategic Wisdom Archive v0.0.6*
*"Understanding Defense Through the Lens of History's Conflicts"*

---

## Version 0.0.5 - Goguryeo Defense System (December 27, 2024)

### 🏰 New Content: Five Goguryeo Fortresses

**Purpose:** Document Korea's ancient defensive wisdom through Goguryeo's fortress network that defended against Sui and Tang Dynasty invasions.

**Historical Context:**
Added comprehensive coverage of Goguryeo's sophisticated defense system that successfully resisted Chinese invasions from the 6th-7th centuries CE. These fortresses demonstrate strategic depth, networked defense, and the power of integrated military systems.

**New Fortifications Added:**

1. **Ansi Fortress (안시성)** - The legendary stronghold that withstood Emperor Taizong's 150,000-strong Tang army for 3 months in 645 CE, forcing one of history's greatest emperors to retreat.

2. **Bisa Fortress (비사성 / Great Black Mountain Fortress)** - An impregnable natural fortress surrounded by cliffs on three sides with only a single western gate, demonstrating the power of terrain selection.

3. **Cheonli Jangseong (천리장성 / Thousand Li Wall)** - Goguryeo's answer to China's Great Wall, a 480-500 km defensive system built over 16 years (631-647 CE) to create strategic depth against Tang invasion.

4. **Baekam Fortress (백암성)** - A mountain strongpoint integrated into the Cheonli Jangseong network, showing the value of coordinated defensive systems.

5. **Jeokri Fortress (적리성)** - A forward outpost specializing in early warning and intelligence gathering, proving that information can be more valuable than walls.

**Strategic Themes:**
- **Defense in Depth**: Multiple layers preventing catastrophic breakthroughs
- **Network Effects**: Fortresses supporting each other as integrated systems
- **Intelligence Warfare**: Early warning and rapid communication across hundreds of kilometers
- **Asymmetric Defense**: Small forces defeating larger armies through positioning and strategy
- **Long-term Planning**: 16-year construction projects requiring sustained national commitment

**Data Schema Features:**
- Complete attribution (who built it, who commissioned it)
- Historical siege information (commanders, outcomes, strategic notes)
- Special attributes (legendary sieges, impregnable defenses, network components)
- Modern applications (cybersecurity, business strategy, military doctrine)
- Strategic lessons (terrain advantage, resource optimization, communication networks)

---

### 📁 Files Modified

**New Files Created:**
- `_fortifications/ansi-fortress/ansi-fortress.md` - 300+ lines, comprehensive siege analysis
- `_fortifications/bisa-fortress/bisa-fortress.md` - 200+ lines, natural fortress design
- `_fortifications/cheonli-jangseong/cheonli-jangseong.md` - 350+ lines, mega-project analysis
- `_fortifications/baekam-fortress/baekam-fortress.md` - 200+ lines, network integration
- `_fortifications/jeokri-fortress/jeokri-fortress.md` - 250+ lines, intelligence warfare

**Language Setting:**
- Confirmed English as default language (already set in `_layouts/default.html`)

---

### 📊 Statistics

**New Content:**
- 5 new fortification entries
- 1,300+ lines of historical content
- Medieval era (6th-7th century CE) entries
- Integrated into Military History timeline
- Complete bilingual support (EN/KO)

**Coverage Expansion:**
- Added Korean Peninsula defensive systems
- Documented Goguryeo-Tang Wars (645 CE)
- Included Sui Dynasty invasion responses (612 CE)
- Connected to broader East Asian military history

**Educational Value:**
- Case studies in asymmetric warfare
- Network defense principles
- Strategic foresight and planning
- Information warfare fundamentals
- Terrain and resource optimization

---

### 🎓 Historical Significance

These fortresses represent:
- **Ansi**: How determination and leadership can overcome numerical superiority
- **Bisa**: The power of choosing the right defensive position
- **Cheonli Jangseong**: National commitment to long-term security projects
- **Baekam**: Integration multiplying individual effectiveness
- **Jeokri**: Intelligence as a force multiplier in defense

Together, they form a case study in comprehensive national defense strategy that remains relevant 1,400 years later.

---

## Version 0.0.4 - Era Time Filter (December 27, 2024)

### 🕐 New Feature: Historical Era Filter

**Purpose:** Allow users to filter Military History timeline by specific historical periods.

**Implementation:**
- Added filter button bar to Military History page
- 5 filter options: All Eras, Ancient, Medieval, Modern, Contemporary
- Real-time filtering with smooth animations
- Bilingual filter labels (English/Korean)
- Auto-scroll to timeline after filter selection

**Filter Options:**
- **All Eras**: Show all entries (default)
- **Ancient**: Before 500 CE (고대)
- **Medieval**: 500-1500 (중세)
- **Modern**: 1500-1900 (근대)
- **Contemporary**: 1900-Present (현대)

**Visual Design:**
- Filter bar with gradient background
- Active filter highlighted in blue gradient
- Hover effects on buttons
- Smooth show/hide transitions
- Responsive button layout for mobile

**User Experience:**
- Click any era to show only entries from that period
- Future/Sci-Fi/Fantasy eras excluded from filters (still visible in timeline when "All Eras" selected)
- Smooth scroll to timeline after filter change
- Clear visual feedback for active selection

---

### 📁 Files Modified

**Updated Files:**
- `military-history.md` - Added filter UI, CSS styles, and JavaScript functionality

---

### 📊 Statistics

**New Features:**
- 5 era filter buttons
- 70+ lines of CSS for filter styling
- 50+ lines of JavaScript for filter logic
- Full bilingual support

---

## Version 0.0.3 - Military History Overview Page (December 27, 2024)

### 📚 New Feature: Military History Overview Page

**Purpose:** Provide a comprehensive entry point to explore all archive content organized by historical era.

**Implementation:**
- Created new `/military-history/` page as primary navigation entry point
- Combines both fortifications and strategies in chronological view
- Era-based organization (Ancient, Medieval, Modern, Contemporary, Future, Sci-Fi, Fantasy)
- Archive statistics dashboard
- Quick navigation cards to category pages

**Page Sections:**
1. **Archive Statistics:** Shows total defense structures, strategic systems, and combined entries
2. **Historical Timeline:** All entries organized by era with type badges (Defense Structure / Strategic System)
3. **Quick Navigation:** Cards linking to Fortifications and Strategies collection pages

**Visual Features:**
- Era sections with emoji icons (🏛️ Ancient, 🏰 Medieval, ⚔️ Modern, etc.)
- Type badges color-coded: Blue for Defense Structures, Purple for Strategic Systems
- Entry cards showing title, summary, and year (BCE/CE notation)
- Hover effects and responsive grid layout
- Fully bilingual (English/Korean)

**Navigation Update:**
- New navigation order: Home → **Military History** → Defense Structures → Strategies → Simulator → Map → Insights
- Renamed "Fortifications" to "Defense Structures" in navigation for clarity

**Benefits:**
- Single page to see entire archive scope
- Historical context at a glance
- Easy comparison between eras
- Clear distinction between physical structures and strategic systems

---

### 📁 Files Modified

**New Files:**
- `military-history.md` - Main overview page with timeline and statistics

**Updated Files:**
- `_layouts/default.html` - Added Military History to navigation (first position after Home)
- `README.md` - Updated site structure documentation to reflect new page and reorganized sections

---

### 📊 Statistics

**New Content:**
- 1 new major navigation page
- 400+ lines of page content and embedded CSS
- Complete bilingual support
- Dynamic content generation from Jekyll collections

---

## Version 0.0.2 - Attribution & Historical Context (December 27, 2024)

### 🏗️ New Feature: Attribution System (Fortifications)

**Purpose:** Answer "Who built it?" and "Who commissioned it?"

**Implementation:**
- Added `attribution` field to fortification schema
- Supports multiple construction phases
- Bilingual support for all attribution data

**Data Fields:**
- `phase_en/ko`: Construction period/phase name
- `commissioner_en/ko`: Who ordered the construction
- `commissioner_role_en/ko`: Why they commissioned it
- `chief_architect_en/ko`: Who designed it
- `architect_role_en/ko`: Their contribution
- `workforce_en/ko`: Labor force information

**Example - Great Wall:**
- Qin Dynasty Phase (221-206 BC): Emperor Qin Shi Huang + General Meng Tian
- Ming Dynasty Phase (1368-1644): Ming Emperors + General Qi Jiguang
- Shows 300,000-500,000 workers (Qin) and millions over 276 years (Ming)

---

### ⚔️ New Feature: Historical Applications (Strategies)

**Purpose:** Track "Who used this strategy?", "When?", and "Against whom?"

**Implementation:**
- Added `historical_applications` field to strategy schema
- Documents real-world usage of defensive tactics
- Shows outcomes and strategic lessons

**Data Fields:**
- `period_en/ko`: When the strategy was used
- `commander_en/ko`: Who implemented it
- `threat_en/ko`: What enemy/threat it faced
- `outcome_en/ko`: Results of using the strategy
- `strategic_notes_en/ko`: Key observations

**Example - Hwaseong Defense:**
- 1796-1800: Political consolidation under King Jeongjo
- 1950-1951: Korean War tactical positions
- 1975-Present: Cultural heritage protection strategy

---

### 🎨 Visual Design

**Attribution Section (Blue Theme):**
- Blue gradient background (#34495e, #2c3e50)
- Left border accent (#3498db)
- Phase-based organization
- Role descriptions in italic gray

**Historical Applications Section (Purple Theme):**
- Purple gradient background (#8e44ad, #9b59b6)
- Left border accent (#9b59b6)
- Application instance cards
- Strategic notes in italic purple

---

### 📁 Files Modified

**Data Files:**
- `_fortifications/great-wall/great-wall.md` - Added 2 attribution phases
- `_strategies/hwaseong-defense/hwaseong-defense.md` - Added 3 historical applications

**Templates:**
- `_layouts/fortification-template.html` - Added attribution display section
- `_layouts/strategy-template.html` - Added historical applications display section

**Styles:**
- `assets/css/style.css` - Added 100+ lines for attribution and applications styling

**Documentation:**
- `README.md` - Documented both new schema features with full YAML examples

---

### 🔑 Key Distinction

**Fortifications** (Physical Structures):
- Focus: Who built it and who commissioned it
- Attribution shows creators and sponsors
- Example: Emperor + Architect + Workforce

**Strategies** (Tactical Systems):
- Focus: Who used it, when, and against whom
- Historical applications show usage in practice
- Example: Commander + Enemy + Outcome

---

### 📊 Statistics

**New Data:**
- 2 attribution phases for Great Wall (Qin + Ming dynasties)
- 3 historical applications for Hwaseong (1796-Present)
- 100+ lines of new CSS styling
- Comprehensive bilingual documentation

**Schema Expansion:**
- Fortifications: 8 new attribution fields per phase
- Strategies: 8 new application fields per instance

---

## Version 0.0.1 - Initial Release (December 27, 2024)

### 🎯 Complete Rebranding: Arsenal → Strategic Wisdom

**From:** Global Arsenal Archive (weapons/wars database)  
**To:** Strategic Wisdom Archive (defense/protection platform)

---

## ✅ Language Toggle System Fixed

### Issue Resolved
- Fixed CSS `display: revert` compatibility issue
- Proper block/inline display handling for all elements
- Created comprehensive test page: `test-language-toggle.html`

### Verification
- ✓ 30 EN + 30 KO content pairs in index (perfect 1:1 ratio)
- ✓ All navigation items bilingual
- ✓ Headers, footers, and content properly toggle
- ✓ LocalStorage persistence working

---

## 📊 New Metric: Strategic Utility

### Added to All Entries
**Metric:** `strategic_utility` (0-100)  
**Purpose:** Quantifies overall strategic value beyond physical defense

**Values Set:**
- Great Wall: 88/100
- Hwaseong: 92/100

### Implementation
- ✅ Added to data schema (fortifications & strategies)
- ✅ Displayed in detail page templates
- ✅ Integrated into simulator calculations
- ✅ Color-coded orange metric bar
- ✅ New simulator slider with 20% weight
- ✅ Updated README documentation

### Simulator Weight Distribution
```
Communication: 25% (was 30%)
Strategic Utility: 20% (NEW)
Durability: 20% (was 25%)
Deterrence: 12% (was 15%)
Terrain: 15% (was 20%)
Resources: 8% (was 10%)
Total: 100%
```

---

## 🏷️ New Feature: Special Attributes Tags

### System Overview
Beyond numeric metrics, entries can now have qualitative tags for unique characteristics.

### Example Tags Added

**Great Wall:**
- ✦ UNESCO World Heritage Site
- ✦ Ancient Wonder of the World
- ✦ Longest Structure Ever Built
- ✦ Revolutionary Communication System

**Hwaseong Fortress:**
- ✦ UNESCO World Heritage Site (1997)
- ✦ Scientific Design Methodology
- ✦ Comprehensive Construction Records (Uigwe)
- ✦ East-West Architectural Synthesis

### Visual Design
- Color-coded gradient badges
- Different colors per tag type:
  - Purple: UNESCO Heritage
  - Red: Ancient Wonder
  - Blue: Innovation/Science
  - Green: Records/Structure
  - Orange: Hybrid Architecture
- Hover animations
- Bilingual labels
- Special section above metrics

---

## 📁 Files Modified

### Data Files
- `_fortifications/great-wall/great-wall.md` - Added strategic_utility + special_attributes
- `_strategies/hwaseong-defense/hwaseong-defense.md` - Added strategic_utility + special_attributes

### Templates
- `_layouts/fortification-template.html` - Added strategic_utility metric display + special attributes section
- `_layouts/strategy-template.html` - Added strategic_utility metric display + special attributes section

### Simulator
- `simulator.md` - Added 6th slider for strategic_utility, updated weights, added to presets

### Styles
- `assets/css/style.css` - Fixed language toggle CSS + added special attributes badge styles

### Documentation
- `README.md` - Documented strategic_utility metric + special attributes system + updated YAML examples

### Testing
- `test-language-toggle.html` - Comprehensive language toggle verification page

---

## 🎨 Design Enhancements

### Special Attributes Section
- Gradient background with left border accent
- Gold/orange color scheme
- Responsive badge layout
- Hover lift effect
- Icon prefixes (✦)

### Metric Bars
- Strategic Utility has distinct orange gradient
- All other metrics retain blue gradient
- Consistent 0-100 scale display

---

## 📚 Documentation Updates

### README.md Additions
1. Strategic Utility metric explanation
2. Special Attributes tag system
3. Complete tag type list
4. Updated YAML examples
5. Color-coded badge information

---

## 🧪 Testing Artifacts

### New Test Files
- `test-language-toggle.html` - 4 comprehensive tests for EN/KO switching

### Preview Files (Already Updated)
- `preview-index.html` ✓
- `preview-fortifications.html` ✓
- `preview-great-wall.html` ✓
- `preview-simulator.html` ✓

---

## 💡 Key Innovations

### 1. Dual Metric System
- **Quantitative:** Numeric scores (0-100)
- **Qualitative:** Special attribute tags

### 2. Strategic Value Focus
- Moved beyond physical metrics
- Captures intangible attributes (heritage, innovation, documentation)
- Supports future expansion with custom tags

### 3. Visual Hierarchy
- Tags appear before numeric metrics
- Gold/orange scheme distinguishes from blue metrics
- Clear separation of "what makes it special" vs "how effective it is"

---

## 🔮 Future Enhancements Ready

### Tag System Supports
- Custom tag creation
- Tag filtering on collection pages
- Tag-based search
- Tag intersection analysis
- Historical value categorization

### Metric System Supports
- Custom metric definitions
- Weighted calculations
- Comparison views
- Trend analysis

---

## 📊 Statistics

**Total Changes:**
- 8 files modified
- 1 new test file created
- 2 new data fields added (strategic_utility + special_attributes)
- 90+ lines of new CSS
- 6-variable simulator (was 5)
- 4 special attributes per example entry

**Language Coverage:**
- 100% bilingual (EN/KO)
- All new features fully translated
- Consistent terminology

---

## ✨ User Benefits

1. **Richer Context:** Tags provide historical/cultural significance
2. **Better Decisions:** Strategic utility quantifies overall value
3. **Clear Categorization:** Visual tags vs numeric metrics
4. **Flexible System:** Easy to add new tags/metrics
5. **Educational Value:** Tags explain *why* something matters
6. **Beautiful UI:** Color-coded, animated, professional badges

---

*Strategic Wisdom Archive v0.0.5*
*"From Destruction to Protection, From Arsenal to Architecture"*
