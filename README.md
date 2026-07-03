# customer-segmentation-market-basket-analysis
Customer segmentation (K-Means/RFM) and market basket analysis (association rule mining) using KNIME and Tableau

# Customer Segmentation & Market Basket Analysis

Two-part analytics project applying unsupervised learning and association rule mining to solve real business problems: customer segmentation for a B2B automobile parts manufacturer, and product bundle discovery for a grocery retailer.

[Live Tableau Dashboard →](https://public.tableau.com/app/profile/akshay.sreekumar8075/viz/MRA_main-Analysis/Dashboard1)

---

## Part A — Customer Segmentation (RFM + K-Means Clustering)

### Business Problem
An automobile parts manufacturer had 3 years of transactional data but no in-house analytics capability to understand customer behavior. The goal: segment customers to enable targeted marketing and improve retention.

### Data
- **2,747** transactions, **20** variables (7 numerical, 13 categorical)
- No missing values
- Fields include order details, product line, sales value, deal size, and customer/geographic info

### Approach
1. **EDA** — analyzed sales distribution, product line popularity, deal size trends, and seasonality using Tableau
2. **RFM feature engineering** — calculated Recency, Frequency, and Monetary scores per customer
3. **K-Means clustering** in KNIME — cluster count selected using the Elbow Method, validated for business interpretability
4. **Segment profiling** — translated cluster statistics into actionable customer groups

### Key Findings
- **4 customer segments identified:**
  | Segment | Profile |
  |---|---|
  | Champions | Recent, frequent, high spend — best customers |
  | Potential Loyal | Recent, moderate frequency, low spend — upsell candidates |
  | At Risk | Low frequency, medium spend — churn risk, needs re-engagement |
  | Big Spenders | Highest spend, but inactive recently — needs immediate outreach |
- Classic Cars was the top-selling product line; USA generated the highest revenue
- Sales peak in the last 4 months of the year (seasonal trend)
- Top customer: Euro Shopping Channel ($912,294 in sales)

### Business Recommendations
- Launch win-back campaigns for **At Risk** customers
- Offer VIP/renewal programs for **Big Spenders** to re-engage high-value but inactive accounts
- Use bundled discounts to upsell **Potential Loyal** customers toward Champion status

**Tools:** Tableau, KNIME (K-Means clustering, RFM analysis)

---

## Part B — Market Basket Analysis (Association Rule Mining)

### Business Problem
A grocery retailer wanted to identify frequently co-purchased items to design combo offers, optimize inventory, and increase average basket size.

### Data
- **20,641** POS transaction rows, spanning 2018–2020
- 3 fields: Date, Order ID, Product (640 unique products)
- No missing values

### Approach
- Applied **association rule mining** (Apriori-style) with:
  - Minimum support: **0.05** (5% of transactions)
  - Minimum confidence: **0.60**
- Evaluated rules using support, confidence, and lift

### Key Findings
- Identified strong cross-sell rules, e.g.: `{cheese, cereal, yogurt} → {coffee/tea}`
- Several rules reached **100% confidence**, indicating near-certain purchase patterns
- Products like pork, yogurt, soap, and cereal appeared across multiple high-confidence rules

### Business Recommendations
- Create combo packs/promotions around high-lift item pairs (e.g., breakfast bundle: cereal + yogurt + coffee)
- Use rule-based product placement to increase basket size
- Target promotions using confidence/lift thresholds to prioritize the highest-impact bundles

**Tools:** KNIME (Association Rule Mining / Apriori)

