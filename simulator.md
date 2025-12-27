---
layout: default
title_en: "Strategic Logic Simulator"
title_ko: "전략 논리 시뮬레이터"
permalink: /simulator/
---

<div class="simulator-container">

    <div class="simulator-body">
        <div class="simulator-controls">
            <h2 class="lang-en-only">Defense System Variables</h2>
            <h2 class="lang-ko-only">방어 시스템 변수</h2>

            <div class="control-group">
                <label for="deterrence" class="lang-en-only">
                    Deterrence Level (Psychological Impact)
                    <span class="help-text">How intimidating is the defense to potential attackers?</span>
                </label>
                <label for="deterrence" class="lang-ko-only">
                    억지력 (심리적 영향)
                    <span class="help-text">방어 시설이 잠재적 공격자에게 얼마나 위협적입니까?</span>
                </label>
                <input type="range" id="deterrence" min="0" max="100" value="50" step="5">
                <span class="value-display" id="deterrence-value">50</span>
            </div>

            <div class="control-group">
                <label for="communication" class="lang-en-only">
                    Communication Efficiency (Signal Network)
                    <span class="help-text">How quickly can warnings spread across the defense network?</span>
                </label>
                <label for="communication" class="lang-ko-only">
                    통신 효율성 (신호 네트워크)
                    <span class="help-text">방어 네트워크 전체에 경고가 얼마나 빨리 전파될 수 있습니까?</span>
                </label>
                <input type="range" id="communication" min="0" max="100" value="50" step="5">
                <span class="value-display" id="communication-value">50</span>
            </div>

            <div class="control-group">
                <label for="durability" class="lang-en-only">
                    Defensive Durability (Physical Strength)
                    <span class="help-text">How resistant is the structure to physical assault?</span>
                </label>
                <label for="durability" class="lang-ko-only">
                    방어 내구성 (물리적 강도)
                    <span class="help-text">구조물이 물리적 공격에 얼마나 저항력이 있습니까?</span>
                </label>
                <input type="range" id="durability" min="0" max="100" value="50" step="5">
                <span class="value-display" id="durability-value">50</span>
            </div>

            <div class="control-group">
                <label for="terrain" class="lang-en-only">
                    Terrain Advantage (Geographic Position)
                    <span class="help-text">How well does the defense use natural geography?</span>
                </label>
                <label for="terrain" class="lang-ko-only">
                    지형 이점 (지리적 위치)
                    <span class="help-text">방어가 자연 지형을 얼마나 잘 활용합니까?</span>
                </label>
                <input type="range" id="terrain" min="0" max="100" value="50" step="5">
                <span class="value-display" id="terrain-value">50</span>
            </div>

            <div class="control-group">
                <label for="resources" class="lang-en-only">
                    Resource Availability (Supply Security)
                    <span class="help-text">How sustainable is the defense during prolonged siege?</span>
                </label>
                <label for="resources" class="lang-ko-only">
                    자원 가용성 (보급 안정성)
                    <span class="help-text">장기 포위 공격 중 방어가 얼마나 지속 가능합니까?</span>
                </label>
                <input type="range" id="resources" min="0" max="100" value="50" step="5">
                <span class="value-display" id="resources-value">50</span>
            </div>

            <div class="control-group">
                <label for="utility" class="lang-en-only">
                    Strategic Utility (Value & Effectiveness)
                    <span class="help-text">How effectively does this system achieve its defensive goals?</span>
                </label>
                <label for="utility" class="lang-ko-only">
                    전략적 효용성 (가치 및 효과)
                    <span class="help-text">이 시스템이 방어 목표를 얼마나 효과적으로 달성합니까?</span>
                </label>
                <input type="range" id="utility" min="0" max="100" value="50" step="5">
                <span class="value-display" id="utility-value">50</span>
            </div>

            <div class="preset-buttons">
                <h3 class="lang-en-only">Historical Presets:</h3>
                <h3 class="lang-ko-only">역사적 사전 설정:</h3>
                <button onclick="loadPreset('great-wall')" class="preset-btn">Great Wall / 만리장성</button>
                <button onclick="loadPreset('hwaseong')" class="preset-btn">Hwaseong / 화성</button>
                <button onclick="loadPreset('balanced')" class="preset-btn">Balanced System / 균형 시스템</button>
            </div>
        </div>

        <div class="simulator-results">
            <div class="result-display">
                <h2 class="lang-en-only">Survival Probability</h2>
                <h2 class="lang-ko-only">생존 확률</h2>
                <div class="survival-score" id="survival-score">50%</div>
                <div class="score-bar">
                    <div class="score-fill" id="score-fill" style="width: 50%"></div>
                </div>
                <p class="score-label" id="score-label-en" class="lang-en-only">Moderate Defense</p>
                <p class="score-label" id="score-label-ko" class="lang-ko-only">보통 방어</p>
            </div>

            <div class="insights-panel">
                <h3 class="lang-en-only">Strategic Analysis</h3>
                <h3 class="lang-ko-only">전략적 분석</h3>
                <div id="analysis-output" class="analysis-text">
                    <p class="lang-en-only">Adjust the variables above to see how different factors impact defensive effectiveness.</p>
                    <p class="lang-ko-only">위의 변수를 조정하여 다양한 요소가 방어 효율성에 미치는 영향을 확인하세요.</p>
                </div>
            </div>

            <div class="weakness-analysis">
                <h3 class="lang-en-only">Critical Weaknesses</h3>
                <h3 class="lang-ko-only">주요 약점</h3>
                <ul id="weaknesses-list" class="weaknesses">
                    <li class="lang-en-only">Adjust metrics to identify vulnerabilities</li>
                    <li class="lang-ko-only">취약점을 식별하려면 지표를 조정하세요</li>
                </ul>
            </div>

            <div class="strength-analysis">
                <h3 class="lang-en-only">Key Strengths</h3>
                <h3 class="lang-ko-only">주요 강점</h3>
                <ul id="strengths-list" class="strengths">
                    <li class="lang-en-only">Adjust metrics to identify advantages</li>
                    <li class="lang-ko-only">장점을 식별하려면 지표를 조정하세요</li>
                </ul>
            </div>
        </div>
    </div>
