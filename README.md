# marketing_campaigns

## Logistic Regression Results Across Campaigns

### Business Insights

Across the five campaigns, logistic regression confirms several of the same drivers identified by tree-based models, while adding complementary perspective on how customer attributes shift the likelihood of campaign acceptance.

#### Campaign 1
- Household Income and Wine Spending are the strongest positive predictors, mirroring the dominance of income and wine in the tree-based models.  
- Catalog purchases and website visits also increase campaign acceptance, consistent with engagement as a recurring theme across models.  
- Negative signals like store purchases and fruit spending suggest traditional or low-margin channels are less effective, again in line with tree-based findings.  

#### Campaign 2
- Income, wine spending, and catalog purchases remain critical positive drivers, fully aligned with tree-based importance rankings.  
- Web activity (website visits) shows up as an additional positive signal.  
- Negative predictors such as fish, meat, and web purchases reinforce the idea that high online transaction activity doesn’t always translate into responsiveness to campaigns.  

#### Campaign 3
- Catalog purchases, gold product spending, and web visits emerge as the strongest positive drivers, confirming that high-value product engagement and digital activity are central to responsiveness.  
- Household income shows as a weaker or even negative predictor here, which may reflect multicollinearity effects rather than a true business pattern.  
- Catalog and luxury product buyers remain more receptive, giving confidence in targeting this segment.  

#### Campaign 4
- Wine spending and household income again lead, reinforcing their status as universal predictors across all models.  
- Positive contributions from web visits and catalog purchases strengthen the narrative that digital engagement is a reliable indicator of responsiveness.  
- Negative signals from meat, sweets, and children/teens count are consistent with tree-based models’ finding that larger families and everyday grocery spending correlate with lower campaign response.  

#### Campaign 5
- The most decisive positive drivers are household income and wine spending, perfectly aligned with Random Forest and XGBoost.  
- Gold and sweets spending also contribute positively, suggesting premium and indulgence product buyers are most receptive.  
- Negative associations with deals, marital status categories, and fish purchases further support the idea that discount-driven and family-oriented customers are less responsive.  

---

### Key Takeaways Across Campaigns
- **Consistent predictors**: Household income and wine spending stand out across all models and campaigns, making them the most reliable levers for targeting.  
- **Engagement signals**: Catalog purchases and web activity repeatedly emerge as positive drivers, highlighting the importance of omnichannel engagement.  
- **Less responsive segments**: Customers with higher family size, stronger focus on grocery/discount purchases, or heavy store reliance show weaker responses, confirming segmentation opportunities.  

---

## Campaigns Feature Importance – Tree-Based Models

#### Campaign 1
The strongest driver of response was household income, followed by spending on meat and wines. Customers with higher incomes and consistent grocery spending showed greater acceptance. Catalog purchases and deal sensitivity also played a role, indicating the campaign appealed to both loyal premium customers and promotion-driven buyers. Engagement metrics such as time since becoming a customer and recency of purchases reinforced this effect.  
**Insight:** Campaign 1 was most effective with long-term, high-income customers who regularly shop premium categories but also respond to deals.  

---

#### Campaign 2
Response was dominated by wine spending, with household income and catalog purchases as additional drivers. Customers with higher wine expenditure and stronger engagement in premium categories (e.g., gold, meat) were far more likely to accept the offer.  
**Insight:** Campaign 2 resonated most with premium and luxury-oriented customers, particularly heavy wine buyers. Positioning this type of campaign around exclusive wine or high-end offers will maximize results.  

---

#### Campaign 3
Key factors included store and catalog purchases, luxury spending (gold and wines), and household income. Meat and fish spend also mattered, along with customer age, which suggested stronger response among middle-aged customers with spending capacity.  
**Insight:** Campaign 3 succeeded with traditional store/catalog shoppers who purchase luxury consumables. Future campaigns should highlight exclusive in-store or catalog bundles, targeting these high-value segments.  

---

#### Campaign 4
The top driver was again wine spending, supported by household income. Other important factors included spending on meat and fruits, store purchases, and recency indicators such as web visits and customer tenure. Age also influenced results, suggesting demographic variation in responsiveness.  
**Insight:** Campaign 4 reached affluent wine and food category buyers with recent engagement, making it well suited for omnichannel strategies that combine in-store and online follow-ups.  

---

#### Campaign 5
Household income was by far the strongest driver, with wine spending and catalog engagement also highly predictive. Additional signals included meat and fish spending, age, and teens in the household, showing that family composition influenced responsiveness. Deal sensitivity was present but secondary.  
**Insight:** Campaign 5 was most effective among affluent, wine-buying households with families, particularly those engaged through the catalog channel. Scaling should focus on premium catalog offers tailored to high-income family households.  

---

### Overall Patterns Across Campaigns
- **Household income and spending on wines/meat** consistently defined responsiveness, highlighting the importance of affluent, premium buyers.  
- **Catalog channel engagement** was a recurring driver, showing that catalog customers are particularly responsive.  
- **Customer tenure and recency** mattered across multiple campaigns, confirming that engaged, long-standing customers are more likely to accept.  
- **Demographics such as age and household composition** occasionally emerged, suggesting targeted family-oriented opportunities.  
