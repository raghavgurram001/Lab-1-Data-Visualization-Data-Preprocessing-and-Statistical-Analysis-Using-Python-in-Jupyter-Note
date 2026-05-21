# README – Weather Data Analysis Lab

## Overview
This Jupyter Notebook performs a complete exploratory data analysis (EDA) on an hourly weather dataset from Canada (2012, 8784 records). The pipeline covers:
- Data loading and inspection
- Visualization (scatter plot, box plot)
- Preprocessing (missing value imputation, outlier detection/removal using IQR, data reduction, scaling, discretization)
- Statistical analysis (central tendency, dispersion, correlation matrix)

The notebook is part of **Lab 1** for the course *MSCS 634 – Big Data Analytics* at University of the Cumberlands.

## Dataset
- **Source**: Kaggle – [Weather Data](https://www.kaggle.com/datasets/rohitgrewal/weather-data)
- **Original file**: `Project 1 - Weather Dataset.csv`
- **Variables**: Date/Time, Temp_C, Dew Point Temp_C, Rel Hum_%, Wind Speed_km/h, Visibility_km, Press_kPa, Weather (categorical)

## Notebook Contents

| Section | Description |
|---------|-------------|
| 1. Data Collection | Reads CSV, converts datetime, displays first rows |
| 2. Data Visualization | Scatter plot (Temp vs Humidity, colored by wind speed); Box plot (Temp by top 8 weather conditions) |
| 3. Preprocessing | Missing value handling (median/mode), IQR outlier detection on Visibility_km, random sampling (30%), column reduction, Min‑Max scaling, Z‑score standardization, temperature discretization (Very Cold to Hot) |
| 4. Statistical Analysis | Descriptive statistics, central tendency (mean/median/mode), dispersion (range, IQR, variance, std, CV%), correlation matrix + heatmap |

## Dependencies
Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

- Python 3.8+
- Jupyter Notebook or JupyterLab

## How to Run
1. Place the dataset `Project 1 - Weather Dataset.csv` in the same directory as the notebook (or update the file path).
2. Launch Jupyter and open the notebook.
3. Run cells sequentially (Kernel → Restart & Run All).

**Note**: The current path `/kaggle/input/...` is from a Kaggle environment. For local use, replace with your local path.

## Key Results (Brief)
- No missing values in the original dataset.
- Visibility_km had 3539 outliers (40.3%) – these are meteorologically meaningful low‑visibility events.
- Strong positive correlation (0.93) between temperature and dew point.
- Moderate negative correlations: humidity vs. visibility (-0.63), temperature vs. humidity (-0.22).
- After discretization, “Mild” (10–20°C) and “Cool” (0–10°C) dominate (54% of observations).

## File Structure
```
.
├── lab-1-weather-data-analysis.ipynb   # Main notebook
├── Project 1 - Weather Dataset.csv
└── README.md                # This file
```

## References
- Molin, S. (2021). *Hands‑On Data Analysis with Pandas*. Packt.
- Shen, S. S., & North, G. R. (2023). *Statistics and Data Visualization in Climate Science with R and Python*. Cambridge University Press.
