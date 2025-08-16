# Revenue Calculator - Extracted from Investor Pitch Deck

This document contains the complete revenue calculator that was extracted from the investor pitch deck HTML file.

## CSS Styles

```css
/* Enhanced Calculator Styles */
.calculator-section {
    background: linear-gradient(135deg, #55efc4, #00b894);
    color: white;
    border-radius: 25px;
    padding: 50px;
    margin: 40px 0;
    position: relative;
    overflow: hidden;
}

.calculator-section::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
    opacity: 0.3;
}

.calculator-title {
    font-size: 2.8rem;
    font-weight: 800;
    text-align: center;
    margin-bottom: 40px;
    position: relative;
    z-index: 2;
}

.calculator-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    align-items: start;
    position: relative;
    z-index: 2;
}

.calculator-inputs {
    background: rgba(255,255,255,0.15);
    padding: 40px;
    border-radius: 20px;
    border: 2px solid rgba(255,255,255,0.2);
    backdrop-filter: blur(15px);
}

.input-group {
    margin-bottom: 30px;
}

.input-label {
    display: block;
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 15px;
}

.input-field {
    width: 100%;
    padding: 18px;
    font-size: 1.2rem;
    border: none;
    border-radius: 12px;
    background: rgba(255,255,255,0.95);
    color: #333;
    font-weight: 600;
    transition: all 0.3s ease;
}

.input-field:focus {
    outline: none;
    box-shadow: 0 0 20px rgba(255,255,255,0.5);
    transform: scale(1.02);
}

.slider {
    width: 100%;
    height: 8px;
    border-radius: 10px;
    background: rgba(255,255,255,0.3);
    outline: none;
    margin-bottom: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.slider::-webkit-slider-thumb {
    appearance: none;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: #fff;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    transition: all 0.3s ease;
}

.slider::-webkit-slider-thumb:hover {
    transform: scale(1.2);
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
}

.calculator-results {
    background: rgba(255,255,255,0.1);
    padding: 40px;
    border-radius: 20px;
    border: 2px solid rgba(255,255,255,0.2);
    backdrop-filter: blur(15px);
}

.result-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 0;
    border-bottom: 1px solid rgba(255,255,255,0.2);
    margin-bottom: 15px;
}

.result-label {
    font-size: 1.1rem;
    font-weight: 600;
    opacity: 0.9;
}

.result-value {
    font-size: 1.4rem;
    font-weight: 800;
}

.result-highlight {
    background: rgba(255,255,255,0.2);
    padding: 30px;
    border-radius: 15px;
    text-align: center;
    margin: 25px 0;
    border: 2px solid rgba(255,255,255,0.3);
}

.big-number {
    font-size: 3.5rem;
    font-weight: 900;
    margin-bottom: 10px;
}

/* Responsive Design */
@media (max-width: 768px) {
    .calculator-grid {
        grid-template-columns: 1fr;
        gap: 30px;
    }
    
    .calculator-title { font-size: 2rem; }
    
    .slide {
        padding: 40px 30px;
    }
}
```

## HTML Structure

