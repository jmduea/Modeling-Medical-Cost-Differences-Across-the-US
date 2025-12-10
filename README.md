# Modeling Medical Cost Differences Across the US

[![Project Status](https://img.shields.io/badge/Status-Complete-success)](https://github.com/jmduea/Modeling-Medical-Cost-Differences-Across-the-US)
[![Analysis](https://img.shields.io/badge/Analysis-Regression-blue)](https://github.com/jmduea/Modeling-Medical-Cost-Differences-Across-the-US)
[![Data](https://img.shields.io/badge/Data-Insurance-orange)](https://github.com/jmduea/Modeling-Medical-Cost-Differences-Across-the-US)

A comprehensive statistical analysis investigating whether factors influencing medical insurance costs remain consistent across different US regions. This project employs multiple linear regression modeling with logarithmic transformations to understand regional variations in healthcare expenses.

## 📋 Table of Contents

- [Overview](#overview)
- [Research Question](#research-question)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Visualizations](#visualizations)
- [Technologies](#technologies)
- [Repository Structure](#repository-structure)
- [Results](#results)
- [Authors](#authors)
- [References](#references)

## 🎯 Overview

Healthcare costs in the United States vary significantly across regions, influenced by demographic and lifestyle factors. This project investigates whether predictors of medical insurance charges—such as age, BMI, smoking status, and family size—have consistent effects across the four major US regions (Northeast, Northwest, Southeast, Southwest).

### Motivation

Understanding regional variations in medical costs is crucial because:
- It reveals whether individuals face cost disparities based solely on their geographic location
- It identifies which specific factors most significantly impact healthcare expenses
- It provides insights for policy makers and insurance providers on regional healthcare dynamics
- It helps beneficiaries understand what drives their insurance costs

## ❓ Research Question

**"Do the factors that influence medical costs remain consistent across different regions?"**

This question addresses the variability in medical costs billed by insurance across the United States, potentially driven by demographic and lifestyle differences.

## 📊 Dataset

The dataset contains **1,338 beneficiaries** with complete information on annual medical insurance charges and associated predictors.

### Data Source
- **Origin**: Medical Cost Personal Datasets from Kaggle
- **Original Use**: Machine Learning with R (Lantz, 2013)
- **Basis**: U.S. Census Bureau demographic statistics (circa 2013)

### Variables

| Variable | Type | Description | Range/Values |
|----------|------|-------------|--------------|
| **charges** | Continuous | Annual medical costs billed by insurance (USD) | Response variable |
| **age** | Integer | Age of beneficiary | ≤64 years |
| **sex** | Categorical | Gender | male/female |
| **bmi** | Continuous | Body Mass Index | kg/m² |
| **children** | Integer | Number of dependents | 0+ |
| **smoker** | Categorical | Smoking status | yes/no |
| **region** | Categorical | US Geographic region | northeast, northwest, southeast, southwest |

### Sample Data

![Dataset Sample](figures/Dataset%20first%20five%20records.png)

## 🔬 Methodology

### Statistical Approach

1. **Exploratory Data Analysis (EDA)**
   - Distribution analysis of response and predictor variables
   - Identification of outliers and data patterns
   - Assessment of relationships between variables

2. **Data Transformation**
   - Log transformation of charges to address right skewness
   - Creation of obesity indicator variable (BMI ≥ 30)
   - Multiplicative model interpretation for percentage-based insights

3. **Model Building**
   - Multiple linear regression with `log(charges)` as response
   - Incorporation of interaction effects (BMI × smoking status)
   - Regional comparison models to test effect consistency

4. **Model Validation**
   - Assumption checking (normality, homoscedasticity, independence)
   - Residual analysis
   - Model comparison and selection

### Tools Used
- **JMP**: Primary statistical analysis software
- **Statistical Techniques**: Multiple linear regression, interaction modeling, logarithmic transformations

## 🔍 Key Findings

### From Exploratory Data Analysis

1. **Charges Distribution**
   - Original charges are right-skewed with outliers
   - Log transformation normalizes the distribution
   - Heteroscedasticity present across regions (addressed through transformation)

2. **BMI Impact**
   - Average BMI: 30.66 (classified as obese by CDC standards)
   - Sharp increase in variance at BMI ≥ 30
   - Obese individuals show greater variability in medical costs

3. **Smoking Effect**
   - Smokers face **over 3× higher medical costs** than non-smokers on average
   - Outlier costs for non-smokers fall within normal range for smokers
   - Strong interaction effect between smoking and obesity

4. **Regional Patterns**
   - Southeast region shows notably higher average costs
   - Southeast has highest prevalence of:
     - Smokers
     - Obese individuals (BMI ≥ 30)
   - Regional differences largely explained by lifestyle factor distribution

### Statistical Insights

- **Interaction Effects**: The combination of obesity and smoking significantly amplifies medical costs beyond additive effects
- **Regional Consistency**: After controlling for smoking and obesity, regional effects on predictor impacts are minimal
- **Model Performance**: Logarithmic transformation successfully addressed heteroscedasticity and improved model fit

## 📈 Visualizations

The project includes comprehensive visualizations analyzing:

- **Appendix A**: Exploratory Data Analysis (11 figures)
  - Distribution analyses
  - Regional comparisons
  - BMI and smoking interactions
  
- **Appendix B**: Model Building and Selection (7 figures)
  - Regression models
  - Interaction effects
  - Model comparisons

- **Appendix C**: Model Diagnostics (8 figures)
  - Residual plots
  - Assumption validation
  - Outlier analysis

- **Appendix D**: Regional Effect Analysis (9 figures)
  - Regional model comparisons
  - Effect consistency testing
  - Regional interaction patterns

*All visualizations can be found in the `/figures` directory.*

## 🛠️ Technologies

- **Statistical Analysis**: JMP Statistical Software
- **Data Format**: CSV
- **Documentation**: Microsoft Word, PDF
- **Version Control**: Git/GitHub

### Analysis Files

- `insurance.csv` - Raw dataset (1,338 records)
- `insurance.jmp` - JMP workbook with all analyses and scripts
- `Modeling Medical Cost Differences Across the US - Kyle Smith & Jon Duea.pdf` - Complete research report
- `Project Proposal - Kyle Smith & Jon Duea.docx` - Original project proposal

## 📁 Repository Structure

```
.
├── README.md                                          # This file
├── insurance.csv                                      # Dataset (1,338 beneficiaries)
├── insurance.jmp                                      # JMP analysis workbook
├── Modeling Medical Cost Differences Across the US - Kyle Smith & Jon Duea.pdf
├── Modeling Medical Cost Differences Across the US - Kyle Smith & Jon Duea.docx
├── Project Proposal - Kyle Smith & Jon Duea.docx
└── figures/                                           # All visualization outputs
    ├── Dataset first five records.png
    ├── Figure-A1.png through Figure-A11.png          # Appendix A: EDA
    ├── Figure-B1.png through Figure-B7.png           # Appendix B: Model Building
    ├── Figure-C1.png through Figure-C8.png           # Appendix C: Diagnostics
    └── Figure-D1.png through Figure-D9.png           # Appendix D: Regional Analysis
```

## 📊 Results

### Main Conclusions

1. **Regional Consistency**: After accounting for smoking status and obesity, the effects of predictors on medical costs remain relatively consistent across regions.

2. **Primary Cost Drivers**:
   - **Smoking status**: Most significant predictor (3× cost increase)
   - **Obesity (BMI ≥ 30)**: Increases cost variability
   - **Age**: Positive correlation with costs
   - **Smoking × Obesity interaction**: Amplifies costs beyond individual effects

3. **Regional Differences**: Largely attributable to differences in the prevalence of smokers and obese individuals rather than inherent regional effects on predictor impacts.

4. **Model Interpretation**: Using multiplicative models (log-transformed charges) provides intuitive percentage-based interpretations suitable for healthcare cost analysis.

### Practical Implications

- Geographic location affects insurance costs primarily through population health characteristics
- Prevention and intervention programs targeting smoking cessation and obesity management could significantly reduce regional cost disparities
- Insurance pricing models should account for interaction effects between lifestyle factors

## 👥 Authors

**Kyle Smith & Jon Duea**

*STAT 311 Regression Analysis, Spring 2025*

## 📚 References

1. Choi, M. (n.d.). *Medical Cost Personal Datasets*. Kaggle. Retrieved from https://www.kaggle.com/datasets/mirichoi0218/insurance

2. Lantz, B. (2013). *Machine Learning with R*. Packt Publishing.

3. Centers for Disease Control and Prevention. (2024). *About Adult BMI*. Retrieved from https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html

4. Stewart, S. T., Cutler, D. M., & Rosen, A. B. (2009). *Forecasting the Effects of Obesity and Smoking on U.S. Life Expectancy*. New England Journal of Medicine, 361(23), 2252-2260.

---

## 📝 How to Reproduce

1. **Clone the repository**:
   ```bash
   git clone https://github.com/jmduea/Modeling-Medical-Cost-Differences-Across-the-US.git
   ```

2. **Open the JMP workbook**:
   - Requires JMP Statistical Software
   - Open `insurance.jmp`
   - All scripts are named to match corresponding figures and tables

3. **Review the analysis**:
   - Complete methodology and results in the PDF report
   - All figures regenerable from JMP scripts

---

## 📄 License

This project was completed as coursework for STAT 311 Regression Analysis. The dataset is publicly available and originally sourced from Kaggle.

---

*For questions or collaborations, please reach out through GitHub issues.*