---
layout: default
title_en: "Global Defense Map"
title_ko: "글로벌 방어 지도"
permalink: /map/
---

<div class="map-container">

    <div class="map-controls">
        <div class="filter-group">
            <label class="lang-en-only">Filter by Type:</label>
            <label class="lang-ko-only">유형별 필터:</label>
            <button class="filter-btn active" data-filter="all">
                <span class="lang-en-only">All</span>
                <span class="lang-ko-only">전체</span>
            </button>
            <button class="filter-btn" data-filter="fortification">
                <span class="lang-en-only">Fortifications</span>
                <span class="lang-ko-only">방어 구조</span>
            </button>
            <button class="filter-btn" data-filter="strategy">
                <span class="lang-en-only">Strategies</span>
                <span class="lang-ko-only">전략</span>
            </button>
        </div>
    </div>

    <div id="defense-map" class="map-display"></div>

    <div class="map-legend">
        <h3 class="lang-en-only">Legend</h3>
        <h3 class="lang-ko-only">범례</h3>
        <div class="legend-items">
            <div class="legend-item">
                <span class="marker-icon fortification-marker">🏰</span>
                <span class="lang-en-only">Fortification</span>
                <span class="lang-ko-only">방어 구조</span>
            </div>
            <div class="legend-item">
                <span class="marker-icon strategy-marker">⚔️</span>
                <span class="lang-en-only">Strategy</span>
                <span class="lang-ko-only">전략</span>
            </div>
        </div>
    </div>
</div>

<!-- Leaflet.js CDN -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
     integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY="
     crossorigin=""/>
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"
     integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo="
     crossorigin=""></script>

<script>
    // Initialize the map
    const map = L.map('defense-map').setView([35.0, 105.0], 3);

    // Add OpenStreetMap tile layer
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
        maxZoom: 18,
    }).addTo(map);

    // Define custom icons
    const fortificationIcon = L.divIcon({
        html: '<div class="custom-marker fortification">🏰</div>',
        className: 'custom-div-icon',
        iconSize: [40, 40],
        iconAnchor: [20, 40],
        popupAnchor: [0, -40]
    });

    const strategyIcon = L.divIcon({
        html: '<div class="custom-marker strategy">⚔️</div>',
        className: 'custom-div-icon',
        iconSize: [40, 40],
        iconAnchor: [20, 40],
        popupAnchor: [0, -40]
    });

    // Store markers for filtering
    let markers = [];

    // Data from Jekyll collections
    const defenseData = [
        {% for fort in site.fortifications %}
        {
            type: 'fortification',
            location: [{{ fort.location[0] }}, {{ fort.location[1] }}],
            title_en: "{{ fort.title_en }}",
            title_ko: "{{ fort.title_ko }}",
            summary_en: "{{ fort.summary_en }}",
            summary_ko: "{{ fort.summary_ko }}",
            url: "{{ fort.url | relative_url }}",
            metrics: {
                deterrence: {{ fort.metrics.deterrence_level | default: 0 }},
                communication: {{ fort.metrics.communication_efficiency | default: 0 }},
                durability: {{ fort.metrics.defensive_durability | default: 0 }}
            },
            key_insight_en: "{{ fort.key_insight_en | strip_newlines | escape }}",
            key_insight_ko: "{{ fort.key_insight_ko | strip_newlines | escape }}"
        }{% unless forloop.last %},{% endunless %}
        {% endfor %}
        {% if site.fortifications.size > 0 and site.strategies.size > 0 %},{% endif %}
        {% for strat in site.strategies %}
        {
            type: 'strategy',
            location: [{{ strat.location[0] }}, {{ strat.location[1] }}],
            title_en: "{{ strat.title_en }}",
            title_ko: "{{ strat.title_ko }}",
            summary_en: "{{ strat.summary_en }}",
            summary_ko: "{{ strat.summary_ko }}",
            url: "{{ strat.url | relative_url }}",
            metrics: {
                deterrence: {{ strat.metrics.deterrence_level | default: 0 }},
                communication: {{ strat.metrics.communication_efficiency | default: 0 }},
                innovation: {{ strat.metrics.innovation_index | default: 0 }}
            },
            key_insight_en: "{{ strat.key_insight_en | strip_newlines | escape }}",
            key_insight_ko: "{{ strat.key_insight_ko | strip_newlines | escape }}"
        }{% unless forloop.last %},{% endunless %}
        {% endfor %}
    ];

    // Get current language
    function getCurrentLanguage() {
        return document.body.getAttribute('data-lang') || 'en';
    }

    // Create popup content
    function createPopupContent(item) {
        const lang = getCurrentLanguage();
        const title = lang === 'ko' ? item.title_ko : item.title_en;
        const summary = lang === 'ko' ? item.summary_ko : item.summary_en;
        const keyInsight = lang === 'ko' ? item.key_insight_ko : item.key_insight_en;

        const typeLabel = lang === 'ko'
            ? (item.type === 'fortification' ? '방어 구조' : '전략')
            : (item.type === 'fortification' ? 'Fortification' : 'Strategy');

        const readMoreLabel = lang === 'ko' ? '자세히 보기' : 'Learn More';
        const metricsLabel = lang === 'ko' ? '전략 지표' : 'Strategic Metrics';

        let metricsHTML = `<div class="popup-metrics"><strong>${metricsLabel}:</strong><ul>`;
        if (item.metrics.deterrence) {
            const label = lang === 'ko' ? '억지력' : 'Deterrence';
            metricsHTML += `<li>${label}: ${item.metrics.deterrence}/100</li>`;
        }
        if (item.metrics.communication) {
            const label = lang === 'ko' ? '통신 효율성' : 'Communication';
            metricsHTML += `<li>${label}: ${item.metrics.communication}/100</li>`;
        }
        if (item.metrics.durability) {
            const label = lang === 'ko' ? '내구성' : 'Durability';
            metricsHTML += `<li>${label}: ${item.metrics.durability}/100</li>`;
        }
        if (item.metrics.innovation) {
            const label = lang === 'ko' ? '혁신' : 'Innovation';
            metricsHTML += `<li>${label}: ${item.metrics.innovation}/100</li>`;
        }
        metricsHTML += '</ul></div>';

        return `
            <div class="map-popup">
                <span class="popup-type">${typeLabel}</span>
                <h3 class="popup-title">${title}</h3>
                <p class="popup-summary">${summary}</p>
                ${metricsHTML}
                ${keyInsight ? `<p class="popup-insight"><em>${keyInsight}</em></p>` : ''}
                <a href="${item.url}" class="popup-link">${readMoreLabel} →</a>
            </div>
        `;
    }

    // Add markers to map
    function addMarkers(filter = 'all') {
        // Clear existing markers
        markers.forEach(marker => map.removeLayer(marker));
        markers = [];

        // Add filtered markers
        defenseData.forEach(item => {
            if (filter === 'all' || filter === item.type) {
                const icon = item.type === 'fortification' ? fortificationIcon : strategyIcon;
                const marker = L.marker(item.location, { icon: icon })
                    .bindPopup(createPopupContent(item), {
                        maxWidth: 350,
                        className: 'defense-popup'
                    })
                    .addTo(map);

                markers.push(marker);
            }
        });
    }

    // Initial marker placement
    addMarkers();

    // Filter buttons
    document.querySelectorAll('.filter-btn').forEach(btn => {
        btn.addEventListener('click', function() {
            // Update active state
            document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
            this.classList.add('active');

            // Apply filter
            const filter = this.getAttribute('data-filter');
            addMarkers(filter);
        });
    });

    // Update popups when language changes
    const observer = new MutationObserver(function(mutations) {
        mutations.forEach(function(mutation) {
            if (mutation.type === 'attributes' && mutation.attributeName === 'data-lang') {
                // Re-render all markers to update popup content
                const currentFilter = document.querySelector('.filter-btn.active').getAttribute('data-filter');
                addMarkers(currentFilter);
            }
        });
    });

    observer.observe(document.body, {
        attributes: true,
        attributeFilter: ['data-lang']
    });