```html
<!-- Slide 3: Revenue Calculator -->
<div class="slide">
    <div class="slide-title" style="text-align: center; margin-bottom: 20px; font-size: 2.5rem; color: #fff;">Revenue Calculator</div>
    <div class="slide-subtitle" style="text-align: center; color: #94a3b8; margin-bottom: 40px;">Interactive model - adjust parameters to see returns</div>
    
    <div class="calculator-section">
        <div class="calculator-title">💰 Revenue & Returns Calculator</div>
        
        <div class="calculator-grid">
            <div class="calculator-inputs">
                <h3 style="margin-bottom: 25px; font-size: 1.4rem; position: relative; z-index: 2;">📊 Input Parameters</h3>
                
                <div class="input-group">
                    <label class="input-label">US Couples Seeking Help (millions)</label>
                    <input type="range" id="aduSlider" class="slider" min="5" max="47" value="15" step="1">
                    <input type="number" id="aduInput" class="input-field" value="15" min="5" max="47">
                </div>
                
                <div class="input-group">
                    <label class="input-label">Average Revenue Per User/Month ($)</label>
                    <input type="range" id="monthlySlider" class="slider" min="12" max="89" value="28" step="2">
                    <input type="number" id="monthlyInput" class="input-field" value="28" min="12" max="89">
                </div>
                
                <div class="input-group">
                    <label class="input-label">Customer Retention Rate (%)</label>
                    <input type="range" id="retentionSlider" class="slider" min="40" max="95" value="78" step="2">
                    <input type="number" id="retentionInput" class="input-field" value="78" min="40" max="95">
                </div>
                
                <div class="input-group">
                    <label class="input-label">Market Capture Rate (%)</label>
                    <input type="range" id="penetrationSlider" class="slider" min="0.5" max="15" value="3.2" step="0.1">
                    <input type="number" id="penetrationInput" class="input-field" value="3.2" min="0.5" max="15" step="0.1">
                </div>
            </div>
            
            <div class="calculator-results">
                <h3 style="margin-bottom: 25px; font-size: 1.4rem;">🎯 Results</h3>
                
                <div class="result-item">
                    <span class="result-label">Target Couples</span>
                    <span class="result-value" id="targetUsers">480K</span>
                </div>
                
                <div class="result-item">
                    <span class="result-label">Monthly Revenue</span>
                    <span class="result-value" id="monthlyRevenue">$13.4M</span>
                </div>
                
                <div class="result-item">
                    <span class="result-label">Annual Revenue</span>
                    <span class="result-value" id="annualRevenue">$161M</span>
                </div>
                
                <div class="result-item">
                    <span class="result-label">Customer LTV</span>
                    <span class="result-value" id="customerLTV">$696</span>
                </div>
                
                <div class="result-highlight">
                    <div class="big-number" id="totalMarketValue">$15.8B</div>
                    <div>Total Addressable Market</div>
                </div>
                
                <div class="result-highlight" style="background: rgba(255,215,0,0.3); margin-top: 20px;">
                    <div class="big-number" id="investorReturn" style="font-size: 2.8rem;">38.7x</div>
                    <div style="font-weight: 600;">Projected ROI Multiple</div>
                    <div id="roi-description" style="font-size: 0.95rem; margin-top: 8px; opacity: 0.8;">
                        Based on $250K seed investment at 6x revenue multiple
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
```

## JavaScript Functions

