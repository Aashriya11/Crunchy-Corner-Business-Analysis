# Crunchy-Corner-Business-Analysis

Crunchy Corner is one of India largest Fast Foods restaurant chain and serving millions of customers daily across various cities in India with more than 1000 restaurant and have largest SKU in the industry. 
This dashboard offers a thorough analysis of the company's financial performance, comparing actual figures with budgeted data, and providing insights: overall sales, gross profit, PAT and EBITDA of the company. This facilitates effective data-driven decision-making for the company.

---

## 1. Introduction

This project focuses on delivering a comprehensive analytical solution using Power BI dashboards to evaluate:

*	**Dashboard 1: Financial Performance Analysis** – Highlights financial performance of the company: overall sales, gross profit, PAT, EBITDA and Count of SKUs. It offers insights into YOY change, illustrates trends and bifurcation of Business KPIs by different aspects.

*	**Dashboard 2: Optimising the Business** – Provides it demonstrates the comparison of Gross Profit and Volume with their average and for Category, also a chart showcasing Top-5 Categories by Gross Profit and Net Revenue.

*	**Dashboard 3: Pareto Analysis** – Demonstrating out 20% SKU Contributing 80% of the Revenue. 

*	**Dashboard 4: Quadrant Analysis** – Contribution of Location and Category by Sales and Gross Profit.

*	**Dashboard 5: Mekko Chart** – Visualizes customer segments and product-category contribution to highlight revenue concentration and growth opportunities.

*	**Dashboard 6: Financial Analysis of Business Drivers** – Actual Vs Budget Financial Analysis for Business Drivers (Sales, EBITDA, PAT, Volume) with Trend YoY.

*	**Dashboard 7: Financial Analysis of Cost Drivers** – Actual Vs Budget Financial Analysis for Cost Drivers (COGS, Packaging, Marketing) with Trend YoY.

*	**Dashboard 8: PVM Analysis** – Breaks down revenue changes into Price, Volume, and Mix effects to reveal the true drivers of sales variance.

The analysis highlights clear gaps between Actual and Budget performance and provides insights into key drivers influencing growth and profitability.

---

## 2.	Data Pre-processing Process

The first stage of preparing the datasets for analysis involved cleaning and standardizing the data to ensure accuracy, consistency, and reliability. Both the Actual and Budget datasets were imported into a single Excel workbook and processed as follows:

#### 1.	Handling Missing Values
*	Missing values in the SKU Code column were replaced with Null.
*	Missing values in categorical fields were replaced with “Unknown” to preserve rows that contained useful information in other attributes.

#### 2.	Standardizing SKU Codes
*	Inconsistent entries in the SKU Code column (e.g., “Beefy” and “CS”) were replaced with standardized numeric codes (1111 and 2222).
*	This step ensured SKU Codes were consistent and suitable for numerical analysis.

#### 3.	Removing Duplicate Records
*	Duplicate rows were identified and removed from both Actual and Budget datasets.
*	This reduced redundancy and improved the reliability of reporting.

--- 

## 3.	Data Feature Engineering

Once the datasets were cleaned, new features and structures were created to enhance the analytical capability of the model. These transformations provided meaningful attributes and a scalable structure for dashboard development:

#### 1.	Adding a “Nature” Column
*	A new column was introduced to distinguish the source of the data.
*	Records from the Actual dataset were tagged as “Actual” while those from the Budget dataset were tagged as “Budget”.
*	This allowed for straightforward comparison and combined reporting.

#### 2.	Data Modelling with Star Schema
*	The Actual and Budget datasets were appended into a unified fact table, supported by multiple dimension tables for advanced analytics.
*	Dimension Tables included: Date Table, SKU Table, Category Table, Product Table, Cluster Table, Channel Table, Location Table)

#### 3.	Assigning Unique Identifiers
*	Unique keys such as Date ID, SKU ID, Category ID, Product ID, Cluster ID, Channel ID, and Location ID were assigned to establish reliable relationships between Fact and Dimension Tables.
*	This reinforced referential integrity and optimized dashboard queries.

