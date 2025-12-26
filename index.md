---
layout: default
title: "Global Arsenal Archive - Dashboard"
---

<div class="dashboard container">
    <div class="dashboard-header">
        <h1 class="lang-en-only">Global Arsenal Archive</h1>
        <h1 class="lang-ko-only">글로벌 무기 아카이브</h1>
        <p class="subtitle lang-en-only">A data-driven platform archiving global military history and weapon specifications</p>
        <p class="subtitle lang-ko-only">전 세계 군사 역사와 무기 사양을 아카이브하는 데이터 기반 플랫폼</p>
    </div>

    <!-- Weapons Section -->
    <section class="collection-section">
        <h2 class="lang-en-only">Weapons Arsenal</h2>
        <h2 class="lang-ko-only">무기 목록</h2>
        <div class="grid-container">
            {% for weapon in site.weapons %}
            <a href="{{ weapon.url | relative_url }}" class="item-card">
                <div class="card-image">
                    <img src="{{ weapon.thumbnail | relative_url }}" alt="{{ weapon.title_en }}">
                </div>
                <div class="card-content">
                    <h3 class="card-title-en lang-en-only">{{ weapon.title_en }}</h3>
                    <p class="card-title-ko lang-ko-only">{{ weapon.title_ko }}</p>
                    <p class="card-summary lang-en-only">{{ weapon.summary_en }}</p>
                    <p class="card-summary lang-ko-only">{{ weapon.summary_ko }}</p>
                </div>
            </a>
            {% endfor %}
        </div>
    </section>

    <!-- Wars Section -->
    <section class="collection-section">
        <h2 class="lang-en-only">Historical Conflicts</h2>
        <h2 class="lang-ko-only">역사적 전쟁</h2>
        <div class="grid-container">
            {% for war in site.wars %}
            <a href="{{ war.url | relative_url }}" class="item-card">
                <div class="card-image">
                    <img src="{{ war.thumbnail | relative_url }}" alt="{{ war.title_en }}">
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
