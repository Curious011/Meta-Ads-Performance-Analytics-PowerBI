# 📊 Meta Ads End-to-End Performance Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures_&_Formulas-00758F?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Marketing_Analytics-2ea44f?style=for-the-badge)

An interactive, enterprise-grade **Power BI Marketing Analytics & Media Buying Intelligence Dashboard** engineered to evaluate cross-platform advertising efficiency, diagnose full-funnel conversion leakage, and optimize capital allocation across **400,000 ad events**, **50 multi-channel campaigns**, and **$2.54M in total ad spend** across Meta platforms (**Facebook & Instagram**).

---

## 📌 Business Problem & Objectives

### The Business Context
In cross-platform digital advertising operations, performance marketing teams face a constant strategic challenge: **maximizing purchase conversion efficiency while mitigating ad spend waste and delivery leakage**. Without centralized business intelligence, media buyers and marketing executives face significant operational blind spots:

1. **Cross-Platform Format Misalignment**: Applying uniform creative formats across Facebook and Instagram feeds without recognizing platform-specific user consumption behaviors.
2. **Pacing Inefficiencies & Lack of Dayparting**: Serving ad impressions evenly 24/7, failing to align ad spend with peak high-intent purchasing hours.
3. **Unit Economic Bleed**: Lacking real-time visibility into campaign-level CAC variance, allowing underperforming campaigns to drain hundreds of thousands of dollars in capital.

### The Analytical Solution
This Power BI reporting system was engineered to deliver actionable, data-driven answers across two core analytical levels:
* **Facebook & Instagram Dedicated Performance Pages**: Isolated channel views to benchmark click-through rates (CTR), engagement rates (ER), and conversion rates (CVR) side-by-side.
* **Interactive Dayparting & Calendar Tooltip Engine**: Hourly area distribution charts and a custom **Calendar Heatmap Matrix** equipped with dynamic report-page hover tooltips for granular daily KPI audits.
* **Dynamic Parameter Switching**: Integrated **Field Parameters** (`Select Dynamic Measure`) enabling users to toggle charts dynamically between volume counts (Impressions, Clicks, Purchases) and efficiency ratios (CTR, CVR, Engagement Rate) without visual clutter.

---

## 🖼️ Dashboard Preview

| Facebook Performance Page | Instagram Performance Page |
| :---: | :---: |
| ![Facebook Page](assets/facebook_view.png) | ![Instagram Page](assets/instagram_view.png) |

| Calendar Heatmap with Custom Hover Tooltip | Star Schema Data Model Architecture |
| :---: | :---: |
| ![Calendar Tooltip](assets/calendar_tooltip.png) | ![Data Model](assets/data_model.png) |

---

## 📈 Key Performance Indicators (KPI Summary)

### 1. Overall Portfolio Scale
| Metric | Measure Name | Portfolio Total | Facebook | Instagram | Variance / Channel Insight |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Total Ad Events** | `ad_events (Rows)` | **400,000** | ~254,000 | ~146,000 | 63.5% FB share |
| **Delivered Impressions** | `[Impressions]` | **339,812** | **215,972** (63.6%) | **123,840** (36.4%) | High volume channel: FB |
| **Total Clicks** | `[Clicks]` | **40,079** | **25,389** | **14,690** | 11.79% blended CTR |
| **Click-Through Rate (CTR)** | `[CTR (Click Through Rate)]` | **11.79%** | **11.76%** | **11.86%** | **Instagram +0.10% higher CTR** |
| **Total Engagements** | `[Engagements]` | **46,144** | 29,353 | 16,791 | Shares + Clicks + Comments |
| **Engagement Rate (ER)** | `[Engagement Rate]` | **13.58%** | 13.59% | 13.56% | Balanced engagement |
| **Completed Purchases** | `[Purchases]` | **2,031** | **1,323** (65.1%) | **708** (34.9%) | **Facebook drives 65% of sales** |
| **Conversion Rate (CVR)** | `[Conversion rate]` | **5.07%** | **5.21%** | **4.82%** | **Facebook +8.1% more efficient** |
| **Total Ad Budget** | `[Total Budget]` | **$2,535,923.78** | — | — | 50 active campaigns |
| **Blended CAC** | *Total Budget / Purchases* | **$1,248.61** | — | — | $63.27 Cost Per Click |

---

## 🔍 Deep Analytical Insights

### 1. Platform-Specific Creative Affinities (Stories vs. Carousels)
* **The Finding**: While Instagram generated higher click interest (+0.10% CTR), Facebook dominated bottom-of-funnel sales conversion (5.21% vs 4.82% CVR).
* **Format Divergence**:
  * **On Facebook**, **Stories** was the highest-converting format (**5.52% CVR**, 464 purchases), followed by **Video** (**5.22% CVR**, 284 purchases).
  * **On Instagram**, **Carousel** ads delivered the highest conversion rate (**5.23% CVR**, 238 purchases), outperforming Stories (5.00% CVR).
  * Across **both platforms**, standard **Static Images** produced the lowest conversion efficiency (4.91% on FB, 4.35% on IG).
