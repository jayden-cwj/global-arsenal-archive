---
layout: default
title_en: "Strategic Wisdom Archive - Home"
title_ko: "전략적 지혜 아카이브 - 홈"
---

<div class="home-hero">
    <div class="hero-content">
        <h1 class="hero-title lang-en-only">Strategic Wisdom Archive</h1>
        <h1 class="hero-title lang-ko-only">전략적 지혜 아카이브</h1>
        <p class="hero-subtitle lang-en-only">
            Exploring the Logic of Defense, Protection, and Strategic Thinking Throughout History
        </p>
        <p class="hero-subtitle lang-ko-only">
            역사를 통한 방어, 보호, 전략적 사고의 논리 탐구
        </p>
        <div class="hero-stats">
            <div class="stat">
                <span class="stat-number">{{ site.fortifications.size }}</span>
                <span class="stat-label lang-en-only">Fortifications</span>
                <span class="stat-label lang-ko-only">방어 구조</span>
            </div>
            <div class="stat">
                <span class="stat-number">{{ site.strategies.size }}</span>
                <span class="stat-label lang-en-only">Strategies</span>
                <span class="stat-label lang-ko-only">전략</span>
            </div>
            <div class="stat">
                <span class="stat-number">{{ site.insights.size }}</span>
                <span class="stat-label lang-en-only">Insights</span>
                <span class="stat-label lang-ko-only">인사이트</span>
            </div>
        </div>
    </div>
</div>

