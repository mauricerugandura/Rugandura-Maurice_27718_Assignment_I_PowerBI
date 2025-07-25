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

##  Tools and Technologies

- **Python (Pandas)** – For data cleaning and preparation  
- **Power BI Desktop** – For data visualization and dashboard creation  
- **GitHub** – For version control and project documentation  
- **Dataset Source**: [Uber Fares Dataset – Kaggle](https://www.kaggle.com/datasets/yasserh/uber-fares-dataset)

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

### 🔹 EDA Visualization Samples

```python
import pandas as pd
```
```python
data = pd.read_csv('uber.csv')
```
```python
data
```
![data](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/1d92ddb4328906eef3de0e9da99112ea3a18df0c/data.PNG)

```python
data.isna().sum()
```
![data is na](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/6757ff9270bb30f5a1c24d0abb57e6aa77864deb/dataisna.PNG)

```python
data.drop_duplicates
```
![data drop](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/6757ff9270bb30f5a1c24d0abb57e6aa77864deb/datadrop.PNG)

```python
data.isnull()
```
![data is null](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/6757ff9270bb30f5a1c24d0abb57e6aa77864deb/dataisnull.PNG)

```python
data_remove = data.dropna()
```
```python
data_remove
```

![data remove](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/cb936a216cde4a1e21d923348a33c0f7c831d2d5/dataremove.PNG)

```python
data.dropna(inplace=True)
```
```python
fare_amount = data['fare_amount'].mean()
print("fare_amount:", fare_amount)
```
![mean](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/59d58d8ea33fe2de6a9a98610b45e8f8ba825fb6/fareamount.PNG)

```python
data = pd.DataFrame(data)
print("mean fare_amount:", data['fare_amount'].median())
```
![Logical Data Model](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/2f78b8abdb9cecf9de87fba2b0e5405ebc5923d4/median.PNG)

```python
print("mode:", data['fare_amount'].mode())
```
![mode](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/e003998d47b5508c9ca83f6b2d9530a0171df702/mode.PNG)

```python
print("std dev of age:", data['fare_amount'].std())
```
![stddev](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/6373189725a2ef103b367d9be04fe0e1c3a5bb0d/stddev.PNG)

```python
print("25th percentile (Q1):", data['fare_amount'].quantile(0.25))
print("50th percentile (Median):", data['fare_amount'].quantile(0.5))
print("75th percentile (Q3):", data['fare_amount'].quantile(0.75))
```
![quantile](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/db72505765b5c1354dea48c543a9ca6000092f93/qualantile.PNG)

```python
range_value = data['fare_amount'].max() - data['fare_amount'].min()
print("Range of fare amount:", range_value)
```
![rangevalue](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/14c422ca6ed746befa78842bdf50efeba8d3b8a7/rangevalue.PNG)

```python
Q1 = data['fare_amount'].quantile(0.25)
Q3 = data['fare_amount'].quantile(0.75)
IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

outliers = data[(data['fare_amount'] < lower_bound) | (data['fare_amount'] > upper_bound)]
print("Outliers:\n", outliers)
```
![outlier](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/a855921ca8f5100f9a38e6a17239e00340b1dbb0/outlier.PNG)

 **Fare Distribution**
 
```python
data['fare_amount'] = pd.to_datetime(data['fare_amount'])  
data['fare_amount'].value_counts().sort_index().plot(kind='line')
plt.title('fare distrubution  ')
plt.xlabel('fare_amount')
plt.ylabel('pickup_datetime')
plt.show()
```
![fare distribution](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/5dd10a5d8f6fde08916b93e41b8091c0b5289b3a/fare%20distribution.PNG)

 **Fare Amount**
 
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(x=data['fare_amount'])
plt.show()
```

![matplotlib](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/4b986e37aca56bf2a2012aefb2ae950e2ad62096/matplotlib.PNG)

```python
import numpy as np

def haversine(lat1, lon1, lat2, lon2):
    # Convert to radians
    lat1, lon1, lat2, lon2 = map(np.radians, [lat1, lon1, lat2, lon2])
    R = 6371  # Earth radius in km
    dlat = lat2 - lat1
    dlon = lon2 - lon1
    a = np.sin(dlat/2)*2 + np.cos(lat1)*np.cos(lat2)*np.sin(dlon/2)*2
    c = 2 * np.arcsin(np.sqrt(a))
    return R * c
```
```python
data['distance_km'] = haversine(
    data['pickup_latitude'], data['pickup_longitude'],
    data['dropoff_latitude'], data['dropoff_longitude']
)
```
![distance](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/692a777a3a42f9ad12ba829148e4253810458b04/distance.PNG)

```python
data['pickup_datetime'] = pd.to_datetime(data['pickup_datetime'])
data['hour'] = data['pickup_datetime'].dt.hour  # Hour of the day (0–23)
```
  **Fare vs Distance**
  
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(x='distance_km', y='fare_amount', data=data, alpha=0.3)
plt.title('Fare Amount vs. Distance')
plt.xlabel('Distance Traveled (km)')
plt.ylabel('Fare Amount ($)')
plt.show()
```
![fare vs distance](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/40ffbf746801725c2dfcbf7995ed3a43318b3937/farevsdist.PNG)

###  Hourly Ride Trends

```python
import matplotlib.pyplot as plt

avg_fare_by_hour = data.groupby('hour')['fare_amount'].mean()

plt.plot(avg_fare_by_hour.index, avg_fare_by_hour.values)
plt.title('Average Fare by Hour of Day')
plt.xlabel('Hour of Day')
plt.ylabel('Average Fare Amount ($)')
plt.xticks(range(0, 24))
plt.grid(True)
plt.show()
```
![average fareamount](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/181351676cac5abf171cf7a0a09248f0ba8933e9/average%20fare.PNG)

```python
print(data[['fare_amount', 'distance_km', 'passenger_count']].corr())
```
![corr](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/acf81bde8ef39864599501552df87e10b51b02fe/corr.PNG)

```python
data['pickup_datetime'] = pd.to_datetime(data['pickup_datetime'])
data['hour'] = data['pickup_datetime'].dt.hour
data['day'] = data['pickup_datetime'].dt.day
data['month'] = data['pickup_datetime'].dt.month
data['day_of_week'] = data['pickup_datetime'].dt.day_name()
print(data[['pickup_datetime', 'hour', 'day', 'month', 'day_of_week']].head())
```
![pickup](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/acf81bde8ef39864599501552df87e10b51b02fe/pickup.PNG)

```python
def peak_status(hour):
    if 7 <= hour <= 9 or 16 <= hour <= 19:
        return "Peak"
    else:
        return "Off-Peak"
data['peak_status'] = data['hour'].apply(peak_status)
print(data[['hour', 'peak_status']].head(10))
```
![peakstatus](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/842140f4c351c36a268bf5f32b462553a2c7edd9/peakstatus.PNG)

```python
data['day_of_week'] = pd.Categorical(data['day_of_week'],
                                   categories=['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
 ordered=True)
```
```python
data.to_csv('uber_enhanced.csv', index=False)
print(" File 'uber_enhanced.csv' saved successfully.")
```
![message successful](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/842140f4c351c36a268bf5f32b462553a2c7edd9/successful.PNG)

---

### 🔹 Power BI Dashboard Preview

![dashboard](https://github.com/mauricerugandura/Rugandura_Maurice_Assignment_I_PowerBI/blob/6adc6e2cdb2b2c761d32f6f6fe7fbb540d9f6f4b/dashboard.PNG)

## ✅ Conclusion

This project provided valuable insights into Uber's fare trends and ride behaviors through time-based and spatial analysis. Using Python, the dataset was cleaned and enriched with additional features, and then visualized in Power BI.

Key findings include:
- Peak hours with higher fare averages (7–9 AM and 4–7 PM)
- Most rides occurring on weekdays, especially Fridays and Mondays
- Fare amounts are heavily concentrated under $20
- Monthly trends reveal potential seasonality in ride demand

These insights highlight how ride-hailing services like Uber can optimize operations, adjust pricing strategies, and better plan for high-demand periods.

The interactive Power BI dashboard enables dynamic exploration of these patterns and supports future business decisions with data-driven evidence.


## 💡 Recommendations

Based on the analysis, the following actions are recommended for Uber and similar services:

- Optimize driver allocation during peak hours and weekdays.
- Consider adjusting fare pricing dynamically based on seasonal and hourly demand.
- Use geographic data to identify high-demand pickup areas for better coverage.
- Incorporate external data (e.g., weather, traffic) for deeper insights in future analyses.

## 📫 Contact

For any questions regarding this project, feel free to contact:

**Rugandura Maurice**  

📧 mauricerugandura123@gmail.com 
🔗 GitHub: [[GitHub Link](https://github.com/mauricerugandura)]  

  Course: Introduction to Big Data Analytics
  
  Instructor: Eric Maniraguha | [LinkedIn](https://www.linkedin.com/in/ericmaniraguha/)
