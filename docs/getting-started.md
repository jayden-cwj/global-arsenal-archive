# Getting Started

This guide will help you set up the Strategic Wisdom Archive for local development and contribute new content.

---

## Technical Stack

- **Static Site Generator:** Jekyll
- **Hosting:** GitHub Pages
- **Map Visualization:** Leaflet.js
- **Styling:** Custom CSS with responsive design
- **Language Support:** Bilingual (English/Korean) with client-side toggle
- **Data Format:** YAML front matter with markdown content

---

## Local Development

### Prerequisites

- Ruby (version 2.5 or higher)
- RubyGems
- GCC and Make

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/jayden-cwj/strategic-wisdom-archive.git
   cd strategic-wisdom-archive
   ```

2. **Install Jekyll:**
   ```bash
   gem install bundler jekyll
   bundle install
   ```

3. **Run locally:**
   ```bash
   bundle exec jekyll serve
   ```

4. **View in browser:**
   ```
   http://localhost:4000/strategic-wisdom-archive/
   ```

The site will automatically rebuild when you make changes to files.

---

## Adding New Content

### Add a War

Wars organize how defensive structures and strategies were used in historical conflicts.

1. **Create directory and file:**
   ```bash
   mkdir -p _wars/war-name
   nano _wars/war-name/war-name.md
   ```

2. **Add YAML front matter:**
   ```yaml
   ---
   layout: war-template
   id: "war-name"
   title_en: "English War Name"
   title_ko: "한국어 전쟁 이름"
   summary_en: "Brief description"
   summary_ko: "간단한 설명"
   era: "medieval"
   year: 1200

   war_info:
     period_en: "1200-1250"
     period_ko: "1200-1250년"
     location_en: "Geographic location"
     location_ko: "지리적 위치"
     result_en: "War outcome"
     result_ko: "전쟁 결과"

   participants:
     - side_en: "Allied Forces"
       side_ko: "동맹군"
       nations:
         - name_en: "Nation Name"
           name_ko: "국가 이름"
           leader_en: "Leader Name"
           leader_ko: "지도자 이름"

   defensive_structures:
     - name_en: "Fortress Name"
       name_ko: "요새 이름"
       url: "/fortifications/fortress-name/"
       role_en: "Role in the war"
       role_ko: "전쟁에서의 역할"

   major_battles:
     - name_en: "Battle Name"
       name_ko: "전투 이름"
       date: "1215"
       location_en: "Battle location"
       location_ko: "전투 장소"
       result_en: "Battle result"
       result_ko: "전투 결과"
       significance_en: "Why it mattered"
       significance_ko: "중요한 이유"

   strategic_significance_en: "Overall significance..."
   strategic_significance_ko: "전반적인 중요성..."

   modern_relevance_en:
     - "Modern application 1"
     - "Modern application 2"
   modern_relevance_ko:
     - "현대적 적용 1"
     - "현대적 적용 2"
   ---

   # Content in markdown format

   ## Background
   Historical context...

   ## Course of the War
   How events unfolded...

   ## Outcome and Legacy
   Long-term impact...
   ```

3. **Test locally:**
   ```bash
   bundle exec jekyll serve
   ```

4. **View at:** `http://localhost:4000/strategic-wisdom-archive/wars/war-name/`

---

### Add a Fortification

1. **Create directory and file:**
   ```bash
   mkdir -p _fortifications/fortress-name
   nano _fortifications/fortress-name/fortress-name.md
   ```

2. **Add YAML front matter:**
   ```yaml
   ---
   layout: fortification-template
   id: "fortress-name"
   title_en: "English Fortress Name"
   title_ko: "한국어 요새 이름"
   summary_en: "Brief description"
   summary_ko: "간단한 설명"
   location: [latitude, longitude]
   era: "medieval"
   year: 1200

   special_attributes:
     - tag: "unesco-world-heritage"
       label_en: "UNESCO World Heritage Site"
       label_ko: "유네스코 세계문화유산"

   attribution:
     - phase_en: "Construction Phase (1200-1250)"
       phase_ko: "건설 단계 (1200-1250년)"
       commissioner_en: "Who ordered it"
       commissioner_ko: "누가 명령했는지"
       commissioner_role_en: "Why they commissioned it"
       commissioner_role_ko: "왜 의뢰했는지"
       chief_architect_en: "Who designed it"
       chief_architect_ko: "누가 설계했는지"
       architect_role_en: "Their role"
       architect_role_ko: "그들의 역할"
       workforce_en: "Who built it"
       workforce_ko: "누가 건설했는지"

   metrics:
     deterrence_level: 85
     communication_efficiency: 70
     defensive_durability: 90
     terrain_advantage: 75
     resource_cost: 60
     strategic_utility: 80
   ---

   # Content in markdown format

   ## History
   Construction and historical context...

   ## Design Features
   Architectural details...

   ## Strategic Role
   Military significance...

   ## Modern Applications
   Contemporary relevance...
   ```

3. **Add image (optional):**
   ```bash
   cp fortress-image.jpg assets/images/fortifications/fortress-name.jpg
   ```

   Then add to YAML:
   ```yaml
   thumbnail: "/assets/images/fortifications/fortress-name.jpg"
   ```