---

## 4.	Data Analysis

### Dashboard 1 Insights: - Financial Performance Analysis
   Overall KPIs: (for Actual)
| Metric              | Value   |
| ------------------- | ------- |
| **Total Sales**     | 559.14M |
| **Gross Profit**    | 162.22M |
| **EBITDA**          | 88.17M  |
| **PAT**             | 61.03M  |
| **Count of SKU ID** | 4207    |

   Overall KPIs: (for Budget)
| Metric              | Value   |
| ------------------- | ------- |
| **Total Sales**     | 638.99M |
| **Gross Profit**    | 192.90M |
| **EBITDA**          | 112.01M |
| **PAT**             | 85.54M  |
| **Count of SKU ID** | 2310    |


#### 1.	YoY Change for Following (Sales, Gross Profit, EBITDA, PAT):
#####	**Actual Data:**
  * Sales are relatively stable across years (≈110M–115M per year).
  * PAT values are consistent (~17M each year), with minimal fluctuation.
   
  > Insight: The business is stable but not showing significant year-on-year growth.

##### **Budget Data:**
  * Higher expected sales growth in 2023 (144.43M) compared to actual (115.28M).
  * PAT forecast peaks in 2023 (24.78M), much higher than actuals.
    
  > Insight: Budget assumed aggressive growth, but actual performance indicates the company is underperforming compared to expectations.

#### 2.	Trend of Sales with PAT and PAT%:
#####	**Actual Data:**
 * PAT% fluctuates between 10.6%–11.4%.
 * Sales are flat, around 110M–115M per year.

 > Insight: Sales stagnation combined with consistent PAT% indicates efficiency is maintained but growth opportunities are being missed.

#####  **Budget Data:**
 *	PAT% is higher, ranging from 13%–14%.
 *	Sales in budget show growth (124M in 2020 to 144M in 2023).

 > Insight: The budget expected stronger profitability ratios than achieved in actuals.

#### 3.	100% Stacked Column Chart (Sales, Gross Profit, EBITDA, PAT):
#####	**Actual Data:**
 *	Sales contribute ~64%, Gross Profit ~19%, EBITDA ~10%, PAT ~7%.
 *	Proportions are consistent across years.

 > Insight: The cost structure is stable, but low PAT contribution (<7%) indicates high operating costs.

#####	**Budget Data:**
 * Sales contribution is slightly lower (~62%), while Gross Profit is higher (~19%).
 * PAT share improves (~8.2% vs. 6.8% in actual).

 > Insight: Budget assumed higher efficiency in cost control and profitability, but actuals did not meet these efficiency levels.

#### 4.	Volume Trend by Category:
#####	**Actual Data:**
 * Top categories: Fresh Fare (70.42K), Country Fries (49.47K), Crunch Pack (29.46K).
 * Bottom categories: Cake (4.87K), Sweet Crust (2.52K).
   
 > Insight: Sales volume is heavily skewed — top 3 categories dominate while niche categories contribute very little.

##### **Budget Data:**
 * Similar dominance by top categories: Fresh Fare (61.33K), Country Fries (53.92K), Protein Pack (46.8K).
 * Lower categories have negligible contributions.

 > Insight: Budget projected slightly better distribution across categories compared to actual, but actual shows more concentration in fewer products.

#### 5.	Sales Bifurcation by Channel:
#####	**Actual Data:**
 * Leading channel: Direct Sales (171.39M).
 * Other major channels: Bulk Sales (103.3M), Culinary Services (99.12M).
 * Smaller contributors: Online Sales (2.87M), Mfg Sales (0.28M).
   
 > Insight: Heavy reliance on Direct Sales (≈30% of total). Online and Manufacturing channels are underutilized.

 ##### **Budget Data:**
  * Leading channel: Direct Sales (190.46M), followed by Culinary Services (139.12M) and Bulk Sales (110.03M).
  * Budget expected strong performance from Culinary Services and Domestic Sales.

  > Insight: Budget planned more balanced growth across channels, but actual results show greater dependency on Direct Sales than intended.



