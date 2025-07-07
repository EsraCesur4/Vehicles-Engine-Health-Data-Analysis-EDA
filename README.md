![## 🔍 7  Örnek Tahminler (Sample Predictions) Modelin gerçek hayattaki tahmin gücünü göstermek amacıyla test setinden rastgele seçilen öğrenciler için tahminler yapılmıştır  Öğrenci  Gerçek Değer  (1)](https://github.com/user-attachments/assets/a7f4165c-1696-4121-b9bf-ebe3e0a86c5c)

# Automative Vehicles Engine Health Data Analysis & EDA

This project performs an in-depth Exploratory Data Analysis (EDA) on engine sensor data to uncover patterns, assess data quality, and extract meaningful insights about engine operating conditions.

## 📁 1. Dataset Overview

- **Source**: [Kaggle - Automotive Vehicles Engine Health Dataset](https://www.kaggle.com/datasets/parvmodi/automotive-vehicles-engine-health-dataset)
- **File**: `engine_data.csv`
- **Rows**: 19,535
- **Columns**: 7
- **Target Variable**: `Engine Condition` (0 = Healthy, 1 = Unhealthy)

### Features

| Feature Name         | Description                              |
|----------------------|------------------------------------------|
| Engine rpm           | Revolutions per minute                   |
| Lub oil pressure     | Lubricating oil pressure (bar)           |
| Fuel pressure        | Fuel line pressure                       |
| Coolant pressure     | Cooling system pressure                  |
| lub oil temp         | Lubricating oil temperature (°C)         |
| Coolant temp         | Coolant temperature (°C)                 |
| Engine Condition     | Binary label for engine health           |

---

## 2. Key EDA Steps

### Data Quality Check

- No missing or infinite values
- No duplicate records
- All columns correctly typed

### Descriptive Statistics

- Computed summary stats (mean, std, min, max)
- Assessed skewness and kurtosis of all numeric features

### Outlier Detection

- Used **Box Plot** and **IQR method**
- Significant outliers found in:
  - `lub oil temp` (~13.4%)
  - `Fuel pressure` & `Coolant pressure` (~5–6%)

![image](https://github.com/user-attachments/assets/5eca05d7-77e3-4db3-97e7-89721f4c1fac)

### Feature Engineering

- `rpm_category`: Categorized RPM into Low/Medium/High/Very High
- `temp_difference`: Difference between oil and coolant temps
- `pressure_ratio`: Ratio of lub oil to fuel pressure

---

## 3. Visualizations

- Histograms and violin plots

![image](https://github.com/user-attachments/assets/8d4ad139-6c2e-4c9a-a10b-1d61f5b4e0fa)

![image](https://github.com/user-attachments/assets/a46f9f90-61f1-4aea-9318-04c94a6883cc)

- Correlation heatmap

![image](https://github.com/user-attachments/assets/2b51abd3-d88d-40e7-9ae1-9faab38df212)

- Pairplots with `Engine Condition` hue
![image](https://github.com/user-attachments/assets/4267f41d-1664-42de-95ab-764f718dabc8)

- Interactive Visuals with Plotly:
  - 3D scatter plot
  ![image](https://github.com/user-attachments/assets/f1278f9b-b8f7-4ad6-bab2-953848c91bcf)

  - Parallel coordinates plot
  ![image](https://github.com/user-attachments/assets/aa352a57-b9f3-4660-a30c-c55cb60b01b9)

---

## 4. Insights

- Majority of engines (~63%) were labeled **Unhealthy**
- `Engine rpm`, `Fuel pressure`, and `lub oil temp` show significant variation between classes
- Low redundancy between features — correlation scores are generally weak

---

## 5. Tools & Technologies

- Libraries:
  - `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `plotly`, `scipy`

---

##  6. Project Structure
 engine-health-eda  
 ┣  engine_data.csv  
 ┣  engine_eda_notebook.ipynb  
 ┗  README.md  
