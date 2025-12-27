# Strategic Wisdom Archive - Changelog

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

*Strategic Wisdom Archive v0.0.2*
*"From Destruction to Protection, From Arsenal to Architecture"*