### Dashboard 2 Insights: Optimising the Business

#### 1.	Overall Gross Profit vs Volume:
*	X-axis: Volume in Metric Tons (Mt)
*	Y-axis: Gross Profit
*	Red dots: Below average performance
*	Grey dots: Around average
*	Green dot (Top-right quadrant): High volume & high profit
*	Average Benchmarks:
*	Volume: ~3,996 Mt
*	Gross Profit: ~2.99M
  > Insight: Most data points are below average in both volume and profit. Only one product (green dot) stands out as a high performer (SKU Code: 4094026673) — both in terms of gross profit and volume.

#### 2.	Gross Profit & Volume by Category:
*	**Categories like:**
Cake, Country Fries, Crunch & Munch, Fresh Fare, Frosted Fare, Frosty Veggies, Protein Pack, Sweet Crust
*	Protein Pack shows a high Gross Profit (~80M) with moderate-to-high volume (~60K Mt).

  > Insight: Protein Pack is the top category in terms of both profitability and volume sold. Country Fries, Fresh Fare, and Crunch & Munch also have moderate performances. Cake and others are underperforming (lower profit and volume).

#### 3.	Top-5 Categories by Gross Profit and Net Revenue:
*	**Top category:** Protein Pack (highest in both Net Revenue and Gross Profit)
*	**Other top categories:**	Country Fries, Crunch & Munch, Fresh Fare, Frosty Veggies

  > Insight: Protein Pack dominates in profitability and revenue. Other categories cluster near the lower end, suggesting room for improvement in both revenue and margins.



### Dashboard 3 Insights: Pareto Analysis

This dashboard analyzes the contribution of SKUs to total sales using the Pareto Principle (80/20 Rule). The analysis shows that 560 SKUs, which is approximately 13% of the total 4,207 SKUs, contribute to 80% of total sales. This confirms the classic Pareto distribution in our product portfolio.

To further enhance this analysis, I created a separate Pareto table in Excel, grouping SKUs into broader product categories. This helped identify high-performing categories for strategic focus and low-impact categories for potential optimization or rationalization.

  > Key insights:
>   * High-performing SKUs (13%) are core revenue drivers and should be prioritized in inventory, promotions, and demand planning.
>   * The remaining 87% of SKUs contribute just 20% of sales, indicating a long tail of low-impact products that require strategic review.


### Dashboard 4 Insights: - Quadrant Analysis

#### 1.	Category Contribution by Sales & Gross Profit:
*	Only one Category (Protein Pack) lies in the green quadrant (Top-right quadrant) with High Sales and High Gross Profit.  
*	All other categories are at grey quadrant (Bottom-left quadrant) with Low Sales & Low Gross Profit.

  > Insight: Protein Pack dominates in Sales and Gross Profit. Other categories cluster in Low Sales & Low Gross Profit quadrant, suggesting room for improvement in both sales and gross profit.

#### 2.	Location Contribution by Sales & Gross Profit:
*	Uttar Pradesh and Maharashtra lie in the green quadrant (Top-right quadrant) with High Sales and High Gross Profit.  
*	Rajasthan lies in blue quadrant (Top-left quadrant) with Low Sales and High Gross Profit.
*	Gujarat, Karnataka, Calcutta and Tamil Nadu lie in the grey quadrant (Bottom-left quadrant)
with Low Sales & Low Gross Profit.

  > Insight: Uttar Pradesh generates the highest sales and gross profit returns compared to all other locations. Maharashtra follows, also yielding good returns in terms of sales and gross profit.


### Dashboard 5 Mekko Chart

Mekko Chart is a type of data visualization that combines elements of bar charts and stacked bar charts to show data distribution across multiple dimensions. 

