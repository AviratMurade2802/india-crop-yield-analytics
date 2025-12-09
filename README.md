# Prediction of Agriculture Crop Yield and Production in India

This project analyzes and predicts agricultural crop yield and production patterns in India using multiple datasets covering costs, yields, varieties, and national production statistics.

---

## Project objectives

- Predict crop yield (Quintal/Hectare) for major crops across Indian states from cost and regional features.
- Analyze multi‑year trends in production, area and yield for key crops.
- Explore recommended varieties, season/duration and cultivation zones for important crops.
- Visualize national‑level agricultural production and index trends over time.

---

## Data files

- **`datafile (1).csv`** – Crop–State–Cost–Yield data  
  - Columns: Crop, State, Cost of Cultivation (A2+FL, C2) per hectare, Cost of Production (C2) per quintal, Yield (Quintal/Hectare).

- **`datafile (2).csv`** – Crop‑wise Production, Area and Yield (2006–07 to 2010–11)  
  - Wide table with Production, Area and Yield for each crop and year.

- **`datafile (3).csv`** – Crop varieties, season/duration and recommended zones  
  - Columns: Crop, Variety, Season/duration in days, Recommended Zone.

- **`datafile.csv`** – Index of agricultural production (2004‑05 = 100)  
  - Crop‑group indices (Rice, Wheat, Pulses, Coarse Cereals, Oilseeds, Fibres, All Agriculture) for 2004‑05 to 2011‑12.

- **`produce.csv`** – National production time series  
  - National production (million tonnes) for Foodgrains and key components (Rice, Wheat, Maize, etc.), by year.

---

## Notebooks

1. **`yield_model.ipynb` – Yield prediction model**  
   - Cleans `datafile (1).csv` and performs EDA (yield by crop/state, yield vs cost).  
   - Builds a preprocessing + model pipeline with one‑hot encoding for crop and state and a RandomForestRegressor for yield prediction.  
   - Evaluates performance using MAE, RMSE and \(R^2\), and inspects feature importance.

2. **`CROP_TREND.ipynb` – Crop production/area/yield trends**  
   - Reshapes `datafile (2).csv` from wide to long (crop × year × production/area/yield).  
   - Plots yield and production vs year by crop and computes average yield and growth across 2006–07 to 2010–11.

3. **`varietirs_&_Zones.ipynb` – Varieties, duration and zones**  
   - Cleans `datafile (3).csv` and analyzes number of varieties per crop and their duration in days.  
   - Explores recommended zones text to see which states are most frequently targeted for new varieties.  
   - Optionally enriches the yield dataset with per‑crop variety counts.

4. **`Macro_national_trend.ipynb` – Macro national trends**  
   - Converts `produce.csv` to long format and plots national production trends for total foodgrains, rice and wheat.  
   - Converts `datafile.csv` to long format and plots index trends (2004‑05 = 100) for Rice, Wheat, Pulses, Coarse Cereals and All Agriculture.  

---

## Tech stack

- Python, pandas, numpy  
- scikit‑learn (modeling)  
- matplotlib, seaborn (visualization)  
- VS Code + Jupyter notebooks

---

## Key outcomes

- End‑to‑end regression pipeline that predicts crop yield per hectare from cost and regional features.
- Time‑series style analysis of crop‑wise production, area and yield across multiple years.
- Integration of agronomic context (varieties, season length, recommended zones) with yield and production patterns.
- Macro‑level visualizations of India’s agricultural production and production indices to frame the problem in a national context.
