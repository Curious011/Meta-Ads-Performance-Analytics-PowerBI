# 📐 DAX Calculations & Measures Documentation

This documentation provides the full catalog of **Data Analysis Expressions (DAX)** implemented within the **Meta Ads Performance Analytics Dashboard**. Measures are organized into functional analytical tiers: Core Funnel Volume, Interaction & Engagement, Conversion & Funnel Ratios, Financial & Budget Tracking, and Dynamic UI Parameters.

---

## 1. Core Funnel Volume Measures

These base calculation measures evaluate raw event occurrences across the 400,000 ad event transactions in `ad_events`.

### Impressions
```dax
Impressions = 
COUNTROWS(
    FILTER(
        ad_events, 
        ad_events[event_type] = "Impression"
    )
)
```
* **Purpose**: Calculates the total ad impressions delivered across Facebook and Instagram feeds and story placements.
* **Model Total**: **339,812** impressions.

---

### Clicks
```dax
Clicks = 
COUNTROWS(
    FILTER(
        ad_events, 
        ad_events[event_type] = "Click"
    )
)
```
* **Purpose**: Tracks cumulative ad click events triggering landing page redirects.
* **Model Total**: **40,079** clicks.

---

### Purchases (Conversions)
```dax
Purchases = 
COUNTROWS(
    FILTER(
        ad_events, 
        ad_events[event_type] = "Purchase"
    )
)
```
* **Purpose**: Tracks bottom-of-funnel conversion events where users completed product checkouts.
* **Model Total**: **2,031** purchases.

---

### Shares
```dax
Shares = 
COUNTROWS(
    FILTER(
        ad_events, 
        ad_events[event_type] = "Share"
    )
)
```
* **Purpose**: Quantifies organic virality and user ad amplification.
* **Model Total**: **3,000** shares.

---

### Comments
```dax
Comments = 
COUNTROWS(
    FILTER(
        ad_events, 
        ad_events[event_type] = "Comment"
    )
)
```
* **Purpose**: Measures direct user discourse and community engagement on ad creatives.
* **Model Total**: **3,065** comments.

---

## 2. Interaction & Engagement Measures

### Engagements
```dax
Engagements = [Shares] + [Clicks] + [Comments]
```
* **Purpose**: Aggregates all active user interaction events across posts to measure composite engagement volume.
* **Model Total**: **46,144** total engagements.

---

### Engagement Rate (ER)
```dax
Engagement Rate = 
DIVIDE(
    [Engagements],
    [Impressions],
    0
)
```
* **Purpose**: Evaluates creative resonance by measuring the proportion of impressions that led to active user interactions.
* **Portfolio Benchmark**: **13.58%**.

---

## 3. Conversion & Funnel Ratios

### CTR (Click-Through Rate)
```dax
CTR (Click Through Rate) = 
DIVIDE(
    [Clicks], 
    [Impressions], 
    0
)
```
* **Purpose**: Measures top-to-mid funnel creative appeal and hook effectiveness.
* **Portfolio Benchmark**: **11.79%** (11.76% Facebook vs. 11.86% Instagram).

---

### Conversion Rate (CVR)
```dax
Conversion rate = 
DIVIDE(
    [Purchases], 
    [Clicks], 
    0
)
```
* **Purpose**: Measures bottom-of-funnel traffic quality and landing page conversion efficiency (Click-to-Purchase).
* **Portfolio Benchmark**: **5.07%** (5.21% Facebook vs. 4.82% Instagram).

---

### Purchase Rate (Overall Impression-to-Purchase)
```dax
Purchase Rate = 
DIVIDE(
    [Purchases], 
    [Impressions], 
    0
)
```
* **Purpose**: End-to-end full funnel efficiency metric showing the percentage of delivered impressions resulting in a sale.
* **Portfolio Benchmark**: **0.60%** (0.61% Facebook vs. 0.57% Instagram).

---

## 4. Financial & Portfolio Budget Tracking

### Total Budget
```dax
Total Budget = 
SUM(campaigns[total_budget])
```
* **Purpose**: Tracks cumulative capital allocated across advertising campaigns.
* **Portfolio Total**: **$2,535,923.78** across 50 campaigns.

---

### Avg. Budget per Campaign
```dax
Avg. Budget per Campaign = 
AVERAGE(campaigns[total_budget])
```
* **Purpose**: Establishes baseline capital expenditure pacing per campaign initiative.
* **Portfolio Average**: **$50,718.48**.

---

### Customer Acquisition Cost (CAC) *(Derived / Calculated KPI)*
```dax
CAC = 
DIVIDE(
    [Total Budget], 
    [Purchases], 
    0
)
```
* **Purpose**: Monitors unit economics to identify high-efficiency vs. capital-draining campaigns.
* **Portfolio Average**: **$1,173.34** (ranging from **$118.18** on top seasonal campaigns up to **$6,511.53** on underperforming launches).

---

### Cost Per Click (CPC) *(Derived / Calculated KPI)*
```dax
CPC = 
DIVIDE(
    [Total Budget], 
    [Clicks], 
    0
)
```
* **Purpose**: Evaluates competitive media bidding efficiency across platform ad sets.
* **Portfolio Average**: **$63.27**.

---

## 5. Dynamic Field Parameters (`Select Dynamic Measure`)

Implemented via Power BI Field Parameters to allow interactive metric switching without canvas clutter:

```dax
Select Dynamic Measure = {
    ("Impressions", NAMEOF('ad_events'[Impressions]), 0),
    ("Clicks", NAMEOF('ad_events'[Clicks]), 1),
    ("Purchases", NAMEOF('ad_events'[Purchases]), 2),
    ("CTR", NAMEOF('ad_events'[CTR (Click Through Rate)]), 3),
    ("Conversion Rate", NAMEOF('ad_events'[Conversion rate]), 4),
    ("Engagement Rate", NAMEOF('ad_events'[Engagement Rate]), 5)
}
```
* **Functionality**: Empowers users to toggle categorical bar charts, trend lines, and heatmap matrices dynamically between volume metrics and efficiency percentages.