* **Strategic Recommendation**: Stop syndicating identical creatives across platforms. Shift Instagram creative budget toward multi-slide Carousels and concentrate Facebook production on vertical Story/Reel experiences.

---

### 2. Flat 24/7 Pacing vs. 55% Fluctuations in Buying Intent (Dayparting)
* **The Finding**: Ad impressions were delivered uniformly 24/7 without time-based pacing (~14,100 impressions delivered every single hour; ~85,000 impressions in Morning, Afternoon, Evening, and Night).
* **The Inefficiency**:
  * **Peak Purchase Hours**: Early morning at **7:00 AM (6.49% CVR, 107 purchases)** and late night at **12:00 AM Midnight (6.01% CVR, 103 purchases)**.
  * **Trough Hours**: Midday at **12:00 PM (4.39% CVR, 76 purchases)** and evening at **8:00 PM (4.17% CVR, 72 purchases)**.
* **Strategic Recommendation**: Configure **ad dayparting / automated bid scheduling** to reduce bid caps by 20–30% during low-converting afternoon and dinner browsing periods, scaling budgets during morning and night checkout windows to capture up to 55% higher conversion efficiency.

---

### 3. Extreme Campaign Unit Economic Dispersion (55x CAC Spread)
* **The Finding**: Across 50 evaluated campaigns, Customer Acquisition Cost (CAC) ranged from a low of **$118.18** up to **$6,511.53**—a **55x variance**.
  * **Top Performers**: Focused seasonal campaigns (e.g., `Campaign_42_Summer` at **$118 CAC** / $4.96 CPC and `Campaign_29_Winter` at **$341 CAC** / $13.88 CPC).
  * **Underperformers**: Broad launch and general awareness initiatives (e.g., `Campaign_35_Launch` at **$6,511 CAC** / $359.93 CPC and `Campaign_50_Summer` at **$5,909 CAC** / $264.10 CPC).
* **Strategic Recommendation**: Establish an automated portfolio shutdown rule pausing any campaign exceeding **$2,000 CAC** or **$150 CPC**, immediately reallocating freed capital into top-quartile seasonal campaigns.

---

## 🛠️ Data Architecture & Modeling

The reporting model is structured as an optimized **Star Schema** to ensure high query performance and seamless cross-filtering:

```text
       ┌──────────────┐         ┌──────────────┐
       │   campaigns  │         │    users     │
       │  (Dimension) │         │ (Dimension)  │
       └──────┬───────┘         └──────┬───────┘
              │ 1                      │ 1
              │                        │
              │ *                      │ *
       ┌──────┴───────┐         ┌──────┴───────┐
       │     ads      ├─────────┤   ad_events  │
       │  (Dimension) │ 1     * │    (FACT)    │
       └──────────────┘         └──────┬───────┘
                                       │ *
                                       │
                                       │ 1
                                ┌──────┴───────┐
                                │Calendar Table│
                                │ (Dimension)  │
                                └──────────────┘
```

* **Fact Table**:
  * `ad_events` (400,000 records): Event transactions capturing timestamps, platform, user IDs, event types (`Impression`, `Click`, `Share`, `Comment`, `Purchase`), day of week, and event hour.
* **Dimension Tables**:
  * `ads` (200 records): Ad metadata including `campaign_id`, `ad_platform`, `ad_type`, `target_gender`, `target_age_group`, and `target_interests`.
  * `campaigns` (50 records): Campaign metadata, flight dates, duration in days, and total budget allocations.
  * `users` (9,841 records): User demographic data including age, age group, gender, country, location, and user interest profiles.
  * `Calendar Table`: Automated date dimension providing month names, week numbers, day names, and chronological sort keys.
* **Disconnected Utility Table**:
  * `Select Dynamic Measure`: Disconnected field parameter table supporting dynamic measure selection in dashboard visual headers.

---

## 📂 Repository Structure

```text
├── assets/
│   ├── facebook_view.png                   # Facebook Analytics Page preview
│   ├── instagram_view.png                  # Instagram Analytics Page preview
│   ├── calendar_tooltip.png                # Calendar Heatmap with Tooltip preview
│   └── data_model.png                      # Star Schema Relationship view
├── Meta_ads_analytics.pbix                 # Full interactive Power BI Desktop workbook (12.3 MB)
├── DAX_Measures.md                         # Complete catalog of DAX formulas & logic
├── .gitignore                              # Git exclusion rules for Power BI temporary files
└── README.md                               # Project documentation & insight breakdown
```

---

## 🚀 How to Open and Explore

1. Clone this repository (or download as ZIP from the green Code button above):
   ```bash
   git clone https://github.com/Curious011/Meta-Ads-Performance-Analytics-PowerBI.git
   ```
2. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
3. Open `Meta_ads_analytics.pbix`.
4. Interact with the slicers, date table filters, and dynamic measure toggle buttons!

---

## 👤 Author
* **Harsh Sharma**
* **Project**: Meta Ads End-to-End Performance Analytics
* **Tools**: Power BI, DAX, Power Query, Marketing Data Analysis