<div class="dashboard container">
    <!-- Three Core Activities -->
    <section class="activities-section">
        <h2 class="section-title lang-en-only">Three Ways to Explore Strategic Wisdom</h2>
        <h2 class="section-title lang-ko-only">전략적 지혜를 탐구하는 세 가지 방법</h2>

        <div class="activities-grid">
            <!-- Activity 1: Simulator -->
            <a href="{{ '/simulator/' | relative_url }}" class="activity-card simulator-card">
                <div class="activity-icon">🧮</div>
                <h3 class="lang-en-only">Strategic Logic Simulator</h3>
                <h3 class="lang-ko-only">전략 논리 시뮬레이터</h3>
                <p class="lang-en-only">
                    Test defensive strategies by adjusting key metrics. See how deterrence, communication, and terrain affect survival probability.
                </p>
                <p class="lang-ko-only">
                    주요 지표를 조정하여 방어 전략을 테스트하세요. 억지력, 통신, 지형이 생존 확률에 미치는 영향을 확인하세요.
                </p>
                <span class="activity-cta lang-en-only">Launch Simulator →</span>
                <span class="activity-cta lang-ko-only">시뮬레이터 실행 →</span>
            </a>

            <!-- Activity 2: Insights -->
            <a href="{{ '/insights/' | relative_url }}" class="activity-card insights-card">
                <div class="activity-icon">📖</div>
                <h3 class="lang-en-only">Wisdom Chronicles</h3>
                <h3 class="lang-ko-only">지혜 연대기</h3>
                <p class="lang-en-only">
                    Bilingual insights connecting historical defense systems to modern challenges in leadership, innovation, and peace.
                </p>
                <p class="lang-ko-only">
                    역사적 방어 시스템을 리더십, 혁신, 평화의 현대적 도전과 연결하는 이중 언어 통찰력.
                </p>
                <span class="activity-cta lang-en-only">Read Insights →</span>
                <span class="activity-cta lang-ko-only">인사이트 읽기 →</span>
            </a>

            <!-- Activity 3: Map -->
            <a href="{{ '/map/' | relative_url }}" class="activity-card map-card">
                <div class="activity-icon">🗺️</div>
                <h3 class="lang-en-only">Interactive Defense Map</h3>
                <h3 class="lang-ko-only">대화형 방어 지도</h3>
                <p class="lang-en-only">
                    Explore the geographical distribution of humanity's defensive wisdom. See how location shaped strategic thinking.
                </p>
                <p class="lang-ko-only">
                    인류의 방어 지혜의 지리적 분포를 탐색하세요. 위치가 전략적 사고를 어떻게 형성했는지 확인하세요.
                </p>
                <span class="activity-cta lang-en-only">Explore Map →</span>
                <span class="activity-cta lang-ko-only">지도 탐색 →</span>
            </a>
        </div>
    </section>

    <!-- Featured Fortifications -->
    <section class="collection-section">
        <div class="section-header">
            <h2 class="section-title lang-en-only">Featured Fortifications</h2>
            <h2 class="section-title lang-ko-only">주요 방어 구조</h2>
            <a href="{{ '/fortifications/' | relative_url }}" class="view-all lang-en-only">View All →</a>
            <a href="{{ '/fortifications/' | relative_url }}" class="view-all lang-ko-only">전체 보기 →</a>
        </div>
        <div class="grid-container">
            {% for fort in site.fortifications limit:3 %}
            <a href="{{ fort.url | relative_url }}" class="item-card">
                <div class="card-image">
                    {% if fort.thumbnail %}
                    <img src="{{ fort.thumbnail | relative_url }}" alt="{{ fort.title_en }}">
                    {% else %}
                    <div class="placeholder-image fortification-placeholder">
                        <span class="placeholder-icon">🏰</span>
                    </div>
                    {% endif %}
                </div>
                <div class="card-content">
                    <h3 class="card-title lang-en-only">{{ fort.title_en }}</h3>
                    <h3 class="card-title lang-ko-only">{{ fort.title_ko }}</h3>
                    <p class="card-summary lang-en-only">{{ fort.summary_en }}</p>
                    <p class="card-summary lang-ko-only">{{ fort.summary_ko }}</p>
                </div>
            </a>
            {% endfor %}

            {% if site.fortifications.size == 0 %}
            <div class="empty-state">
                <p class="lang-en-only">Fortifications coming soon!</p>
                <p class="lang-ko-only">곧 방어 구조가 추가됩니다!</p>
            </div>
            {% endif %}
        </div>
    </section>

    <!-- Featured Strategies -->
    <section class="collection-section">
        <div class="section-header">
            <h2 class="section-title lang-en-only">Featured Strategies</h2>
            <h2 class="section-title lang-ko-only">주요 전략</h2>
            <a href="{{ '/strategies/' | relative_url }}" class="view-all lang-en-only">View All →</a>
            <a href="{{ '/strategies/' | relative_url }}" class="view-all lang-ko-only">전체 보기 →</a>
        </div>
        <div class="grid-container">
            {% for strat in site.strategies limit:3 %}
            <a href="{{ strat.url | relative_url }}" class="item-card">
                <div class="card-image">
                    {% if strat.thumbnail %}
                    <img src="{{ strat.thumbnail | relative_url }}" alt="{{ strat.title_en }}">
                    {% else %}
                    <div class="placeholder-image strategy-placeholder">
                        <span class="placeholder-icon">⚔️</span>
                    </div>
                    {% endif %}
                </div>
                <div class="card-content">
                    <h3 class="card-title lang-en-only">{{ strat.title_en }}</h3>
                    <h3 class="card-title lang-ko-only">{{ strat.title_ko }}</h3>
                    <p class="card-summary lang-en-only">{{ strat.summary_en }}</p>
                    <p class="card-summary lang-ko-only">{{ strat.summary_ko }}</p>
                </div>
            </a>
            {% endfor %}

            {% if site.strategies.size == 0 %}
            <div class="empty-state">
                <p class="lang-en-only">Strategies coming soon!</p>
                <p class="lang-ko-only">곧 전략이 추가됩니다!</p>
            </div>
            {% endif %}
        </div>
    </section>

    <!-- Latest Insights -->
    <section class="collection-section">
        <div class="section-header">
            <h2 class="section-title lang-en-only">Latest Insights</h2>
            <h2 class="section-title lang-ko-only">최신 인사이트</h2>
            <a href="{{ '/insights/' | relative_url }}" class="view-all lang-en-only">View All →</a>
            <a href="{{ '/insights/' | relative_url }}" class="view-all lang-ko-only">전체 보기 →</a>
        </div>
        {% assign latest_insights = site.insights | sort: 'date' | reverse %}
        <div class="insights-list">
            {% for insight in latest_insights limit:2 %}
            <a href="{{ insight.url | relative_url }}" class="insight-preview">
                <div class="insight-meta">
                    <time>{{ insight.date | date: "%B %d, %Y" }}</time>
                    {% if insight.category %}
                    <span class="category-badge">{{ insight.category }}</span>
                    {% endif %}
                </div>
                <h3 class="lang-en-only">{{ insight.title_en }}</h3>
                <h3 class="lang-ko-only">{{ insight.title_ko }}</h3>
                <p class="lang-en-only">{{ insight.summary_en | truncate: 120 }}</p>
                <p class="lang-ko-only">{{ insight.summary_ko | truncate: 120 }}</p>
            </a>
            {% endfor %}

            {% if site.insights.size == 0 %}
            <div class="empty-state">
                <p class="lang-en-only">First insight coming soon!</p>
                <p class="lang-ko-only">첫 번째 인사이트가 곧 제공됩니다!</p>
            </div>
            {% endif %}
        </div>
    </section>