To enhance this analysis, I created a separate Mekko table in Excel, grouping SKUs same as Pareto Analysis. This helped identify high-performing categories for strategic focus and low-impact categories for potential optimization or rationalization.

* i- Top 100 customers = ~45% of total sales → high customer concentration.
* ii- Mid-tier customers (101–600) = major growth zone → strong potential.
* iii- Long-tail customers (601–2000) contribute very little → upsell opportunity.
* iv- Few product categories dominate share → product concentration risk.
* v- Smaller categories highly fragmented → candidates for optimization.


### Dashboard 6 Insights: - Financial Analysis of Business Drivers

#### 1. Sales Performance Analysis
*	Actual Sales are lower than Budget in all 5 years.
*	The gap is largest in 2023 (-20.18%), indicating a challenging year—possibly due to demand slowdown or pricing pressure.
*	A slight recovery appears in 2024, with the variance improving from -20.18% to -13.55%.
*	Despite fluctuations, the business has not achieved budgeted sales even once in the 5-year period.

#### 2. EBITDA Performance Analysis
*	EBITDA performance shows consistent underachievement, even more severe than sales.
*	Variance ranges between -15% to -24%, showing severe margin pressure.
*	2023 shows the worst EBITDA drop (-24.10%), coinciding with the worst sales year.
*	The inability to convert revenue into profit suggests cost inefficiencies or reduced-price realization.

#### 3. Volume (MT) Performance Analysis
*	Volume performance also consistently misses budget expectations.
*	Major decline in 2023 with -13.49% variance — aligning with the weakest Sales and EBITDA performance.
*	2024 shows improvement but still significantly below target (-12.73%).

#### 4. PAT (Profit After Tax) Analysis
*	PAT shows the most severe negative variances among all metrics.
*	Every year performs significantly below budget, ranging from -23% to -33%.
*	Worst year: 2023 (-33.59%), when Sales, Volume, and EBITDA were also at their lowest.
*	2024 shows slight recovery but still far from target (-31.19%).


### Dashboard 7 Insights: - Financial Analysis of Cost Drivers

#### 1. COGS (Cost of Goods Sold)
*	COGS exceeded budget in all years (2020–2024), indicating persistent cost overruns.
*	2023 shows the largest negative variance (-19.5%), signalling significant inefficiencies or higher raw material costs.
*	2024 variance improved to -11.7%, but still remains above budget—cost control actions are delivering results but not fully resolving the issue.

#### 2. Packaging Costs
*	Packaging costs also consistently exceed budget across all years.
*	2023 is the worst-performing year (-29.8%), indicating a major spike in packaging expenses (likely due to inflation or supply shortages).
*	2024 variance recovers slightly (-26.8%), but packaging remains a high-cost pressure area requiring strategic attention.

#### 3. Marketing Spend
*	Marketing shows the smallest variances compared to COGS & Packaging.
*	Variances remain within a -4% to -8% range (2020–2022), indicating relatively disciplined spending.
*	2023 shows a sharp overspend (-24.5%), suggesting a major campaign or unplanned expense.
*	2024 variance improves (-15.3%), but tracking and ROI evaluation need strengthening.

### Dashboard 8 Insights: - PVM Analysis

#### 1. Actual Sales Waterfall 
*	Net Change: Actual sales show a decline from Start → Finish, mainly driven by negative price effect.
*	Price Effect: Largest negative contributor (≈ –122K), indicating price reductions or lower realized prices vs prior period.
*	Mix Effect: Mix impact is almost neutral (≈ +1K), meaning product mix did not significantly help.
*	Volume Effect: Slight positive (≈ +10K) but not enough to offset price pressure.
* Overall Result: Price deterioration is the primary driver of the fall in actual sales.

