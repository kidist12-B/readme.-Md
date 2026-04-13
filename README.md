
**E-Commerce Customer Behavior Analysis**
**Project Overview**


This project analyzes customer behavior patterns in an e-commerce dataset to uncover meaningful insights about spending distribution, customer satisfaction, temporal trends, and regional preferences. The analysis combines statistical methods with visualizations to provide actionable business intelligence.

**Dataset Description**
The dataset contains e-commerce transaction records with the following key attributes:
**purchase_date:** Timestamp of customer transactions
**purchase_amount:** Monetary value of each purchase
**customer_tenure_months:** Duration of customer relationship in months
**satisfaction_score:** Customer satisfaction rating (likely on a scale)
**location:** Geographic region of customers
**category:** Product category of purchased items


**Key Insights from Analysis**

**1. Spending Distribution Analysis**
The histogram visualization reveals the distribution of customer purchase amounts across the platform. The analysis identifies a statistical cutoff point (calculated using the IQR method at Q3 + 1.5×IQR) that distinguishes typical transactions from high-value purchases.

**What the data shows:** Most customers tend to make purchases within a moderate spending range, with a long tail distribution indicating a subset of high-value customers. The outlier threshold provides a benchmark for identifying VIP customers or potential anomalies that may warrant fraud investigation.

**Business implications:** Companies can use this distribution to set marketing thresholds, identify cross-selling opportunities for moderate spenders, and develop retention strategies for high-value customers who may represent significant revenue


**2. Customer Satisfaction by Tenure Analysis**
The boxplot visualization explores the relationship between customer tenure (how long someone has been a customer) and their satisfaction scores. Customers are segmented into five groups: Newbie (0-6 months), Rising (7-12 months), Regular (13-24 months), Loyal (25-60 months), and Veteran (60+ months).

**What the data shows:** The visualization reveals whether long-term customers tend to be more satisfied than newer ones.
Typically, satisfaction patterns may show that customers with moderate tenure (Regular or Loyal groups) have the highest satisfaction due to accumulated positive experiences, while very new customers might show lower satisfaction due to onboarding challenges, and long-tenured customers might show declining satisfaction or complacency.

**Business implications:** Understanding satisfaction by tenure helps identify critical periods in the customer lifecycle where intervention may be needed. If new customers show lower satisfaction, investment in onboarding processes is warranted. If veteran customers show declining satisfaction, retention efforts should focus on preventing churn among these valuable customers.


**3. Weekly Sales Trends Analysis**
The line plot tracks total sales amounts aggregated by day of the week, providing insights into temporal purchasing patterns.

**What the data shows:** The visualization reveals which days of the week drive the most sales volume. Common patterns in e-commerce often show mid-week peaks (Tuesday through Thursday) when customers are most engaged with work activities, with weekend dips as personal time takes priority. Alternatively, some platforms see weekend peaks when consumers have more leisure time for shopping.

**Business implications:** Temporal analysis enables optimized marketing timing, staffing decisions, and promotional calendar planning. If Friday shows peak activity, campaigns should be timed to reach customers earlier in the week. Inventory and customer service staffing can be adjusted based on predicted daily volumes


**4. Regional Spending Patterns Heatmap**
The heatmap visualization cross-tabulates average purchase amounts across different geographic locations and product categories, revealing spending preferences by region.

**What the data shows:** Different regions may show distinct category preferences—for example, urban areas might prefer electronics while rural areas might favor agricultural products. The visualization also identifies which category-region combinations generate the highest average transaction values, enabling geographic merchandising strategies.

**Business implications:** Regional analysis supports targeted marketing campaigns, location-specific inventory optimization, and expansion decisions. If certain categories dramatically outperform in specific regions, marketing spend can be allocated accordingly, and product availability can be adjusted regionally.

**Technical Implementation Details**


**Data Processing Pipeline**

The analysis implements a robust data processing pipeline that includes duplicate removal, column deduplication, and datetime conversion. These preprocessing steps ensure data quality and enable accurate temporal analysis.

**Feature Engineering**

Two key derived features are created to enhance analytical depth:

**Loyalty Index:** Calculated as (customer_tenure_months × satisfaction_score) / 100, this composite metric combines relationship duration with satisfaction level. Higher values indicate customers who have been around longer AND are highly satisfied—a valuable segment for referral programs and testimonials.

**Customer Grouping:** Customers are binned into lifecycle stages based on tenure duration, enabling cohort-style analysis of behavioral differences across customer maturity stages.

**Statistical Methods**

The outlier detection uses the Interquartile Range (IQR) method, a robust statistical technique less sensitive to extreme values than standard deviation-based approaches. The formula (Q3 + 1.5×IQR) identifies values that deviate substantially from typical behavior, which can indicate either valuable high-value customers or data quality issues requiring investigation.

**Visualization Components**

The dashboard-style visualization comprises four complementary panels:

**1.Spend Distribution (Histogram with KDE):** Shows the shape of spending data and highlights the outlier threshold

**2.Satisfaction by Tenure (Box Plot):** Reveals group-level differences in satisfaction across customer lifecycle stages

**3.Weekly Trends (Line Plot):** Displays temporal patterns in aggregate sales

**4.Regional Heatmap:** Presents a matrix of region-category spending averages


**Conclusion**
This analysis demonstrates a comprehensive approach to understanding e-commerce customer behavior through data visualization and statistical analysis. The insights gained can inform marketing strategy, customer success initiatives, inventory management, and regional expansion decisions.
