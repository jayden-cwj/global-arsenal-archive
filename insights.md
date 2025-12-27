---
layout: default
title_en: "Wisdom Chronicles"
title_ko: "지혜 연대기"
permalink: /insights/
---

<div class="insights-page">
    <div class="page-header">
        <h1 class="lang-en-only">Wisdom Chronicles</h1>
        <h1 class="lang-ko-only">지혜 연대기</h1>
        <p class="page-description lang-en-only">
            Monthly bilingual insights connecting historical defensive strategies to modern challenges.
            Each post analyzes a specific system and extracts timeless principles for leadership, innovation, and peace.
        </p>
        <p class="page-description lang-ko-only">
            역사적 방어 전략을 현대적 도전과 연결하는 월간 이중 언어 통찰력.
            각 게시물은 특정 시스템을 분석하고 리더십, 혁신, 평화를 위한 시대를 초월한 원칙을 추출합니다.
        </p>
    </div>

    <div class="insights-grid">
        {% assign sorted_insights = site.insights | sort: 'date' | reverse %}
        {% for insight in sorted_insights %}
        <article class="insight-card">
            {% if insight.featured_image %}
            <div class="card-image">
                <img src="{{ insight.featured_image | relative_url }}" alt="{{ insight.title_en }}">
            </div>
            {% endif %}

            <div class="card-content">
                <div class="card-meta">
                    <time datetime="{{ insight.date | date_to_xmlschema }}">
                        {{ insight.date | date: "%B %d, %Y" }}
                    </time>
                    {% if insight.category %}
                    <span class="category-badge">{{ insight.category }}</span>
                    {% endif %}
                </div>

                <h2 class="card-title">
                    <a href="{{ insight.url | relative_url }}">
                        <span class="lang-en-only">{{ insight.title_en }}</span>
                        <span class="lang-ko-only">{{ insight.title_ko }}</span>
                    </a>
                </h2>

                {% if insight.subtitle_en %}
                <p class="card-subtitle lang-en-only">{{ insight.subtitle_en }}</p>
                <p class="card-subtitle lang-ko-only">{{ insight.subtitle_ko }}</p>
                {% endif %}

                <p class="card-summary lang-en-only">{{ insight.summary_en }}</p>
                <p class="card-summary lang-ko-only">{{ insight.summary_ko }}</p>

                {% if insight.tags %}
                <div class="card-tags">
                    {% for tag in insight.tags limit:3 %}
                    <span class="tag">{{ tag }}</span>
                    {% endfor %}
                </div>
                {% endif %}

                <a href="{{ insight.url | relative_url }}" class="read-more">
                    <span class="lang-en-only">Read More →</span>
                    <span class="lang-ko-only">더 읽기 →</span>
                </a>
            </div>
        </article>
        {% endfor %}

        {% if site.insights.size == 0 %}
        <div class="empty-state">
            <p class="lang-en-only">No insights published yet. Check back soon for the first post!</p>
            <p class="lang-ko-only">아직 게시된 인사이트가 없습니다. 첫 번째 게시물을 곧 확인하세요!</p>
        </div>
        {% endif %}
    </div>
</div>

<style>
.insights-page {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

.page-header {
    text-align: center;
    margin-bottom: 3rem;
}

.page-header h1 {
    font-size: 2.5rem;
    color: #2c3e50;
    margin-bottom: 1rem;
}

.page-description {
    font-size: 1.1rem;
    color: #7f8c8d;
    max-width: 800px;
    margin: 0 auto;
    line-height: 1.6;
}

.insights-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 2rem;
}

.insight-card {
    background: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.insight-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 8px 24px rgba(52, 152, 219, 0.2);
}

.card-image {
    width: 100%;
    height: 200px;
    overflow: hidden;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-content {
    padding: 1.5rem;
}

.card-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    font-size: 0.9rem;
    color: #95a5a6;
}

.category-badge {
    background: #3498db;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 12px;
    font-size: 0.85rem;
    font-weight: 600;
}

.card-title {
    margin-bottom: 0.5rem;
}

.card-title a {
    color: #2c3e50;
    text-decoration: none;
    font-size: 1.5rem;
    font-weight: 700;
}

.card-title a:hover {
    color: #3498db;
}

.card-subtitle {
    font-size: 1rem;
    color: #7f8c8d;
    font-style: italic;
    margin-bottom: 0.75rem;
}

.card-summary {
    color: #34495e;
    line-height: 1.6;
    margin-bottom: 1rem;
}

.card-tags {
    margin-bottom: 1rem;
}

.card-tags .tag {
    display: inline-block;
    background: #ecf0f1;
    color: #34495e;
    padding: 0.25rem 0.5rem;
    border-radius: 4px;
    font-size: 0.85rem;
    margin-right: 0.5rem;
    margin-bottom: 0.5rem;
}

.read-more {
    color: #3498db;
    text-decoration: none;
    font-weight: 600;
    display: inline-block;
    transition: transform 0.2s ease;
}

.read-more:hover {
    transform: translateX(5px);
}

.empty-state {
    grid-column: 1 / -1;
    text-align: center;
    padding: 4rem 2rem;
    color: #95a5a6;
    font-size: 1.1rem;
}

@media (max-width: 768px) {
    .insights-grid {
        grid-template-columns: 1fr;
    }

    .page-header h1 {
        font-size: 2rem;
    }
}
</style>
