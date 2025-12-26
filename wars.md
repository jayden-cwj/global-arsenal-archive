---
layout: default
title: "Historical Conflicts"
permalink: /wars/
---

<div class="dashboard container">
    <div class="dashboard-header">
        <h1 class="lang-en-only">Historical Conflicts</h1>
        <h1 class="lang-ko-only">역사적 전쟁</h1>
        <p class="subtitle lang-en-only">Comprehensive archive of major military conflicts throughout history</p>
        <p class="subtitle lang-ko-only">역사상 주요 군사 분쟁의 종합 아카이브</p>
    </div>

    <section class="collection-section">
        <h2 class="lang-en-only">All Wars</h2>
        <h2 class="lang-ko-only">모든 전쟁</h2>
        <div class="grid-container">
            {% for war in site.wars %}
            <a href="{{ war.url | relative_url }}" class="item-card">
                <div class="card-image">
                    {% if war.thumbnail %}
                    <img src="{{ war.thumbnail | relative_url }}" alt="{{ war.title_en }}">
                    {% else %}
                    <svg width="400" height="300" xmlns="http://www.w3.org/2000/svg">
                        <rect width="400" height="300" fill="#1a252f"/>
                        <text x="200" y="150" font-family="Arial" font-size="24" fill="#ecf0f1" text-anchor="middle" font-weight="bold">{{ war.title_en }}</text>
                    </svg>
                    {% endif %}
                </div>
                <div class="card-content">
                    <h3 class="card-title-en lang-en-only">{{ war.title_en }}</h3>
                    <p class="card-title-ko lang-ko-only">{{ war.title_ko }}</p>
                    <p class="card-summary lang-en-only">{{ war.summary_en }}</p>
                    <p class="card-summary lang-ko-only">{{ war.summary_ko }}</p>
                </div>
            </a>
            {% endfor %}
        </div>
    </section>
</div>