</script>

<style>
.map-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
}

.map-header {
    text-align: center;
    margin-bottom: 2rem;
}

.map-header h1 {
    font-size: 2.5rem;
    color: #2c3e50;
    margin-bottom: 1rem;
}

.map-header p {
    font-size: 1.1rem;
    color: #7f8c8d;
    max-width: 800px;
    margin: 0 auto;
}

.map-controls {
    margin-bottom: 1.5rem;
    text-align: center;
}

.filter-group {
    display: inline-flex;
    align-items: center;
    gap: 1rem;
    background: white;
    padding: 1rem 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.filter-group label {
    font-weight: 600;
    color: #2c3e50;
}

.filter-btn {
    padding: 0.5rem 1rem;
    background: #ecf0f1;
    border: 2px solid transparent;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
    color: #34495e;
    transition: all 0.3s ease;
}

.filter-btn:hover {
    background: #d5d8dc;
}

.filter-btn.active {
    background: #3498db;
    color: white;
    border-color: #2980b9;
}

#defense-map {
    height: 600px;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
    margin-bottom: 2rem;
}

.map-legend {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.map-legend h3 {
    margin-bottom: 1rem;
    color: #2c3e50;
}

.legend-items {
    display: flex;
    gap: 2rem;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.marker-icon {
    font-size: 1.5rem;
}

/* Custom marker styles */
.custom-div-icon {
    background: none;
    border: none;
}

.custom-marker {
    font-size: 2rem;
    text-align: center;
    filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.3));
    cursor: pointer;
    transition: transform 0.2s ease;
}

.custom-marker:hover {
    transform: scale(1.2);
}

/* Popup styles */
.defense-popup .leaflet-popup-content-wrapper {
    border-radius: 8px;
    padding: 0;
}

.map-popup {
    padding: 1rem;
}

.popup-type {
    display: inline-block;
    background: #3498db;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 12px;
    font-size: 0.85rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
}

.popup-title {
    color: #2c3e50;
    margin: 0.5rem 0;
    font-size: 1.3rem;
}

.popup-summary {
    color: #34495e;
    line-height: 1.5;
    margin-bottom: 1rem;
}

.popup-metrics {
    background: #f8f9fa;
    padding: 0.75rem;
    border-radius: 6px;
    margin-bottom: 1rem;
}

.popup-metrics strong {
    color: #2c3e50;
}

.popup-metrics ul {
    list-style: none;
    padding-left: 0;
    margin: 0.5rem 0 0 0;
}

.popup-metrics li {
    padding: 0.25rem 0;
    color: #34495e;
}

.popup-insight {
    color: #7f8c8d;
    font-size: 0.95rem;
    line-height: 1.6;
    margin-bottom: 1rem;
    padding-left: 1rem;
    border-left: 3px solid #3498db;
}

.popup-link {
    display: inline-block;
    color: #3498db;
    text-decoration: none;
    font-weight: 600;
    transition: transform 0.2s ease;
}

.popup-link:hover {
    transform: translateX(5px);
}

@media (max-width: 768px) {
    .map-header h1 {
        font-size: 2rem;
    }

    #defense-map {
        height: 400px;
    }

    .filter-group {
        flex-direction: column;
        gap: 0.5rem;
    }

    .legend-items {
        flex-direction: column;
        gap: 0.5rem;
    }
}
</style>
