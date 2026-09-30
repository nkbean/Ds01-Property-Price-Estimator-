# Property Price Estimator

**Team:** _add names_, _add names_, _add names_
**Brief:** DS-01 (Foundation)  ·  **Dataset:** Course dataset `house_price_data.csv`, 600 houses × 10 columns

## The question
A real-estate agency in Dhaka, Chattogram, Sylhet and Rajshahi prices listings by hand, and two agents often quote the same house lakhs apart. **Given a house's size, rooms, age, location and distance from the city, what should its asking price be, and which factors move the price most?** Target: `Price_Lakh`. Success metric: **RMSE in lakh** (with MAE and R²), because it is in the price's own unit and punishes big pricing mistakes.

## Key results
- Baseline (area only): R² __, RMSE ± __ lakh _✍️ fill in after running the notebook_
- Multiple regression: R² __, RMSE ± __ lakh
- Every extra 100 sqft adds about __ lakh; biggest price drivers: __, __, __
- Worst predictions: __


## Approach
1. **Cleaning:** GardenArea (30 missing) filled with the training median plus a missing-flag, because 0 already means "no garden"; DistanceToCity (20 missing) filled with the median of the same city; Location one-hot encoded; HouseID excluded.
2. **EDA:** 7 charts (price distribution, price vs area, price by location, distance, age, bedrooms, correlation heatmap), each with a written insight.
3. **Model:** 80/20 split with `random_state=42` before any fill values are learned; baseline = linear regression on area only; improved = multiple linear regression on all features; evaluated with R²/MAE/RMSE, residual plot, worst-5 error analysis and coefficient interpretation; decision tree and a price calculator as stretch goals.

## How to run
```bash
pip install -r requirements.txt
jupyter notebook notebooks/analysis.ipynb
```
Open `notebooks/analysis.ipynb` and choose **Run All** (Kernel → Restart & Run All). The notebook reads `data/house_price_data.csv` and saves the charts to `reports/figures/`.

> ⚠️ Put the course file in `data/` before running (it is not included yet).

**Google Colab:** open the notebook in Colab and choose Runtime → Run all; a **Choose Files** button appears, so upload `data/house_price_data.csv`.

## Repository structure
```
ds-01-property-price-estimator/
├── README.md
├── data/
│   └── house_price_data.csv
├── notebooks/
│   └── analysis.ipynb      # full notebook, outputs visible
├── reports/
│   ├── figures/            # key charts saved with plt.savefig()
│   └── presentation.pdf    # demo-day slides
└── requirements.txt
```

## Limitations
- 600 houses from a course dataset (may be synthetic); not real market transactions.
- No data on floor, condition, legal papers or road access.
- A linear model assumes each factor adds a fixed amount of price.

## AI usage
Claude (Anthropic) was used as an assistant to draft notebook code, chart code and documentation text, and to suggest checks (for example data-quality and leakage checks). Every team member re-ran the notebook, checked each result against the outputs, and can explain every cell and decision in their own words. The team is responsible for the final content.