</div>

<script>
    // Simulator Logic
    const metrics = {
        deterrence: 50,
        communication: 50,
        durability: 50,
        terrain: 50,
        resources: 50,
        utility: 50
    };

    // Historical Presets
    const presets = {
        'great-wall': {
            deterrence: 95,
            communication: 85,
            durability: 80,
            terrain: 90,
            resources: 70,
            utility: 88
        },
        'hwaseong': {
            deterrence: 88,
            communication: 90,
            durability: 85,
            terrain: 75,
            resources: 80,
            utility: 92
        },
        'balanced': {
            deterrence: 70,
            communication: 70,
            durability: 70,
            terrain: 70,
            resources: 70,
            utility: 70
        }
    };

    // Weight factors for different metrics
    const weights = {
        deterrence: 0.12,      // 12% - psychological warfare
        communication: 0.25,   // 25% - critical (early warning)
        durability: 0.20,      // 20% - physical defense
        terrain: 0.15,         // 15% - force multiplier
        resources: 0.08,       // 8% - sustainability
        utility: 0.20          // 20% - overall strategic value
    };

    function updateSimulator() {
        // Calculate weighted survival score
        const survivalScore = Math.round(
            metrics.deterrence * weights.deterrence +
            metrics.communication * weights.communication +
            metrics.durability * weights.durability +
            metrics.terrain * weights.terrain +
            metrics.resources * weights.resources
        );

        // Update display
        document.getElementById('survival-score').textContent = survivalScore + '%';
        document.getElementById('score-fill').style.width = survivalScore + '%';

        // Update score fill color based on value
        const scoreFill = document.getElementById('score-fill');
        if (survivalScore >= 80) {
            scoreFill.style.background = 'linear-gradient(90deg, #2ecc71, #27ae60)';
        } else if (survivalScore >= 60) {
            scoreFill.style.background = 'linear-gradient(90deg, #3498db, #2980b9)';
        } else if (survivalScore >= 40) {
            scoreFill.style.background = 'linear-gradient(90deg, #f39c12, #e67e22)';
        } else {
            scoreFill.style.background = 'linear-gradient(90deg, #e74c3c, #c0392b)';
        }

        // Update label
        const labels = {
            en: survivalScore >= 80 ? 'Exceptional Defense' :
                survivalScore >= 60 ? 'Strong Defense' :
                survivalScore >= 40 ? 'Moderate Defense' : 'Vulnerable Defense',
            ko: survivalScore >= 80 ? '탁월한 방어' :
                survivalScore >= 60 ? '강력한 방어' :
                survivalScore >= 40 ? '보통 방어' : '취약한 방어'
        };
        document.getElementById('score-label-en').textContent = labels.en;
        document.getElementById('score-label-ko').textContent = labels.ko;

        // Generate analysis
        generateAnalysis(survivalScore);

        // Identify weaknesses and strengths
        identifyWeaknesses();
        identifyStrengths();
    }

    function generateAnalysis(score) {
        const analysisEn = document.createElement('div');
        const analysisKo = document.createElement('div');

        analysisEn.className = 'lang-en-only';
        analysisKo.className = 'lang-ko-only';

        // English analysis
        let textEn = '';
        if (score >= 80) {
            textEn = 'This defense system demonstrates exceptional strategic design. The combination of high deterrence, efficient communication, and strong physical defenses creates a multi-layered security architecture that would be extremely difficult to overcome.';
        } else if (score >= 60) {
            textEn = 'This represents a solid defensive position with notable strengths. However, there may be opportunities to optimize communication networks or leverage terrain advantages more effectively to enhance overall security.';
        } else if (score >= 40) {
            textEn = 'This defense system has moderate effectiveness but significant vulnerabilities. Consider prioritizing improvements to communication efficiency (30% weight) and physical durability (25% weight) for maximum impact.';
        } else {
            textEn = 'Critical vulnerabilities detected. This defense system requires substantial improvements across multiple dimensions. Focus immediately on communication networks and physical fortifications as these provide the greatest security returns.';
        }

        // Korean analysis
        let textKo = '';
        if (score >= 80) {
            textKo = '이 방어 시스템은 탁월한 전략적 설계를 보여줍니다. 높은 억지력, 효율적인 통신, 강력한 물리적 방어의 조합은 극복하기 매우 어려운 다층 보안 아키텍처를 만듭니다.';
        } else if (score >= 60) {
            textKo = '이것은 주목할 만한 강점을 가진 견고한 방어 위치를 나타냅니다. 그러나 통신 네트워크를 최적화하거나 지형 이점을 더 효과적으로 활용하여 전반적인 보안을 강화할 기회가 있을 수 있습니다.';
        } else if (score >= 40) {
            textKo = '이 방어 시스템은 보통 수준의 효율성을 가지고 있지만 상당한 취약점이 있습니다. 최대 효과를 위해 통신 효율성(30% 가중치)과 물리적 내구성(25% 가중치) 개선을 우선적으로 고려하세요.';
        } else {
            textKo = '심각한 취약점이 감지되었습니다. 이 방어 시스템은 여러 차원에서 상당한 개선이 필요합니다. 가장 큰 보안 효과를 제공하는 통신 네트워크와 물리적 요새화에 즉시 집중하세요.';
        }

        analysisEn.innerHTML = `<p>${textEn}</p>`;
        analysisKo.innerHTML = `<p>${textKo}</p>`;

        const output = document.getElementById('analysis-output');
        output.innerHTML = '';
        output.appendChild(analysisEn);
        output.appendChild(analysisKo);
    }

    function identifyWeaknesses() {
        const weaknesses = [];
        const threshold = 50;

        const metricsData = [
            { key: 'communication', nameEn: 'Communication Efficiency', nameKo: '통신 효율성', weight: weights.communication },
            { key: 'durability', nameEn: 'Defensive Durability', nameKo: '방어 내구성', weight: weights.durability },
            { key: 'terrain', nameEn: 'Terrain Advantage', nameKo: '지형 이점', weight: weights.terrain },
            { key: 'deterrence', nameEn: 'Deterrence Level', nameKo: '억지력', weight: weights.deterrence },
            { key: 'resources', nameEn: 'Resource Availability', nameKo: '자원 가용성', weight: weights.resources }
        ];

        // Sort by weight (most important first)
        metricsData.sort((a, b) => b.weight - a.weight);

        metricsData.forEach(metric => {
            if (metrics[metric.key] < threshold) {
                weaknesses.push({
                    nameEn: metric.nameEn,
                    nameKo: metric.nameKo,
                    value: metrics[metric.key],
                    weight: metric.weight
                });
            }
        });

        const listEn = document.createElement('div');
        const listKo = document.createElement('div');
        listEn.className = 'lang-en-only';
        listKo.className = 'lang-ko-only';

        if (weaknesses.length === 0) {
            listEn.innerHTML = '<li>No critical weaknesses detected - all metrics above threshold</li>';
            listKo.innerHTML = '<li>심각한 약점이 감지되지 않음 - 모든 지표가 임계값 이상</li>';
        } else {
            listEn.innerHTML = weaknesses.map(w =>
                `<li>${w.nameEn}: ${w.value}/100 (Weight: ${(w.weight * 100).toFixed(0)}%)</li>`
            ).join('');
            listKo.innerHTML = weaknesses.map(w =>
                `<li>${w.nameKo}: ${w.value}/100 (가중치: ${(w.weight * 100).toFixed(0)}%)</li>`
            ).join('');
        }

        const list = document.getElementById('weaknesses-list');
        list.innerHTML = '';
        list.appendChild(listEn);
        list.appendChild(listKo);
    }

    function identifyStrengths() {
        const strengths = [];
        const threshold = 75;

        const metricsData = [
            { key: 'communication', nameEn: 'Communication Efficiency', nameKo: '통신 효율성' },
            { key: 'durability', nameEn: 'Defensive Durability', nameKo: '방어 내구성' },
            { key: 'terrain', nameEn: 'Terrain Advantage', nameKo: '지형 이점' },
            { key: 'deterrence', nameEn: 'Deterrence Level', nameKo: '억지력' },
            { key: 'resources', nameEn: 'Resource Availability', nameKo: '자원 가용성' }
        ];

        metricsData.forEach(metric => {
            if (metrics[metric.key] >= threshold) {
                strengths.push({
                    nameEn: metric.nameEn,
                    nameKo: metric.nameKo,
                    value: metrics[metric.key]
                });
            }
        });

        const listEn = document.createElement('div');
        const listKo = document.createElement('div');
        listEn.className = 'lang-en-only';
        listKo.className = 'lang-ko-only';

        if (strengths.length === 0) {
            listEn.innerHTML = '<li>No exceptional strengths - consider enhancing key metrics</li>';
            listKo.innerHTML = '<li>탁월한 강점 없음 - 주요 지표 강화 고려</li>';
        } else {
            listEn.innerHTML = strengths.map(s =>
                `<li>${s.nameEn}: ${s.value}/100 - Force multiplier effect</li>`
            ).join('');
            listKo.innerHTML = strengths.map(s =>
                `<li>${s.nameKo}: ${s.value}/100 - 힘의 배가 효과</li>`
            ).join('');
        }

        const list = document.getElementById('strengths-list');
        list.innerHTML = '';
        list.appendChild(listEn);
        list.appendChild(listKo);
    }

    function loadPreset(presetName) {
        const preset = presets[presetName];
        Object.keys(preset).forEach(key => {
            metrics[key] = preset[key];
            document.getElementById(key).value = preset[key];
            document.getElementById(key + '-value').textContent = preset[key];
        });
        updateSimulator();
    }

    // Initialize sliders
    ['deterrence', 'communication', 'durability', 'terrain', 'resources', 'utility'].forEach(id => {
        const slider = document.getElementById(id);
        const valueDisplay = document.getElementById(id + '-value');

        slider.addEventListener('input', function() {
            metrics[id] = parseInt(this.value);
            valueDisplay.textContent = this.value;
            updateSimulator();
        });
    });

    // Initial calculation
    updateSimulator();
