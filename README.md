# HCMC-Real-Estate-Analysis-PowerBI
A data analysis project on Ho Chi Minh City real estate market (2019-2022) using Python and Power BI.
# 🏙️ HCMC District 7 Real Estate Market Dashboard (2019-2022)

> **Project Goal:** To transform 450,000+ raw property listings into actionable investment insights using Python and Power BI.

## 📂 Data Scope
* **Location:** District 7, Ho Chi Minh City (Vietnam).
* **Time Period:** 2019 - 2022 (Pre & Post Pandemic Analysis).
* **Volume:** ~450,000 processed listings.
* **Segments:** Analysis covers both **"For Sale"** and **"For Rent"** markets across Apartments, Houses, and Villas.

## 🛠️ Technical Implementation (What I Did)

### 1. Data Preparation & Cleaning (Python & Power Query)
* **Outlier Treatment:** Detected and handled extreme outliers in `Area` (e.g., removing entries > 500m² for standard apartments) and `Price` columns using histogram distribution analysis.
* **Type Conversion:** Standardized `Lat`/`Lng` coordinates and `Area` measurements to Decimal Number format for accurate geospatial mapping.
* **Category Split:** Separated mixed datasets to distinguish between "Sale" (Billions VND) and "Rent" (Millions VND) workflows.

### 2. Data Modeling (DAX Measures)
Instead of using implicit averages, I built robust DAX measures to ensure calculation accuracy:
* **Market Volume:** `Total Listings = COUNTROWS('Table')`
* **Sale Price Logic:** Used `CALCULATE` and `FILTER` to isolate "Sale" listings, calculating accurate `Avg Sale Unit Price` without rental data interference.
* **Dynamic Analysis:** Implemented Time Intelligence logic to analyze trends over the 4-year period.

### 3. Advanced Visualization & UX Design
* **Geospatial Analysis:** Built a **Density Map** (filtered to Top N high-value listings) to identify premium pricing clusters in specific Wards.
* **Custom Tooltips (Hover-to-Reveal):** Designed a custom report page tooltip. Hovering over any map point dynamically retrieves and renders the property's **image** and key stats (Price, Area, Project Name).
* **Price Segmentation:** Created custom **Bins** (step: 1B VND) to correct X-axis skewness, visualizing the "Bell Curve" of market supply.

## 📊 Key Metrics
The dashboard tracks the following KPIs to assist investors:
* **Total Listings:** Supply trend monitoring.
* **Avg Sale Unit Price (Mil/m²):** Benchmark for property valuation.
* **Avg Rent Price:** Indicator for potential rental yield.

## 📸 Dashboard Preview

### Page 1: Market Overview (Executive View)
*Trends over time and key KPI summary.*
![Page 1 – Market Overview](images/page_1.png)


### Page 2: Location & Price Analysis (Investor View)
*Geospatial heatmaps and price-vs-area scatter plots.*
![Page 2 – Location & Price Analysis](images/page_2.png)


### Page 3: Product Deep Dive (Buyer View)
*Project-level dominance (Tree Map) and Price Range distribution.*
![Page 3 – Product Deep Dive](images/page_3.png)

## 🚀 How to Run
1.  **Clone the Repo:** Download the repository to your local machine.
2.  **Open File:** Double-click `HCMC_Real_Estate_Analysis.pbix`.
3.  **Interact:**
    * Hover over map points on Page 2 to see the **Custom Tooltip** feature.
    * Use the Slicers on the left to filter by `Ward` or `Category`.

---
*Created with ❤️ using Power BI & Python*