</div>

<style>
.home-hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 4rem 2rem;
    text-align: center;
    margin-bottom: 3rem;
}

.hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.hero-title {
    font-size: 3rem;
    font-weight: 800;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.hero-subtitle {
    font-size: 1.3rem;
    margin-bottom: 2rem;
    opacity: 0.95;
}

.hero-stats {
    display: flex;
    justify-content: center;
    gap: 3rem;
    margin-top: 2rem;
}

.stat {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.stat-number {
    font-size: 2.5rem;
    font-weight: 700;
}

.stat-label {
    font-size: 0.95rem;
    opacity: 0.9;
}

.activities-section {
    margin-bottom: 4rem;
}

.section-title {
    font-size: 2rem;
    color: #2c3e50;
    margin-bottom: 2rem;
    text-align: center;
}

.activities-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-bottom: 3rem;
}

.activity-card {
    background: white;
    border-radius: 12px;
    padding: 2rem;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    text-decoration: none;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}

.activity-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
}

.activity-icon {
    font-size: 4rem;
    margin-bottom: 1rem;
}

.activity-card h3 {
    font-size: 1.5rem;
    color: #2c3e50;
    margin-bottom: 1rem;
}

.activity-card p {
    color: #7f8c8d;
    line-height: 1.6;
    margin-bottom: 1.5rem;
    flex-grow: 1;
}

.activity-cta {
    color: #3498db;
    font-weight: 600;
    font-size: 1.1rem;
}

.simulator-card:hover .activity-cta {
    color: #667eea;
}

.insights-card:hover .activity-cta {
    color: #e74c3c;
}

.map-card:hover .activity-cta {
    color: #2ecc71;
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
}

.section-header .section-title {
    margin-bottom: 0;
    text-align: left;
}

.view-all {
    color: #3498db;
    text-decoration: none;
    font-weight: 600;
    transition: transform 0.2s ease;
}

.view-all:hover {
    transform: translateX(5px);
}

.insights-list {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.insight-preview {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    text-decoration: none;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.insight-preview:hover {
    transform: translateX(5px);
    box-shadow: 0 4px 12px rgba(52, 152, 219, 0.2);
}

.insight-meta {
    display: flex;
    gap: 1rem;
    margin-bottom: 0.75rem;
    font-size: 0.9rem;
    color: #95a5a6;
}

.category-badge {
    background: #3498db;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 12px;
    font-size: 0.85rem;
}

.insight-preview h3 {
    color: #2c3e50;
    font-size: 1.3rem;
    margin-bottom: 0.5rem;
}

.insight-preview p {
    color: #7f8c8d;
    line-height: 1.5;
}

.placeholder-image {
    width: 100%;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.placeholder-icon {
    font-size: 5rem;
}

.strategy-placeholder {
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
}

@media (max-width: 768px) {
    .hero-title {
        font-size: 2rem;
    }

    .hero-subtitle {
        font-size: 1.1rem;
    }

    .hero-stats {
        flex-direction: column;
        gap: 1.5rem;
    }

    .activities-grid {
        grid-template-columns: 1fr;
    }

    .section-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
    }
}
</style>