</script>

<style>
.simulator-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

.simulator-header {
    text-align: center;
    margin-bottom: 3rem;
}

.simulator-header h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: #2c3e50;
}

.simulator-header p {
    font-size: 1.1rem;
    color: #7f8c8d;
}

.simulator-body {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
}

.simulator-controls h2, .simulator-results h2 {
    font-size: 1.8rem;
    margin-bottom: 1.5rem;
    color: #34495e;
}

.control-group {
    margin-bottom: 2rem;
}

.control-group label {
    display: block;
    font-weight: 600;
    margin-bottom: 0.5rem;
    color: #2c3e50;
}

.help-text {
    display: block;
    font-size: 0.85rem;
    font-weight: normal;
    color: #95a5a6;
    margin-top: 0.25rem;
}

.control-group input[type="range"] {
    width: 100%;
    height: 8px;
    background: #ecf0f1;
    border-radius: 5px;
    outline: none;
    -webkit-appearance: none;
}

.control-group input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 20px;
    height: 20px;
    background: #3498db;
    cursor: pointer;
    border-radius: 50%;
}

.control-group input[type="range"]::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background: #3498db;
    cursor: pointer;
    border-radius: 50%;
    border: none;
}

.value-display {
    display: inline-block;
    margin-left: 1rem;
    font-weight: 700;
    color: #3498db;
    font-size: 1.1rem;
}