```javascript
// Revenue Calculator Functions
function synchronizeInputs(sliderId, inputId) {
    const slider = document.getElementById(sliderId);
    const input = document.getElementById(inputId);
    
    if (slider && input) {
        slider.addEventListener('input', () => {
            input.value = slider.value;
            calculateRevenue();
        });
        
        input.addEventListener('input', () => {
            const value = parseFloat(input.value);
            if (!isNaN(value) && value >= parseFloat(input.min) && value <= parseFloat(input.max)) {
                slider.value = value;
                calculateRevenue();
            }
        });
    }
}

function calculateRevenue() {
    const couplesValue = parseFloat(document.getElementById('aduInput').value);
    const arpuValue = parseFloat(document.getElementById('monthlyInput').value);
    const retentionValue = parseFloat(document.getElementById('retentionInput').value);
    const captureValue = parseFloat(document.getElementById('penetrationInput').value);

    // Calculate key metrics
    const targetCouples = (couplesValue * captureValue / 100);
    const monthlyRevenue = targetCouples * arpuValue * 1000000; // Convert millions to actual value
    const annualRevenue = monthlyRevenue * 12;
    
    // Calculate LTV based on retention rate (higher retention = longer lifetime)
    const averageLifetimeMonths = retentionValue < 50 ? 8 : 
                                retentionValue < 70 ? 18 :
                                retentionValue < 85 ? 32 : 48;
    const customerLTV = arpuValue * averageLifetimeMonths * (retentionValue / 100);
    
    // Total addressable market calculation - using the input couples value
    const totalMarketValue = couplesValue * 1000000 * arpuValue * 12; // Convert to actual dollars
    
    // Calculate realistic investor returns
    const yearThreeRevenue = annualRevenue * Math.pow(1.35, 3); // 35% annual growth for 3 years
    const revenueMultiple = annualRevenue > 100000000 ? 8 : annualRevenue > 50000000 ? 6 : 4;
    const totalInvestment = 250000; // $250K seed investment
    const exitValuation = yearThreeRevenue * revenueMultiple;
    const investorReturn = exitValuation / totalInvestment;

    // Update display with better formatting
    document.getElementById('targetUsers').textContent = targetCouples >= 1 ? 
        targetCouples.toFixed(1) + 'M' : (targetCouples * 1000).toFixed(0) + 'K';
    document.getElementById('monthlyRevenue').textContent = '$' + 
        (monthlyRevenue >= 1000000000 ? (monthlyRevenue/1000000000).toFixed(1) + 'B' : 
         monthlyRevenue >= 1000000 ? (monthlyRevenue/1000000).toFixed(1) + 'M' : 
         (monthlyRevenue/1000).toFixed(0) + 'K');
    document.getElementById('annualRevenue').textContent = '$' + 
        (annualRevenue >= 1000000000 ? (annualRevenue/1000000000).toFixed(1) + 'B' : 
         annualRevenue >= 1000000 ? (annualRevenue/1000000).toFixed(0) + 'M' : 
         (annualRevenue/1000).toFixed(0) + 'K');
    document.getElementById('customerLTV').textContent = '$' + customerLTV.toFixed(0);
    document.getElementById('totalMarketValue').textContent = '$' + 
        (totalMarketValue >= 1000000000 ? (totalMarketValue/1000000000).toFixed(1) + 'B' : 
         (totalMarketValue/1000000).toFixed(0) + 'M');
    
    // Format investor return with more detail
    if (investorReturn >= 1000) {
        document.getElementById('investorReturn').textContent = (investorReturn/1000).toFixed(1) + 'K x';
    } else {
        document.getElementById('investorReturn').textContent = investorReturn.toFixed(1) + 'x';
    }
    
    // Update the description text to be dynamic
    const roiDescription = document.getElementById('roi-description');
    if (roiDescription) {
        roiDescription.textContent = `Based on $${(totalInvestment/1000).toFixed(0)}K seed investment at ${revenueMultiple}x revenue multiple`;
    }
}

// ROI calculation variables and functions
const roiVariables = {
    conservative: {
        exitMultiple: 8,
        timeToExit: 6,
        dilutionRate: 0.4,
        successProbability: 0.6
    },
    medium: {
        exitMultiple: 12,
        timeToExit: 5,
        dilutionRate: 0.35,
        successProbability: 0.75
    },
    aggressive: {
        exitMultiple: 18,
        timeToExit: 4,
        dilutionRate: 0.3,
        successProbability: 0.85
    }
};

function calculateROI() {
    const investment = document.getElementById('investment-amount').value;
    const aggressiveness = document.getElementById('aggressiveness').value;
    const timeline = document.getElementById('timeline').value;

    if (!investment || !aggressiveness || !timeline) {
        alert('Please select all parameters to calculate your ROI.');
        return;
    }

    const investmentAmount = parseInt(investment);
    const scenario = roiVariables[aggressiveness];
    const years = parseInt(timeline);

    // Calculate ROI
    const companyValuation = 50000000; // $50M ARR * exit multiple
    const exitValuation = companyValuation * scenario.exitMultiple;
    const ownershipPercentage = (investmentAmount / 2000000) * (1 - scenario.dilutionRate); // Assuming $2M pre-money
    const grossReturn = exitValuation * ownershipPercentage;
    const netReturn = grossReturn * scenario.successProbability;
    const totalReturn = netReturn / investmentAmount;
    const annualizedReturn = Math.pow(totalReturn, 1/years) - 1;

    // Display results
    const resultsDiv = document.getElementById('roi-results');
    const gridDiv = document.getElementById('roi-grid');
    
    gridDiv.innerHTML = `
        <div style="background: rgba(255,255,255,0.1); padding: 25px; border-radius: 15px; text-align: center; border: 1px solid rgba(255,255,255,0.2);">
            <div style="font-size: 2rem; font-weight: 800; color: #22c55e; margin-bottom: 10px;">$${(netReturn/1000000).toFixed(1)}M</div>
            <div style="font-size: 1rem; opacity: 0.8;">Expected Return</div>
        </div>
        <div style="background: rgba(255,255,255,0.1); padding: 25px; border-radius: 15px; text-align: center; border: 1px solid rgba(255,255,255,0.2);">
            <div style="font-size: 2rem; font-weight: 800; color: #3b82f6; margin-bottom: 10px;">${totalReturn.toFixed(1)}x</div>
            <div style="font-size: 1rem; opacity: 0.8;">Multiple of Investment</div>
        </div>
        <div style="background: rgba(255,255,255,0.1); padding: 25px; border-radius: 15px; text-align: center; border: 1px solid rgba(255,255,255,0.2);">
            <div style="font-size: 2rem; font-weight: 800; color: #a855f7; margin-bottom: 10px;">${(annualizedReturn * 100).toFixed(0)}%</div>
            <div style="font-size: 1rem; opacity: 0.8;">Annual Return Rate</div>
        </div>
        <div style="background: rgba(255,255,255,0.1); padding: 25px; border-radius: 15px; text-align: center; border: 1px solid rgba(255,255,255,0.2);">
            <div style="font-size: 2rem; font-weight: 800; color: #06b6d4; margin-bottom: 10px;">${(ownershipPercentage * 100).toFixed(2)}%</div>
            <div style="font-size: 1rem; opacity: 0.8;">Final Ownership</div>
        </div>
    `;

    resultsDiv.style.display = 'block';
}

// Initialize calculator
document.addEventListener('DOMContentLoaded', function() {
    synchronizeInputs('aduSlider', 'aduInput');
    synchronizeInputs('monthlySlider', 'monthlyInput');
    synchronizeInputs('retentionSlider', 'retentionInput');
    synchronizeInputs('penetrationSlider', 'penetrationInput');
    calculateRevenue(); // Initial calculation
});
```

## Calculator Features

This revenue calculator includes:

### Input Parameters
- **US Couples Seeking Help**: Range from 5-47 million couples
- **Average Revenue Per User/Month**: $12-89 per month
- **Customer Retention Rate**: 40-95% retention
- **Market Capture Rate**: 0.5-15% market penetration

### Calculated Results
- **Target Couples**: Number of customers based on market capture
- **Monthly Revenue**: Total monthly recurring revenue
- **Annual Revenue**: Total yearly revenue projection
- **Customer LTV**: Customer lifetime value based on retention
- **Total Addressable Market**: Total market size calculation
- **Projected ROI Multiple**: Investment return calculation

### Mathematical Models
- **LTV Calculation**: Based on retention rates with tiered lifetime months
- **Revenue Growth**: 35% annual growth model for 3-year projections
- **Investment Returns**: Multiple scenarios (conservative, medium, aggressive)
- **Market Valuation**: Dynamic revenue multiples based on company size

### Interactive Features
- Synchronized sliders and number inputs
- Real-time calculation updates
- Responsive design for mobile/desktop
- Professional styling with gradient backgrounds
- Hover effects and animations

This calculator was designed to help investors understand the revenue potential and ROI of the TogetherWe AI-powered couples therapy platform.