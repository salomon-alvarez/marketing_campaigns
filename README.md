# Customer Segmentation & Campaign Response Analysis

## Table of Contents
1. [Executive Summary](#executive-summary)  
2. [Objectives & Business Problem](#objectives--business-problem)  
3. [Results](#results)  
   - [Customer Profiles](#customer-profiles)  
   - [General Purchase Behavior](#general-purchase-behavior)  
   - [Campaign Performance](#campaign-performance)  
   - [Modeling Campaign Responses](#modeling-campaign-responses)  
   - [Predicting Customer Complaints](#predicting-customer-complaints)  
4. [Methodology](#methodology)  
5. [Key Insights & Business Implications](#key-insights--business-implications)  
6. [Limitations & Next Steps](#limitations--next-steps)  

---

## Executive Summary

This project analyzes a retail marketing dataset to improve campaign targeting and customer segmentation.  
Using exploratory data analysis (EDA), feature engineering, and multiple machine learning models (Random Forest, XGBoost, Logistic Regression), we identified the key drivers of campaign acceptance and customer complaints, while building actionable segmentation strategies such as **RFM scoring**.

**Key Achievements:**
- Built segmentation models that highlight **high-income and wine-buying households** as the most responsive to marketing campaigns.  
- Designed a **6-category RFM framework** (Champions, Loyal Customers, Potential Loyalists, At Risk, Cold, Lost) to simplify customer retention and re-engagement strategies.  
- Discovered that **catalog and web engagement** consistently predict campaign acceptance across multiple campaigns.  
- Identified that **affluent, long-tenure customers** are both the most responsive and the most likely to complain, emphasizing the need for proactive relationship management.  
- Developed visual dashboards in Tableau to present findings in an executive-friendly format.  

---

## Objectives & Business Problem

The dataset represents thousands of customer records with demographics, purchase behavior, and responses to marketing campaigns.  
The company’s core challenge is **increasing campaign ROI** by better identifying which customers to target and how to engage them.  

**Business Questions:**
- Which customer attributes most influence campaign acceptance?  
- How can we segment customers into actionable groups to improve targeting?  
- What factors drive customer complaints, and how can they be reduced?  
- How do online vs. offline channels (web, catalog, store) affect responsiveness?  

**Objective:**  
To create a **data-driven segmentation and targeting framework** that improves marketing efficiency, boosts campaign conversion, and reduces customer dissatisfaction.

---

## Results

### Customer Profiles  

#### Average Age of Respondents by Campaign
The table below shows the average customer age for each campaign among those who **accepted** the offer, alongside the overall customer average for comparison:

| Group               | Average Age (years) |
|---------------------|----------------------|
| Overall Customers   | 51.1 |
| Campaign 1          | 51.6 |
| Campaign 2          | 51.9 |
| Campaign 3          | 48.6 |
| Campaign 4          | 54.0 |
| Campaign 5          | 50.3 |

**Insights:**  
- The overall customer base averages about **51.1 years old**.  
- Campaign 3 attracted slightly younger respondents on average.  
- Campaign 4 was most effective among older customers (around 54).  
- Campaigns 1, 2, and 5 landed in the early 50s range, showing consistency across those groups.  

#### Demographic Distribution  
![Marital Status Distribution](images/marital_status.png)  
![Education Level Distribution](images/education_level.png)  
![Households with Kids/Teens](images/kids_teens.png)  

---

### General Purchase Behavior  

![Purchases by Channel and Product Type](images/channels_prod_type_bars.png)  
![Spending by Product Category](images/spend_by_category.png)  
![Frequency vs. Monetary Value](images/freq_vs_monetary.png)  
![Income vs. Wine Spending](images/income_vs_wine.png)  

---

### Campaign Performance  

#### Conversion Rates  
An analysis of the conversion rates across the five campaigns revealed clear differences in customer responsiveness:

| Campaign   | Conversion Rate (%) |
|------------|----------------------|
| Campaign 4 | 7.45                 |
| Campaign 3 | 7.41                 |
| Campaign 5 | 7.32                 |
| Campaign 1 | 6.45                 |
| Campaign 2 | 1.36                 |

**Key Insights:**  
- **Campaign 4** achieved the highest conversion rate (7.45%), closely followed by Campaigns 3 and 5.  
- **Campaign 1** performed moderately well at 6.45%.  
- **Campaign 2** showed the weakest performance (1.36%), indicating a significant gap compared to the others.  

**Interpretation:**  
Campaigns 3, 4, and 5 were the most effective at engaging customers, suggesting that their design and targeting aligned better with customer interests. Campaign 2, however, may require a complete redesign or a shift in audience targeting to improve outcomes.  

#### Re-Engagement  
Re-engagement was measured at 30, 60, and 90 days after campaigns, capturing the percentage of customers who made a purchase within those windows.

| Time Window | Re-Engagement Rate (%) |
|-------------|-------------------------|
| 30 days     | 32.3                   |
| 60 days     | 61.6                   |
| 90 days     | 91.2                   |

**Key Insights:**  
- About **one-third of customers (32.3%)** re-engaged within the first 30 days, indicating a strong short-term impact from campaigns.  
- Engagement continued to grow steadily, with **over 60% returning by 60 days**.  
- By **90 days, more than 9 in 10 customers (91.2%)** had re-engaged, suggesting campaigns had a long-lasting effect in maintaining customer relationships.  

**Interpretation:**  
These results highlight that campaigns not only drive immediate responses but also sustain customer activity over time. The strong 90-day retention suggests that targeted follow-ups and loyalty programs could further maximize lifetime value.  

---

### Modeling Campaign Responses  

#### Logistic Regression Results Across Campaigns  

Logistic regression confirms several of the same drivers identified by tree-based models, while adding complementary perspective on how customer attributes shift the likelihood of campaign acceptance.  

- **Campaign 1**: Income and wine spending lead; catalog and web activity help; store/fruit spending hurts.  
- **Campaign 2**: Income, wine, and catalog dominate; fish, meat, and web purchases predict lower responsiveness.  
- **Campaign 3**: Catalog, gold, and web spending lead; household income plays a weaker/negative role; catalog and luxury remain key.  
- **Campaign 4**: Wine and income again lead; web and catalog boost; families and grocery focus hurt.  
- **Campaign 5**: Income and wine strongest; gold and sweets add; discounts and family-oriented buyers are less responsive.  

**Key Takeaways Across Campaigns**  
- **Consistent predictors**: Household income and wine spending are universal drivers.  
- **Engagement signals**: Catalog and web activity repeatedly boost campaign response.  
- **Less responsive segments**: Larger households and discount/grocery-driven buyers show weaker engagement.  

#### Tree-Based Models (Random Forest & XGBoost)  

- Campaigns 1–2: Strong premium signals (income, wine, catalog, gold).  
- Campaign 3: Store + catalog shoppers with luxury preferences.  
- Campaign 4: Wine + affluent food buyers, with recent digital engagement.  
- Campaign 5: High-income wine-buying households with families.  

Overall, **tree-based models aligned with logistic regression** in highlighting income, wine, and catalog/web engagement as the top levers for campaign success.  

![Feature Importances Campaign 1](images/Feature_Importances_for_Campaign1_Random_Forest_vs_XGBoost.png)  
![Feature Importances Campaign 2](images/Feature_Importances_for_Campaign2_Random_Forest_vs_XGBoost.png)  
![Feature Importances Campaign 3](images/Feature_Importances_for_Campaign3_Random_Forest_vs_XGBoost.png)  
![Feature Importances Campaign 4](images/Feature_Importances_for_Campaign4_Random_Forest_vs_XGBoost.png)  
![Feature Importances Campaign 5](images/Feature_Importances_for_Campaign5_Random_Forest_vs_XGBoost.png)  

---

### Predicting Customer Complaints  

To understand which factors are most associated with customers filing complaints, we trained a Random Forest model using **Had_Complaint** as the target variable.  

![Top 15 Feature Importances — Predicting Complaints](images/complaints_feature_importance.png)  

**Key Insights:**  
- **Tenure matters**: Long-term customers complain more, likely due to higher expectations.  
- **Affluent segments**: Older, higher-income, and luxury buyers (gold, wine, meat) are more complaint-prone.  
- **Engagement links**: Higher AOV, recent shopping activity, and omnichannel patterns (store, web) connect with complaint behavior.  

**Business Interpretation:**  
Complaints are concentrated among **the most valuable customers** — affluent, long-tenure, premium buyers.  

**Actionable Implications:**  
- Strengthen support and quality control for premium buyers.  
- Monitor satisfaction among high-value households.  
- Protect long-term relationships with proactive complaint resolution.  

---

## Methodology

### Dataset Description

The raw dataset contains **2,205 customer records** with **39 features** covering demographics, purchase behavior, marketing campaign responses, and complaints.  

**Key feature groups:**
- **Demographics:**  
  - `Income`: Household yearly income.  
  - `Kidhome`, `Teenhome`: Number of children and teenagers in the household.  
  - `Age`: Customer age.  
  - `Customer_Days`: Number of days since becoming a customer.  
  - Marital status (one-hot encoded): `marital_Divorced`, `marital_Married`, `marital_Single`, `marital_Together`, `marital_Widow`.  
  - Education level (one-hot encoded): `education_2n Cycle`, `education_Basic`, `education_Graduation`, `education_Master`, `education_PhD`.  

- **Purchasing behavior (monetary values are yearly spending in each category):**  
  - `MntWines`, `MntFruits`, `MntMeatProducts`, `MntFishProducts`, `MntSweetProducts`, `MntGoldProds`.  
  - Aggregates: `MntTotal` (total spending), `MntRegularProds` (all products except gold).  

- **Purchasing channels:**  
  - `NumDealsPurchases`: Number of purchases with discounts.  
  - `NumWebPurchases`, `NumCatalogPurchases`, `NumStorePurchases`: Purchases by channel.  
  - `NumWebVisitsMonth`: Number of website visits per month.  

- **Marketing campaign responses:**  
  - `AcceptedCmp1`, `AcceptedCmp2`, `AcceptedCmp3`, `AcceptedCmp4`, `AcceptedCmp5`: Binary indicators of acceptance for five campaigns.  
  - `Response`: General campaign response flag.  
  - `AcceptedCmpOverall`: Total number of campaigns accepted.  

- **Customer feedback:**  
  - `Complain`: Indicates whether the customer filed a complaint.  

- **Other technical fields:**  
  - `Z_CostContact`, `Z_Revenue`: Constant columns (same value for all customers, removed during cleaning).  

**Summary:**  
This dataset provides a comprehensive view of customer demographics, engagement, and purchase behavior across multiple channels, as well as their responsiveness to marketing campaigns. It is well-suited for customer segmentation, campaign targeting, and churn/complaint prediction.

This project followed a structured analytics workflow, moving from raw data exploration to advanced modeling and business interpretation. The technical implementation is fully documented in the Jupyter Notebooks (see repository), while the summary below outlines the key steps.

---

### 1. Data Understanding & Cleaning
- Explored the raw dataset of **2,205 customer records and 39 features**, covering demographics, purchase behavior, marketing campaigns, and complaints.  
- Identified and addressed inconsistencies:
  - Removed constant columns (`Z_CostContact`, `Z_Revenue`) with no analytical value.  
  - Corrected `Spend_Total` to include gold product spending.  
  - Renamed columns for clarity and consistency (e.g., `Kidhome → Kids_Count`, `Teenhome → Teens_Count`).  
- Checked distributions and detected skewness across spending variables.  
- Handled outliers using boxplot inspections and domain-driven thresholds.

---

### 2. Exploratory Data Analysis (EDA)
- Visualized distributions of income, age, and spending categories.  
- Correlation and heatmap analysis revealed strong relationships between spending categories.  
- Conducted bivariate analysis (e.g., income vs. wine, frequency vs. monetary value).  
- Derived early insights into high-income, wine-buying households as key drivers of engagement.  

---

### 3. Feature Engineering
- **Campaign Metrics:**  
  - Calculated individual campaign conversion rates.  
  - Built customer-level re-engagement metrics (30, 60, 90 days).  

- **RFM Segmentation:**  
  - Applied Recency, Frequency, Monetary scoring using quintiles (1–5).  
  - Created six actionable customer segments: Champions, Loyal, Potential Loyalists, At Risk, Cold, and Lost.  

- **Additional Features:**  
  - Calculated Average Order Value (AOV).  
  - Aggregated total purchases and channel usage indicators.  

---

### 4. Multicollinearity & Scaling
- Conducted **Variance Inflation Factor (VIF) analysis** to drop redundant features and reduce multicollinearity.  
- Applied **Yeo-Johnson transformations** to correct skewness in heavily skewed spending variables.  
- Implemented **scaling pipeline**:
  - Standardized continuous variables.  
  - Passed through binary variables without transformation.  
- Produced a final **scaled feature dataset** for modeling.

---

### 5. Modeling
- **Random Forest & XGBoost:**  
  - Feature importance analysis across all five campaigns.  
  - Confirmed household income, wine spending, catalog engagement, and web visits as consistent predictors of acceptance.  

- **Logistic Regression:**  
  - Validated tree-based findings while offering interpretability.  
  - Showed positive predictors (income, wine, catalog/web activity) and negative predictors (store/grocery spending, larger households).  
  - Evaluated with ROC-AUC and Precision-Recall AUC.  

- **Customer Complaints Model:**  
  - Built a Random Forest to predict complaint likelihood.  
  - Found tenure, income, age, and luxury spending as top drivers of complaints.  

---

### 6. Visualization & Business Storytelling
- Built Tableau dashboards for executive-ready insights:  
  - Campaign conversion and re-engagement.  
  - Purchase channel and product-type distributions.  
  - Segmentation by marital status, education, and household composition.  
- Produced complementary plots in Jupyter (matplotlib/seaborn) for profiling and model interpretability.

---

### 7. Documentation
- Full workflow is presented in **two Jupyter Notebooks**:  
  1. **EDA Notebook:** Data cleaning, exploration, outlier detection, and feature corrections.  
  2. **Modeling Notebook:** Feature engineering, scaling, modeling (Random Forest, XGBoost, Logistic Regression), and evaluation.  

Links to notebooks are included in the repository for technical review.


## Key Insights & Business Implications

---

### 1. Campaign Effectiveness
- **Strongest Performers:** Campaigns 3, 4, and 5 consistently delivered higher conversion rates (~7.3–7.5%).  
- **Weakest Performer:** Campaign 2 severely underperformed at 1.36%, despite reaching the same customer base.  
- **Re-Engagement:** Over 90% of customers re-engaged within 90 days, showing campaigns generated not just one-off responses but **sustained long-term activity**.

**Implication:**  
Future investments should replicate the structure and targeting of Campaigns 3–4–5, while Campaign 2 needs a complete redesign (offer, messaging, or targeting) to justify continued spending.

---

### 2. Universal Drivers of Campaign Acceptance
- **Affluence + Premium Spend:** Household income and **wine spending** are the most reliable predictors of campaign success across all models.  
- **Omnichannel Engagement:** Catalog purchases and web visits strongly correlate with responsiveness.  
- **Negative Predictors:** Store-heavy buyers, discount-driven shoppers, and larger households with grocery-focused spending are consistently less likely to accept campaigns.

**Implication:**  
Target **affluent, premium-oriented, digitally engaged customers**. Allocate fewer resources to store/grocery-focused segments where ROI is structurally weaker.

---

### 3. Product & Channel Insights
- **Wine as a Flagship Category:** Wine consistently drives responsiveness, making it a strong entry point for upselling other premium products.  
- **Catalog Still Matters:** Despite being a traditional channel, catalog engagement proved one of the strongest campaign acceptance signals.  
- **Web Visits as a Proxy for Intent:** Customers with higher web visits are more receptive, validating investment in digital retargeting strategies.

**Implication:**  
Design campaigns that **anchor around wine and premium categories**, push offers via **catalog and web**, and use digital tracking to trigger follow-ups with high-intent visitors.

---

### 4. Complaints as a Signal
- **Who Complains:** Complaints are concentrated among long-tenure, high-income, premium buyers.  
- **Business Risk:** These are the company’s most valuable customers — the ones with the greatest lifetime value and the highest expectations.

**Implication:**  
Develop a **VIP service program** to quickly resolve complaints from top-tier customers. Preventing churn in this group is worth disproportionately more than resolving issues among low-value segments.

---

### Overall Business Takeaway
- Campaigns work best when **income, premium product focus, and digital/catalog engagement** align.  
- **Wine and catalog** are not just revenue streams, but **strategic levers for marketing ROI**.  
- Protecting relationships with **affluent, high-value customers** through proactive complaint handling is as important as campaign design.  
