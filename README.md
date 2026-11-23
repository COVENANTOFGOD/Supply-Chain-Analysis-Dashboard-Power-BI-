# Supply Chain Analysis Dashboard (Power Bi)

📌 Project Overview

An interactive, executive-level Supply Chain Analysis Dashboard designed to monitor and optimize Brands end-to-end operations—from supplier lead times and warehouse inventory to third-party logistics (3PL) delays and multi-platform retail revenue.

This dashboard empowers supply chain managers and business stakeholders to quickly identify bottlenecks, evaluate carrier performance, and track profitability across years.

# 🗄️ Data Architecture & Modeling

Behind the scenes, this report is powered by a Galaxy Schema (Fact Constellation) designed in Power BI to seamlessly connect multi-stage supply chain processes without creating circular dependencies or many-to-many bottlenecks.

Dimension Tables (dim_)

dim_date: Central calendar table enabling time-intelligence comparisons across 2023 and 2024.

dim_product: Product hierarchy including category, and minimum order/inventory thresholds and others.

dim_customer: Customer segmentation detailing sales channels (channel_type), geography (country), and annual volume and others.

dim_supplier: Vendor master data tracking supplier names, keys, and tier classifications (tier) and other.

dim_facility: Manufacturing and warehouse locations with geographic attributes and annual_capacity.

Fact Tables (fact_)

fact_procurement: Tracks raw material sourcing, supplier lead times, and vendor quality_score etc.

fact_production: Monitors manufacturing output, defective_units, and defect_rate_pct by facility etc.

fact_inventory: Captures stock levels across facilities and products over time etc.

fact_shipment: Logs logistics movement, delivery dates, and specific delay_reason codes etc.

fact_sales: Records retail transactions, revenue, discounts (discount_amount), and platform performance etc.

All relationships follow strict one-to-many (1:*) single-directional filtering from dimension tables down to fact tables, ensuring fast DAX query execution and accurate cross-filtering across the entire dashboard.
<img width="1365" height="767" alt="Screenshot 2026-11-22 183657" src="https://github.com/user-attachments/assets/093b777c-717b-496e-b124-162c50bee1b4" />


🎯 Key Business Objectives

Financial Visibility: Track Gross Revenue, Net Revenue, Sales Costs, and Profit Margins across fiscal years and retail channels.

Inventory Optimization: Monitor stock distribution across product lines (Smartphones, Wearables, Tablets, TVs, and Home Appliances) to prevent overstocking or stockouts.

Supplier & Logistics Evaluation: Benchmark supplier lead times and identify shipping carriers contributing to delivery delays.

Order Fulfillment Tracking: Measure overall operational efficiency through the Perfect Order Rate.
<img width="1082" height="603" alt="Screenshot 2026-11-23 055454" src="https://github.com/user-attachments/assets/08af64ef-b31c-41f2-a45a-5b6192910537" />


📊 Key Metrics & Insights

1. Financial Performance

Gross Revenue: $187M ($89M in 2023 | $88M in 2024)

Net Revenue: $177M

Total Profit: $49M (with a 27% Profit Margin against $78M in sales costs)

Top Revenue Channels: Third-party marketplaces lead sales, with Amazon Inc. ($37M), Flipkart ($36M), and Best Buy ($36M) outpacing Samsung Direct Store ($32M).

2. Supply Chain & Fulfillment

Order & Inventory Flow: 129K Ordered Quantity | 160K Inventory Quantity | 187K Delivered Quantity.

Perfect Order Rate: Currently at 75%, highlighting a 25% gap caused by transit delays or fulfillment discrepancies.

Supplier Lead Times: Core component manufacturers (TSMC, SK Hynix, Sony, BOE) average a 12-day lead time, while regional branches in Samsung India and Samsung Vietnam operate faster at 9 days.
<img width="891" height="198" alt="image" src="https://github.com/user-attachments/assets/d6d68097-0f16-4c5b-9768-6f9faedb9e0a" />

3. Bottlenecks & Risk Areas

Carrier Delays: Sea and express freight delays are heavily concentrated among top carriers, led by Maersk Line (87 delayed days), DHL Express (66 days), and DB Schenker (65 days).

Inventory Concentration: Stock is heavily weighted toward flagship mobile devices—Galaxy S24 Ultra (25K units) and Galaxy Buds2 Pro (22K units)—while bulky home appliances maintain lean stock (3K units).

🛠️ Features & Functionality

Dynamic Slicers: Filter the entire dashboard seamlessly by Supplier, Product, and Platform, complete with a one-click "Clear all slicers" reset button.
<img width="540" height="42" alt="image" src="https://github.com/user-attachments/assets/dbcb7639-b92a-4bfa-830a-34f64f823ef8" />


💡 Strategic Recommendations

Renegotiate Carrier SLAs: Address the 87-day delay bottleneck with Maersk Line and redistribute volume toward higher-performing logistics partners like Kuehne+Nagel (51 days) to boost the Perfect Order Rate above 85%.

Boost Direct-to-Consumer (D2C) Sales: Introduce exclusive bundles or loyalty perks on the Samsung Direct Store ($32M) to capture higher margins currently going to third-party platforms.

Replicate Regional Supplier Efficiency: Audit the workflows at Samsung India and Samsung Vietnam (9-day lead times) to see if their processes can be applied to shorten the 12-day lead times of external vendors.

<img width="1082" height="603" alt="Screenshot 2026-11-23 055454" src="https://github.com/user-attachments/assets/156c5b66-1b05-4715-b08d-cd03cff8b8c1" />


