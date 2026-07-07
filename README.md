# Global Air Quality Data Analytics Project

A data analytics project that explores global air quality trends, applies statistical tests, and builds machine learning models to classify and predict air quality levels across major cities worldwide.

## Team Members

- Prashanth Pinniboyina - 65712996
- Rohan Raj Pampari - 44929952
- Praneeth Kumar - 87020878
- Manogna Mannala - 23921991
- Harshavardhan Babu - 74336308

## Project Overview

This project analyzes air quality data from 10 major cities across 9 countries (New York, Los Angeles, London, Beijing, Delhi, Paris, Tokyo, Sydney, São Paulo, and Cairo) to understand pollution patterns and predict air quality outcomes.

### Objectives

- Analyze global air quality data
- Perform data cleaning and exploratory data analysis (EDA)
- Apply statistical tests (T-Test, ANOVA) to validate pollution patterns
- Build machine learning models to predict air quality
- Compare model performance

## Dataset

**File:** `global_air_quality_dataset.csv`

- **Records:** 3,660 daily observations
- **Time period:** January 1, 2024 – December 31, 2024
- **Cities covered:** New York, Los Angeles, London, Beijing, Delhi, Paris, Tokyo, Sydney, São Paulo, Cairo

**Features:**
| Column | Description |
|---|---|
| Date | Date of observation |
| City / Country | Location of measurement |
| AQI | Air Quality Index |
| PM2.5 (µg/m³) | Fine particulate matter |
| PM10 (µg/m³) | Coarse particulate matter |
| NO2 (ppb) | Nitrogen dioxide |
| SO2 (ppb) | Sulfur dioxide |
| CO (ppm) | Carbon monoxide |
| O3 (ppb) | Ozone |
| Temperature (°C) | Ambient temperature |
| Humidity (%) | Relative humidity |
| Wind Speed (m/s) | Wind speed |

The dataset contains no missing values.

## Methodology

The full workflow is documented in `Global_Air_Quality_Data_Analytics_Project.ipynb`:

1. **Data Loading & Understanding** – Load the dataset and review structure, types, and summary statistics.
2. **Data Cleaning** – Check for missing values.
3. **Target Variable Creation** – Classify AQI into four categories: Good (≤50), Moderate (≤100), Unhealthy (≤200), Very Unhealthy (>200). The categories are also encoded numerically and simplified into a binary Safe (Good/Moderate) vs. Unsafe (Unhealthy/Very Unhealthy) target to address class imbalance.
4. **Exploratory Data Analysis** – Visualize AQI category distribution and correlations between pollutants via a heatmap.
5. **Model Building**
   - Train/test split (80/20, stratified)
   - Feature scaling with `StandardScaler`
   - **Logistic Regression** (class-balanced)
   - **Random Forest Classifier** (300 estimators, class-balanced)
6. **Model Evaluation** – Classification reports, accuracy scores, and confusion matrices for both models.
7. **Statistical Analysis**
   - **T-Test:** Comparing PM2.5 levels between safe and unsafe air quality groups
   - **ANOVA (F-Test):** Comparing PM2.5 levels across all four AQI categories
8. **Additional Visualization** – Boxplot of PM2.5 distribution across AQI categories.

## Key Findings

- PM2.5 and PM10 are highly correlated with AQI and are the strongest predictors of air quality.
- The dataset is imbalanced across AQI categories, which motivated converting the problem into binary classification (Safe vs. Unsafe).
- The Random Forest model outperformed Logistic Regression in predicting air quality.
- Statistical tests (T-Test and ANOVA) confirmed a significant difference in PM2.5 levels across air quality categories (p-value < 0.05).
- Statistical and machine learning results were consistent with each other.

## Repository Contents

| File | Description |
|---|---|
| `Global_Air_Quality_Data_Analytics_Project.ipynb` | Jupyter notebook containing the full analysis: data cleaning, EDA, statistical tests, and ML models |
| `global_air_quality_dataset.csv` | Raw dataset used for the analysis |
| `Presentation.pptx` | Slide deck summarizing the project, methodology, and results |

## Tech Stack

- **Language:** Python 3
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn, scipy

## How to Run

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Global_Air_Quality_Data_Analytics_Project.ipynb
   ```
4. Update the CSV file path in the notebook if needed, then run all cells.

## Conclusion

This project successfully applies data analytics techniques to identify global air pollution patterns. The combination of statistical testing and machine learning models confirms that particulate matter (PM2.5 and PM10) plays a central role in determining air quality, and demonstrates that ML models can be effectively used for air quality prediction.