#### 2. Budget Sales Waterfall 
*	Net Change: Budgeted sales show an increase, ending higher than the starting point.
*	Mix Effect: Strong positive contribution (+3M), meaning planned mix was more profitable.
*	Price Effect: Negative impact (≈ –686K), suggesting budgets assumed discounting or lower margins.
*	Volume Effect: Positive (+259K), showing expected demand growth.
*	Overall Result: Budget expects improvement due to favourable mix + higher volume, despite price pressure.

--

## 5.	Conclusion

The complete data analysis of Crunchy Corner’s Actual and Budget performance reveals a clear picture of the company’s operational and financial health. Across multiple dashboards—Financial KPIs, Business Drivers, Cost Drivers, Pareto, Quadrant, Mekko, and PVM Analysis—the findings consistently show that the business is **stable but significantly underperforming against budget expectations.**
Sales, EBITDA, PAT, and Volume all remain **below budget for five consecutive years**, with 2023 identified as the weakest year due to declining sales, lower volumes, higher COGS, and heavy price pressure. Despite this, PAT% and EBITDA% remain stable, indicating operational consistency but limited growth. Cost drivers such as COGS and Packaging repeatedly exceed budget, highlighting clear inefficiencies and rising input costs.
Customer and product concentration remain extremely high—**13% of SKUs contribute 80% of sales, and Top 100 customers contribute nearly 45% revenue**—exposing the company to dependency risks. Additionally, product mix analysis shows that only a few categories (e.g., Protein Pack, Country Fries, Fresh Fare) drive most of the profitability, while others remain underperforming.
Overall, despite a strong product portfolio and wide footprint, Crunchy Corner faces challenges in **pricing, cost management, product mix optimization, channel performance, and meeting budget expectations**. The insights from this dashboard provide clear direction for strategic and operational improvements.

--

## 6.	Future Scope

Based on the analysis and insights generated, multiple future improvement opportunities and analytical extensions can be implemented:
#### 1. Pricing Strategy Optimization
*	Conduct a detailed price elasticity study to understand customer sensitivity.
*	Use PVM analysis more frequently to evaluate monthly/quarterly price effects.
*	Introduce dynamic pricing for underperforming regions or categories.

#### 2. Cost Control & Procurement Efficiency
*	Deep-dive into COGS drivers (raw materials, logistics, wastage).
*	Re-evaluate vendor contracts and packaging procurement strategy.
*	Implement predictive cost modelling to anticipate inflation-led spikes.

#### 3. Product Portfolio Rationalization
*	Reduce or redesign long-tail products that contribute <20% of sales.
*	Focus marketing and supply chain efforts on high-performing SKUs.
*	Introduce new variants in high-growth categories (Protein Pack, Frozen Items).

#### 4. Customer Segmentation & Upselling Strategy
*	Target mid-tier customers (101–600), where strong growth opportunity exists.
*	Design loyalty programs for Top 100 customers to retain revenue base.
*	Develop data-driven CRM models for cross-selling and upselling.

#### 5. Channel Performance Improvement
*	Strengthen Online Sales and Manufacturing Sales (currently underutilized).
*	Optimize Direct Sales dependency by balancing channel mix.
*	Evaluate profitability of bulk and culinary channel segments.
  
#### 6. Forecasting and Budgeting Enhancement
*	Use machine learning forecasting models for Volume, Sales, and PAT.
*	Create rolling forecasts to adapt budget expectations to market shifts.
*	Improve variance tracking dashboards with automated alerts.
  
#### 7. Advanced Analytics Integration
*	Implement predictive churn analysis for customers.
*	Use clustering models to identify product affinity and bundle opportunities.
*	Build a profitability model at SKU × Customer × Channel level.
  
#### 8. Operational Expansion Strategy
*	Prioritize expansion in high-return states (Uttar Pradesh, Maharashtra).
*	Improve performance in low-yield locations through targeted interventions.
*	Reassess inventory levels region-wise for cost and service optimization.

--

## 🔗 Connect
Feel free to connect for collaboration, reviews, or suggestions to enhance this project further.