---

### Add a Strategy

1. **Create directory and file:**
   ```bash
   mkdir -p _strategies/strategy-name
   nano _strategies/strategy-name/strategy-name.md
   ```

2. **Add YAML front matter:**
   ```yaml
   ---
   layout: strategy-template
   id: "strategy-name"
   title_en: "English Strategy Name"
   title_ko: "한국어 전략 이름"
   summary_en: "Brief description"
   summary_ko: "간단한 설명"
   location: [latitude, longitude]
   era: "medieval"
   year: 1200

   historical_applications:
     - period_en: "1200-1250: First Use"
       period_ko: "1200-1250년: 최초 사용"
       commander_en: "Who used it"
       commander_ko: "누가 사용했는지"
       threat_en: "What threat faced"
       threat_ko: "어떤 위협에 직면했는지"
       outcome_en: "Result"
       outcome_ko: "결과"
       strategic_notes_en: "Analysis"
       strategic_notes_ko: "분석"

   metrics:
     deterrence_level: 80
     communication_efficiency: 75
     innovation_index: 90
     defensive_durability: 70
     strategic_utility: 85
   ---

   # Content in markdown format

   ## Overview
   What this strategy is...

   ## Implementation
   How it was used...

   ## Effectiveness
   Why it worked...

   ## Modern Parallels
   Contemporary applications...
   ```

---

### Add an Insight Post

1. **Create file:**
   ```bash
   nano _insights/2025-01-insight-title.md
   ```

2. **Add YAML front matter:**
   ```yaml
   ---
   layout: insight-template
   id: "2025-01-insight-title"
   title_en: "English Title"
   title_ko: "한국어 제목"
   summary_en: "Brief summary"
   summary_ko: "간단한 요약"
   publish_date: "2025-01-15"
   author_en: "Author Name"
   author_ko: "저자 이름"

   related_fortifications:
     - "fortress-name"
   related_strategies:
     - "strategy-name"

   modern_applications:
     - category_en: "Business"
       category_ko: "비즈니스"
       application_en: "How it applies"
       application_ko: "적용 방법"
   ---

   # Content in markdown format

   ## Introduction
   Hook the reader...

   ## Historical Context
   Explain the defensive system...

   ## Strategic Lessons
   What we can learn...

   ## Modern Applications
   How to apply today...

   ## Conclusion
   Key takeaways...
   ```

---

## Development Workflow

1. **Create a new branch:**
   ```bash
   git checkout -b feature/add-new-fortress
   ```

2. **Make changes and test locally:**
   ```bash
   bundle exec jekyll serve
   ```

3. **Commit changes:**
   ```bash
   git add .
   git commit -m "Add new fortress: Fortress Name"
   ```

4. **Push to GitHub:**
   ```bash
   git push origin feature/add-new-fortress
   ```

5. **Create Pull Request on GitHub**

---

## File Naming Conventions

- **Wars:** `_wars/war-name/war-name.md`
- **Fortifications:** `_fortifications/fortress-name/fortress-name.md`
- **Strategies:** `_strategies/strategy-name/strategy-name.md`
- **Insights:** `_insights/YYYY-MM-title.md`
- **Images:** `assets/images/fortifications/fortress-name.jpg`

Use lowercase with hyphens for all file and directory names.

---

## Troubleshooting

### Jekyll won't start
```bash
# Update dependencies
bundle update
bundle install

# Clear cache
bundle exec jekyll clean
bundle exec jekyll serve
```

### Changes not showing
- Hard refresh browser (Cmd+Shift+R or Ctrl+Shift+R)
- Check Jekyll console for build errors
- Verify YAML syntax is correct

### Map markers not appearing
- Verify `location: [lat, lng]` is valid
- Check JavaScript console for errors
- Ensure coordinates are in correct format (decimal degrees)

---

## Best Practices

### Content Quality
- Write clear, concise summaries
- Include both English and Korean for all text
- Add attributions for historical accuracy
- Link related entries (wars ↔ fortifications ↔ strategies)

### YAML Formatting
- Use 2 spaces for indentation (not tabs)
- Quote strings with special characters
- Validate YAML before committing

### Bilingual Content
- Translate all user-facing text
- Keep translations conceptually aligned
- Use appropriate formality in Korean (formal/존댓말)

### Images
- Optimize images before uploading (< 500KB)
- Use descriptive filenames
- Add alt text in templates

---

## Additional Resources

- **Jekyll Documentation:** [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
- **Leaflet.js Documentation:** [https://leafletjs.com/](https://leafletjs.com/)
- **YAML Syntax:** [https://yaml.org/](https://yaml.org/)
- **Markdown Guide:** [https://www.markdownguide.org/](https://www.markdownguide.org/)

---

## Contributing

We welcome contributions! Please:
1. Fork the repository
2. Create a feature branch
3. Add your content following the data schema
4. Test locally
5. Submit a pull request

For questions or suggestions:
- **GitHub Issues:** [Report a problem or suggest a feature](https://github.com/jayden-cwj/strategic-wisdom-archive/issues)
