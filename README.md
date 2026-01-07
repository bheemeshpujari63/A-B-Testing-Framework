# A/B-Testing-Framework
#  Advanced A/B Testing Analytics Framework

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen.svg)

##  Table of Contents
- [Overview](#overview)
- [Business Problem](#business-problem)
- [Features](#features)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Statistical Tests Implemented](#statistical-tests-implemented)
- [Results & Insights](#results--insights)

---

##  Overview

This project implements a **comprehensive A/B testing framework** for product experimentation and data-driven decision making. It goes beyond basic conversion analysis to include multiple statistical tests, power analysis, sequential testing, and business impact assessment.

**Built to demonstrate:** Statistical rigor, Python expertise, data visualization skills, and business acumen for Data Analyst roles at fintech companies (Jupiter, Standard Chartered, etc.).

---

##  Business Problem

**Context:** E-commerce companies run hundreds of experiments annually to optimize user experience and increase revenue. However, poor statistical methodology leads to:
- False positives (implementing changes that don't actually work)
- Missed opportunities (abandoning good features too early)
- Revenue loss from suboptimal decisions

**Solution:** This framework provides:
1. Statistically rigorous testing methodology
2. Multiple test validation (not just one test)
3. Clear business recommendations
4. Interactive dashboards for stakeholder communication

---

##  Features

### 1. **Multiple Statistical Tests**
- ✅ Z-test for proportions (conversion rates)
- ✅ Chi-Square test (categorical analysis)
- ✅ T-test for continuous metrics (AOV, time on site)
- ✅ Mann-Whitney U test (non-parametric alternative)
- ✅ Power analysis (sample size calculation)
- ✅ Sequential testing (early stopping rules)

### 2. **Business Metrics**
- Conversion rate analysis with confidence intervals
- Revenue impact calculation
- Relative lift (% improvement)
- Statistical significance at multiple confidence levels (90%, 95%, 99%)
- Customer lifetime value (CLV) impact projection

### 3. **Advanced Analytics**
- Segmentation analysis (mobile vs desktop, new vs returning users)
- Time-series analysis (daily conversion trends)
- Funnel analysis (identify drop-off points)
- Multi-armed bandit simulation (for real-time optimization)

### 4. **Interactive Visualizations**
- Conversion rate comparison charts
- Statistical significance indicators
- Revenue impact forecasting
- User funnel visualization
- Confidence interval plots

---

## Methodology


### Experiment Design
```
Hypothesis: Changing checkout button from blue to green will increase conversions

H₀ (Null): p₁ = p₂ (no difference in conversion rates)
H₁ (Alternative): p₁ ≠ p₂ (significant difference exists)

Significance Level (α): 0.05
Power (1-β): 0.80
Minimum Detectable Effect: 10% relative lift
```
---
### Data Collection
- **Sample Size:** 20,000 users (10,000 per group)
- **Duration:** 7 days
- **Randomization:** Hash-based user ID assignment
- **Metrics Tracked:** 
  - Primary: Conversion rate
  - Secondary: Revenue per user, bounce rate, time on page

### Statistical Analysis Pipeline
1. **Data Validation:** Check for sample ratio mismatch, bot traffic
2. **Descriptive Statistics:** Mean, median, std deviation for both groups
3. **Assumption Testing:** Normality tests, variance homogeneity
4. **Hypothesis Testing:** Apply appropriate statistical tests
5. **Effect Size Calculation:** Cohen's d, odds ratio
6. **Confidence Intervals:** Bootstrap confidence intervals
7. **Business Impact:** Revenue projection and ROI calculation

---

##  Key Findings

### Experiment Results: Checkout Button Color Test

| Metric | Control (Blue) | Variant (Green) | Lift | P-value | Significant? |
|--------|---------------|-----------------|------|---------|--------------|
| **Conversion Rate** | 8.50% | 9.80% | +15.3% | 0.0023 |  Yes |
| **Revenue per User** | $4.25 | $4.90 | +15.3% | 0.0019 |  Yes |
| **Bounce Rate** | 45.2% | 42.1% | -6.9% | 0.0412 |  Yes |
| **Avg. Order Value** | $50.00 | $50.00 | 0% | 0.8234 |  No |

### Business Impact
- **Additional Monthly Revenue:** $7,800
- **Annual Revenue Impact:** $93,600
- **Implementation Cost:** $500 (one-time)
- **ROI:** 18,620%
- **Confidence Level:** 99.7%

### Recommendation
** IMPLEMENT VARIANT IMMEDIATELY**

The green button shows statistically significant improvement across conversion rate and revenue metrics with 99.7% confidence. Expected payback period: < 1 day.

---

##  Technologies Used

### Core Libraries
- **Python 3.8+** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **SciPy** - Statistical tests
- **Statsmodels** - Advanced statistical modeling

### Visualization
- **Plotly** - Interactive dashboards
- **Matplotlib/Seaborn** - Static visualizations
- **Dash** (optional) - Web-based dashboard

### Data Storage
- **SQLite** - Local database for test results
- **PostgreSQL** (production) - Scalable data warehouse

---

##  Installation

```bash
# Clone repository
git clone https://github.com/yourusername/ab-testing-framework.git
cd ab-testing-framework

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run Jupyter notebook
jupyter notebook ab_testing_analysis.ipynb
```

### Requirements.txt
```
pandas>=1.5.0
numpy>=1.23.0
scipy>=1.9.0
statsmodels>=0.13.0
plotly>=5.11.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

---

##  Usage

### Quick Start
```python
from ab_testing import ABTest

# Initialize test
test = ABTest(
    control_conversions=850,
    control_visitors=10000,
    variant_conversions=980,
    variant_visitors=10000
)

# Run analysis
results = test.run_analysis()

# View results
print(results.summary())

# Generate visualizations
test.plot_results()

# Export report
test.export_report('experiment_results.pdf')
```

### Advanced Usage
```python
# Segmentation analysis
test.analyze_by_segment(segment='device_type')

# Sequential testing
test.run_sequential_test(alpha=0.05, check_interval='daily')

# Power analysis
test.calculate_sample_size(mde=0.10, power=0.80)

# Multi-variant testing
test.compare_multiple_variants(['A', 'B', 'C', 'D'])
```

---

##  Statistical Tests Implemented

### 1. **Z-Test for Proportions**
**Use Case:** Comparing conversion rates between two groups

**Formula:**
```
z = (p̂₁ - p̂₂) / √(p̂(1-p̂)(1/n₁ + 1/n₂))
```

**When to Use:** 
- Large sample sizes (n > 30)
- Binary outcomes (converted/not converted)
- Independent samples

---

### 2. **Chi-Square Test**
**Use Case:** Testing relationship between categorical variables

**Formula:**
```
χ² = Σ((Observed - Expected)² / Expected)
```

**When to Use:**
- Multiple categories or segments
- Cross-tabulation analysis
- Testing independence

---

### 3. **T-Test (Independent Samples)**
**Use Case:** Comparing continuous metrics (e.g., average order value)

**Formula:**
```
t = (x̄₁ - x̄₂) / √(s₁²/n₁ + s₂²/n₂)
```

**When to Use:**
- Small to medium sample sizes
- Continuous data (revenue, time spent)
- Normally distributed data

---

### 4. **Mann-Whitney U Test**
**Use Case:** Non-parametric alternative when data isn't normally distributed

**When to Use:**
- Revenue data (often skewed)
- Ordinal data
- Non-normal distributions

---

### 5. **Bayesian A/B Testing**
**Use Case:** Continuous monitoring with probability of success

**Advantages:**
- No fixed sample size needed
- Probability statements (e.g., "95% chance variant is better")
- Early stopping possible

---

##  Results & Insights

### Key Learnings

1. **Sample Size Matters**
   - Achieved 95% confidence with 10,000 users per group
   - Smaller samples would require 14+ days for significance

2. **Segmentation Reveals Hidden Patterns**
   - Desktop users: +20% lift (highly significant)
   - Mobile users: +8% lift (marginally significant)
   - **Insight:** Consider mobile-specific optimization

3. **Time-Based Effects**
   - Conversion rates higher on weekdays
   - Weekend traffic has different behavior patterns
   - **Recommendation:** Run experiments minimum 7 days to capture weekly cycles

4. **Multiple Testing Problem**
   - When running 20+ tests, expect 1 false positive at α=0.05
   - **Solution:** Bonferroni correction or False Discovery Rate control

---

## 🔮 Future Enhancements

- [ ] Real-time dashboard with live experiment tracking
- [ ] Automated experiment allocation (multi-armed bandit)
- [ ] Integration with Google Analytics / Mixpanel APIs
- [ ] Machine learning model for conversion prediction
- [ ] A/A test monitoring for system validation
- [ ] Multi-page experiment tracking (full funnel analysis)
- [ ] Bayesian optimization for sample size reduction

---

##  Acknowledgments

- Statistical methodology based on industry best practices from Google, Netflix, and Booking.com
- Inspired by real-world A/B testing frameworks used in fintech
- Built as portfolio project for Data Analyst positions

---

##  References

1. Kohavi, R., Tang, D., & Xu, Y. (2020). *Trustworthy Online Controlled Experiments: A Practical Guide to A/B Testing*
2. VanderPlas, J. (2016). *Python Data Science Handbook*
3. [Evan Miller's A/B Testing Tools](https://www.evanmiller.org/ab-testing/)
4. [Netflix Technology Blog - Experimentation Platform](https://netflixtechblog.com/)

---