.preset-buttons {
    margin-top: 2rem;
    padding-top: 2rem;
    border-top: 2px solid #ecf0f1;
}

.preset-buttons h3 {
    margin-bottom: 1rem;
    color: #34495e;
}

.preset-btn {
    display: block;
    width: 100%;
    padding: 0.75rem;
    margin-bottom: 0.75rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-size: 1rem;
    font-weight: 600;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.preset-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
}

.result-display {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 2rem;
    border-radius: 12px;
    text-align: center;
    color: white;
    margin-bottom: 2rem;
}

.result-display h2 {
    color: white;
    margin-bottom: 1rem;
}

.survival-score {
    font-size: 4rem;
    font-weight: 800;
    margin: 1rem 0;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.score-bar {
    width: 100%;
    height: 30px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 15px;
    overflow: hidden;
    margin: 1.5rem 0;
}

.score-fill {
    height: 100%;
    background: linear-gradient(90deg, #2ecc71, #27ae60);
    transition: width 0.5s ease, background 0.5s ease;
    border-radius: 15px;
}

.score-label {
    font-size: 1.3rem;
    font-weight: 600;
    margin-top: 1rem;
}

.insights-panel, .weakness-analysis, .strength-analysis {
    background: #f8f9fa;
    padding: 1.5rem;
    border-radius: 8px;
    margin-bottom: 1.5rem;
}

.insights-panel h3, .weakness-analysis h3, .strength-analysis h3 {
    color: #2c3e50;
    margin-bottom: 1rem;
    font-size: 1.3rem;
}

.analysis-text p {
    line-height: 1.8;
    color: #34495e;
}

.weaknesses, .strengths {
    list-style: none;
    padding-left: 0;
}

.weaknesses li, .strengths li {
    padding: 0.75rem;
    margin-bottom: 0.5rem;
    background: white;
    border-radius: 6px;
    border-left: 4px solid #e74c3c;
}

.strengths li {
    border-left-color: #2ecc71;
}

@media (max-width: 768px) {
    .simulator-body {
        grid-template-columns: 1fr;
    }

    .survival-score {
        font-size: 3rem;
    }
}
</style>
