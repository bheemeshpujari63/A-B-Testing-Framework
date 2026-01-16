# A/B-Testing-Framework
# 🧪 A/B Testing Analytics Framework

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Statistical Analysis](https://img.shields.io/badge/Analysis-Statistical-green.svg)]()
[![Data Science](https://img.shields.io/badge/Data-Science-orange.svg)]()

**A comprehensive statistical framework for experiment analysis and data-driven decision making in product development**

> 💼 **Built for**: Product Analyst, Business Analyst, and Decision Science roles  
> 🎯 **Skills Demonstrated**: Statistical Testing, Python, Data Visualization, Business Impact Analysis

---

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [What I Built](#what-i-built)
- [Key Results](#key-results)
- [Technical Implementation](#technical-implementation)
- [How to Run This Project](#how-to-run-this-project)
- [Skills Demonstrated](#skills-demonstrated)

---

## 🎯 Project Overview

This project simulates a real-world A/B testing scenario where a company wants to test whether changing their **checkout button color from blue to green** will increase conversions. Instead of relying on a single test, I implemented **4 different statistical tests** to validate the results and calculated the **business impact** of implementing the change.

**Why This Matters:**  
Companies like Amazon, Netflix, and Flipkart run thousands of A/B tests annually. Making wrong decisions costs millions. This framework ensures statistically rigorous testing before implementing changes.

---

## 💡 Business Problem

### The Challenge
An e-commerce company wants to improve their conversion rate. They hypothesize that a **green checkout button** will perform better than their current **blue button**.

### The Question
**Should we implement the green button company-wide?**

To answer this, we need to:
1. ✅ Ensure the improvement is **statistically significant** (not just random chance)
2. ✅ Quantify the **business impact** (revenue increase)
3. ✅ Validate across **multiple statistical tests** (not rely on just one)
4. ✅ Analyze different **user segments** (mobile vs desktop, new vs returning)

---

## 🛠️ What I Built

### 1. **Data Simulation**
- Generated realistic experiment data for **20,000 users**
- Control Group: 10,000 users (blue button)
- Variant Group: 10,000 users (green button)
- Tracked: Conversions, Revenue, Device Type, User Type, Time on Site

### 2. **Multiple Statistical Tests**
Instead of relying on one test, I implemented **4 different tests** for validation:

| Test | Purpose | Result |
|------|---------|--------|
| **Z-Test** | Compare conversion rates | ✅ Significant (p=0.0001) |
| **Chi-Square Test** | Test independence | ✅ Significant (p=0.0001) |
| **T-Test** | Compare revenue per user | ✅ Significant (p=0.0018) |
| **Mann-Whitney U** | Non-parametric validation | ✅ Significant (p=0.0001) |

**All 4 tests passed** → High confidence in results!

### 3. **Business Impact Analysis**
Translated statistical results into business metrics:
- **Monthly Revenue Impact**: $79,480
- **Annual Revenue Impact**: $953,762
- **Implementation Cost**: $500
- **ROI**: 190,652%
- **Payback Period**: Less than 1 day

### 4. **Advanced Analytics**
- **Segmentation Analysis**: Analyzed performance by device and user type
- **Confidence Intervals**: 95% confidence the true lift is between 0.80% and 2.38%
- **Effect Size**: Calculated Cohen's h to measure practical significance
- **Power Analysis**: Verified sample size was sufficient for reliable results

---

## 📊 Key Results

### Experiment Outcome

| Metric | Control (Blue) | Variant (Green) | Improvement | P-value |
|--------|----------------|-----------------|-------------|---------|
| **Conversion Rate** | 8.25% | 9.84% | **+19.3%** | 0.0001 ✅ |
| **Revenue per User** | $4.19 | $4.99 | **+19.0%** | 0.0018 ✅ |
| **Total Revenue** | $41,906 | $49,854 | **+$7,948** | - |

### Statistical Confidence
- **Confidence Level**: 99.99%
- **Relative Lift**: +19.27%
- **Absolute Lift**: +1.59 percentage points
- **95% Confidence Interval**: [0.80%, 2.38%]

### Segmentation Insights

**By Device:**
- Desktop: 7.98% → 9.26% (+16.0% lift)
- Mobile: 8.42% → 10.25% (+21.7% lift)
- **Insight**: Green button works even better on mobile!

**By User Type:**
- New Users: 8.23% → 10.09% (+22.6% lift)
- Returning Users: 8.30% → 9.25% (+11.4% lift)
- **Insight**: Especially effective for new customers

---

## 🎓 Technical Implementation

### Technologies Used
```
Python 3.8+        → Core programming language
Pandas             → Data manipulation and analysis
NumPy              → Numerical computations
SciPy              → Statistical tests
Plotly             → Interactive visualizations
Statsmodels        → Advanced statistical modeling
```

### Statistical Tests Explained

#### 1. **Z-Test for Proportions**
- **What it does**: Compares conversion rates between two groups
- **When to use**: Large sample sizes (n > 30), binary outcomes
- **Formula**: z = (p₁ - p₂) / √[p(1-p)(1/n₁ + 1/n₂)]
- **My Result**: z = 3.92, p = 0.0001 ✅

#### 2. **Chi-Square Test**
- **What it does**: Tests if two variables are independent
- **When to use**: Categorical data, multiple categories
- **My Result**: χ² = 15.17, p = 0.0001 ✅

#### 3. **Independent T-Test**
- **What it does**: Compares means of continuous variables (revenue)
- **When to use**: Continuous data, normally distributed
- **My Result**: t = 3.13, p = 0.0018 ✅

#### 4. **Mann-Whitney U Test**
- **What it does**: Non-parametric alternative (no normality assumption)
- **When to use**: Skewed data like revenue, ordinal data
- **My Result**: U = 50,794,227, p = 0.0001 ✅

---

## 💻 How to Run This Project

### Prerequisites
```bash
Python 3.8 or higher installed
Basic understanding of command line
```

### Installation Steps

**Step 1: Clone the repository**
```bash
git clone https://github.com/yourusername/ab-testing-framework.git
cd ab-testing-framework
```

**Step 2: Install required libraries**
```bash
pip install pandas numpy scipy plotly matplotlib seaborn
```

**Step 3: Run the analysis**
```bash
python ab_testing_analysis.py
```

### Expected Output
```
🧪 ADVANCED A/B TESTING FRAMEWORK
======================================================================
✅ Generated data for 20,000 users
📊 Control Conversion Rate: 8.25%
📊 Variant Conversion Rate: 9.84%
📊 Relative Lift: +19.27%

🔬 Statistical Tests Summary:
   ✅ Tests passed (p < 0.05): 4/4

💰 Projected Annual Revenue Impact: $953,761.69

🎉 RECOMMENDATION: IMPLEMENT VARIANT IMMEDIATELY
```

---

## 🎯 Skills Demonstrated

### 1. **Statistical Analysis**
✅ Hypothesis testing (Z-test, Chi-Square, T-test)  
✅ Confidence intervals and p-values  
✅ Effect size calculation (Cohen's h)  
✅ Power analysis and sample size determination  
✅ Non-parametric methods (Mann-Whitney U)

### 2. **Python Programming**
✅ Data manipulation with Pandas  
✅ Statistical computing with NumPy/SciPy  
✅ Clean, documented code  
✅ Modular function design

### 3. **Data Visualization**
✅ Interactive dashboards with Plotly  
✅ Clear, professional charts  
✅ Stakeholder-ready presentations

### 4. **Business Acumen**
✅ Translating statistics into business metrics  
✅ ROI and revenue impact calculations  
✅ Clear, actionable recommendations  
✅ Risk assessment and decision frameworks

### 5. **Analytical Thinking**
✅ Segmentation analysis (device, user type)  
✅ Multiple test validation (not just one test)  
✅ Comprehensive evaluation before recommendations

---

## 📈 Business Recommendation

### ✅ FINAL DECISION: **IMPLEMENT THE GREEN BUTTON**

**Reasoning:**
1. ✅ **Statistical Significance**: All 4 tests show p < 0.05 (99.99% confidence)
2. ✅ **Practical Significance**: +19.3% lift is substantial for business
3. ✅ **Consistent Results**: Improvement seen across all user segments
4. ✅ **Strong ROI**: $953K annual impact vs $500 implementation cost
5. ✅ **Low Risk**: No negative impacts on secondary metrics

**Implementation Plan:**
1. Roll out to 100% of users immediately
2. Monitor for 2 weeks post-launch
3. Set up automated alerts for conversion rate drops
4. Document learnings for future experiments

---

## 🔮 Future Enhancements

- [ ] **Real-time dashboard** for live experiment monitoring
- [ ] **Sequential testing** with early stopping rules
- [ ] **Multi-variant testing** (A/B/C/D tests)
- [ ] **Bayesian A/B testing** for continuous probability estimates
- [ ] **Sample size calculator** for experiment planning
- [ ] **Integration with Google Analytics** API for real data

---

## 📚 What I Learned

### Technical Skills
- Implemented 4 different statistical tests from scratch
- Learned when to use parametric vs non-parametric tests
- Built confidence in interpreting p-values and confidence intervals
- Gained experience with Python statistical libraries

### Business Skills
- Learned to translate statistics into business impact
- Understood importance of segmentation analysis
- Practiced making data-driven recommendations
- Improved stakeholder communication skills

### Key Takeaways
1. **Never rely on just one statistical test** - validate with multiple methods
2. **Business impact matters more than p-values** - always calculate ROI
3. **Segmentation reveals insights** - overall metrics can hide important patterns
4. **Sample size is critical** - underpowered tests lead to false conclusions

---

## 👤 Author

**Pujari Bheemesh**  
📧 Email: bheemeshpujari63@gmail.com  
💼 LinkedIn: [linkedin.com/in/bheemeshpujari](https://www.linkedin.com/in/bheemeshpujari)  
🐙 GitHub: [@bheemeshpujari63](https://github.com/bheemeshpujari63)

---

## 🙏 Acknowledgments

- Statistical methodology inspired by industry practices at Google, Netflix, and Amazon
- Built as part of portfolio development for Product/Business Analyst roles
- Dataset simulated to demonstrate real-world experiment analysis

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---


##  References

1. Kohavi, R., Tang, D., & Xu, Y. (2020). *Trustworthy Online Controlled Experiments: A Practical Guide to A/B Testing*
2. VanderPlas, J. (2016). *Python Data Science Handbook*
3. [Evan Miller's A/B Testing Tools](https://www.evanmiller.org/ab-testing/)
4. [Netflix Technology Blog - Experimentation Platform](https://netflixtechblog.com/)

---

⭐ **If this project helped you understand A/B testing, please give it a star!**

**Skills Showcased**: Python | Statistical Analysis | A/B Testing | Data Visualization | Business Analytics | Hypothesis Testing | ROI Analysis
---
