# 🚕 Uber Fares Dataset Analysis – Power BI Project

## 📘 Introduction

The objective of this analysis is to explore the **Uber Fares Dataset** from Kaggle to gain meaningful insights into ride patterns, fare distribution, temporal trends, and operational performance. By using **Python for data preprocessing** and **Power BI for visualization**, this project provides a data-driven approach to understanding how Uber fares vary over time, location, and peak hours.

Through the creation of an interactive dashboard, this project enables users to:
- Analyze fare distribution across various times of the day and days of the week.
- Identify high-demand periods and potential peak hours.
- Discover temporal trends in Uber operations (hourly, daily, monthly).
- Visualize the geographic spread of ride pickups (if location data available).

The final dashboard and report offer actionable insights that could support operational optimization, pricing strategy, and customer experience improvement for ride-hailing services.

---

📂 **Main Deliverables**
- Cleaned and enhanced CSV dataset
- Power BI `.pbix` dashboard file
- Python scripts used for data cleaning and feature engineering
- Analytical report (Markdown or PowerPoint)
- Screenshots documenting key project stages
 
---

## 📊 Dataset Description

The dataset used for this project is the **Uber Fares Dataset** from Kaggle. It contains trip-level information including:

- `pickup_datetime` – Timestamp of when the ride started
- `fare_amount` – Final fare in USD
- `pickup_latitude`, `pickup_longitude` – Coordinates of the pickup point
- Additional features (engineered): `hour`, `day_of_week`, `month`, `peak_offpeak`, `fare_bin`

This data was cleaned and enhanced using Python before importing into Power BI for visualization.

---

## 🧪 Methodology

The analysis process followed these main steps:

1. **Data Cleaning** using Python (Pandas)
   - Removed missing and invalid records
   - Converted timestamps to datetime format
   - Extracted hour, day, and month from datetime
   - Created fare bins and peak/off-peak indicators

2. **Feature Engineering**
   - Added new columns to enable time-based and categorical analysis

3. **Data Visualization in Power BI**
   - Created interactive visuals to explore fare distribution, time patterns, and ride volumes

4. **Dashboard Design**
   - Used filters, slicers, tooltips, and maps (where applicable)

---

## 📁 Project Structure

Uber-Fares-PowerBI/
├── data/
│ └── cleaned_uber_fares.csv
├── scripts/
│ └── data_cleaning.py
├── dashboard/
│ └── Uber_Fares_Dashboard.pbix
├── screenshots/
│ └── data_loading.png
│ └── visuals.png
├── README.md
├── report/
│ └── Uber_Fares_Report.md or .pptx

---


---

### 5. ✅ **Visualizations**

```markdown
## 📊 Visualizations

The Power BI dashboard includes:

- Fare Distribution (histogram/fare bins)
- Average Fare by Hour of Day
- Ride Volume by Day of Week
- Fare Trend by Month
- Peak vs Off-Peak Ride Comparison
- Geographic Ride Heatmap (if coordinates available)

All visuals are interactive and support filtering by hour, month, day of week, and peak/off-peak.
```

---






