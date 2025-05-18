# Inventory-Management-Analysis
## Project Overview
This data-driven inventory analysis evaluates stock levels, supplier performance, and warehouse efficiency to optimize supply chain operations. By analyzing key metrics—such as turnover rates, lead times, and restocking patterns—the project identifies inefficiencies (e.g., overstocked categories like Home & Garden) and opportunities (e.g., fast-moving Electronics).

## Report Preview
![Screenshot 2025-05-16 164316](https://github.com/user-attachments/assets/57f33a83-e36d-40b2-b8e9-165a3ffe94bf)
![Screenshot 2025-05-17 152833](https://github.com/user-attachments/assets/6cfb6ebc-da5a-4954-acc2-712385f66b7a)
![Screenshot 2025-05-16 164357](https://github.com/user-attachments/assets/d0380eb9-e779-41e9-9a3c-59935fbcce17)

## Data Sources
The analysis is based on a simulated inventory dataset designed to mimic real-world supply chain operations. While not sourced from an actual company, the data reflects realistic scenarios, including:

- Product Details: Categories (e.g., Electronics, Home & Garden), stock quantities, turnover rates, and pricing.
- Supplier Metrics: Lead times, reliability, and performance comparisons (e.g., fastest: SUP006 at 5.7 days).
- Warehouse Operations: Storage locations (e.g., AISLE-02-SHELF-03), utilization rates, and geographic distribution (Central Europe focus).
- Time-Based Trends: Monthly restocking patterns (peaks in February/September) and inventory aging.

Simulation Approach:
- Structured to mirror common inventory challenges (overstocking, stockouts, supplier variability).
- Includes synthetic but statistically sound KPIs (e.g., turnover rates,
  lead time averages).

Note: No real proprietary data was used. Ideal for demonstrating analytical workflows without confidentiality concerns.

## Data Cleaning & Preparation
1. Data Collection
  Source: Simulated inventory dataset (CSV/Excel) mimicking real-world business scenarios.
  Scope: Covered product details, supplier metrics, warehouse operations, and restocking logs.

2. Data Cleaning
  Issues Addressed:
  
    - Missing Values:
    Identified blank cells in critical fields (e.g., Lead Time, Stock Quantity).
    Imputed missing numerical values with medians (to avoid skew) and categorical values with mode (e.g., "Unspecified" for Category).

    - Inconsistencies:
    Standardized text fields (e.g., "Home & Garden" vs. "Home and Garden").
    Corrected numerical outliers (e.g., a Lead Time of 150 days → confirmed/replaced with 15 days).

3. Feature Engineering
  New Metrics Created:
  
    - Turnover Rate: Calculated as Total Sales / Average Inventory per category.
    - Stock Level Classification: Labeled items as High, Mid, or Low stock based on quartiles.
    - Supplier Tiering: Ranked suppliers by lead time (e.g., "Top Tier" for <7 days).

4. Data Validation
    Cross-checked summary statistics (e.g., mean, min/max) against business logic.
    Verified geographic coordinates for warehouse locations using OpenStreetMap API.

5. Final Output
   - Cleaned dataset exported to Power BI for visualization
   - Sample data preview included in the report’s Appendix.
  
     
## Data Analysis

The analysis began with the exploration of inventory-related data extracted from a supermarket chain. Using Excel and Power BI, the dataset was cleaned, filtered, and prepared to ensure accuracy in downstream analysis. The analysis aimed to uncover patterns in stock movement, highlight inefficiencies, and guide strategic decisions to improve inventory control.

Key steps included:

- Descriptive Analysis: Generated summary statistics to understand stock levels, sales performance, and product categorization.
- Inventory Turnover Analysis: Assessed how quickly inventory was being sold and replenished, which revealed performance across different product lines.
- Stockout and Overstock Detection: Visualizations were used to identify high-risk  frequently out of stock or overstocked, indicating imbalances in supply-demand alignment.
- Supplier Performance Analysis: Evaluated the efficiency and reliability of suppliers based on delivery times and frequency of delayed shipments.
- Trend and Seasonal Insights: Time-series analysis helped uncover sales and stock trends, enabling forecasting and better planning for high-demand periods.

Power BI dashboards were created to present interactive visuals highlighting key inventory metrics, supplier performance, and stock behavior across departments.

## Findings
The analysis revealed a mix of strengths and areas needing strategic improvement across the inventory system:

- Category Stocking vs. Turnover Mismatch: While stock levels are fairly balanced across categories, categories like Home & Garden and Office Supplies are overstocked relative to their low turnover rates (0.03 and 0.02 respectively), leading to inefficient use of storage space and increased holding costs.

- Efficient Mid-Stock Strategy: The majority of inventory falls into the mid-range category, which supports flexibility and mitigates both stockout and overstock risks. However, further alignment with actual sales patterns is needed to maximize efficiency.

- Strong Supplier Reliability: All listed suppliers perform better than the average lead time, with some (e.g., SUP006, SUP023) demonstrating significantly faster delivery, which can be strategically leveraged for high-demand SKUs.

- Seasonal Restocking Strategy: The restocking activity peaks in February and September, suggesting preparation for high-demand periods. Months like June and December show minimal restocking, which may require reevaluation based on actual sales cycles.

- Warehouse Optimization Potential: Aisles such as AISLE-02-SHELF-03 and AISLE-13-SHELF-01 are heavily utilized, indicating potential congestion. There’s room to redistribute slow-moving products to less-used warehouse zones to enhance operational efficiency.

- Centralized Geographic Distribution: The inventory is strategically concentrated in Central Europe, particularly in Belgium, Poland, and Germany. This clustering supports fast delivery across Western Europe but highlights a gap in Eastern European coverage, particularly in the UK and Sweden, which may impact lead times in those regions.

These findings suggest that while the inventory system is strategically designed, targeted adjustments in category management, geographic coverage, and turnover alignment will further improve cost efficiency, responsiveness, and customer satisfaction.

## Recommendations

1. Optimize Stock Levels by Category
Issue: Overstocking in slow-moving categories (e.g., Home & Garden, Office Supplies) and potential stockouts in high-turnover categories (Electronics).
Actions:

- Reduce Overstock:
    - Decrease order quantities for Home & Garden and Office Supplies (current turnover: 0.03 & 0.02).
    - Run targeted promotions/discounts to clear excess inventory.

- Increase Stock for High-Demand Items:
    - Boost safety stock for Electronics (turnover: 0.18) to prevent stockouts.
    - Implement dynamic reorder points based on real-time sales data.

2. Improve Supplier Utilization
Issue: Variability in lead times (5.7 to 11 days), with slower suppliers impacting restocking agility.
Actions:

- Prioritize Fast Suppliers for Critical Items:
    - Assign SUP006 (5.7 days) and SUP023 (6.0 days) to high-demand categories (e.g., Electronics).

- Renegotiate with Slower Suppliers:
    - Push suppliers in the 10–11 day range (e.g., SUP026) to match top performers.
    - Offer incentives (e.g., bulk orders) for faster deliveries.

3. Adjust Restocking Cycles
Issue: Restocking peaks in February & September may not align with actual demand trends.
Actions:

- Align with Sales Data:
    - Compare restocking peaks with historical sales to confirm seasonality.
    - Adjust orders for low-activity months (January, June, December) if demand exists.

- Implement Just-in-Time (JIT) for Slow-Movers:
    - Reduce bulk orders for low-turnover items; opt for smaller, frequent deliveries.

4. Enhance Warehouse Efficiency
Issue: Overutilization of specific aisles (e.g., AISLE-02-SHELF-03) and underused regions (e.g., Eastern Europe).
Actions:

- Reorganize High-Density Zones:
    - Relocate slow-moving items from congested aisles to peripheral storage.
    - Reserve prime locations for fast-selling products (e.g., Electronics).

- Expand Geographic Coverage:
    - Open smaller warehouses in Eastern Europe (e.g., Poland) to reduce lead times for underserved markets (e.g., Sweden, UK).

5. Data-Driven Monitoring & Alerts
Issue: Reactive inventory management leads to stock imbalances.
Actions:

- Automate Replenishment Triggers:
    - Set up low-stock alerts for high-turnover items.
    - Use ML forecasting (e.g., ARIMA models) to predict demand surges.

- Monthly KPI Reviews:
    - rack turnover rates, stockout frequency, and supplier lead times in dashboards.

## Limitataions
1. Simulated Dataset Constraints
Lack of Real-World Variability: The data was artificially generated, which may not fully capture unpredictable real-world factors (e.g., sudden demand spikes, supplier bankruptcies).

2. Supplier Analysis Shortcomings
- Limited Performance Factors: Lead time was the primary KPI, but other critical metrics (e.g., quality defects, order accuracy) were not evaluated.
- Static Supplier Pool: The analysis assumes supplier availability remains constant, ignoring potential disruptions (e.g., geopolitical risks, natural disasters).

3. Temporal and External Factors
- No Macroeconomic Context: Inflation, supply chain disruptions (e.g., pandemics), or competitor actions could invalidate current strategies.
- Static Seasonality: Restocking peaks (February/September) are analyzed in isolation, without testing their alignment with actual sales peaks.
