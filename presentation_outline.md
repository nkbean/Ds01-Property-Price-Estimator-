# Demo-day slides outline (ds-01-property-price-estimator)
Make `reports/presentation.pdf` from this outline **after** running the notebook (charts are in `reports/figures/`).

| Slide | Title | Content |
|---|---|---|
| 1 | The question | Real-estate agency in 4 cities; agents quote the same house lakhs apart → need a data-driven first estimate. |
| 2 | The data | 600 houses × 10 columns; biggest problem fixed: GardenArea blanks ≠ no garden (0 already means none) → median + flag. |
| 3 | Key insights | 02_price_vs_area.png, 03_price_by_location.png: one sentence each. |
| 4 | The model | Baseline area-only regression vs multiple regression; why linear regression (coefficients are easy to explain). |
| 5 | Results | RMSE ± __ lakh, R² __; residual plot 08_residuals.png; "every extra 100 sqft ≈ __ lakh". |
| 6 | Recommendation | Use as a first estimate agents adjust; limits: dataset size, missing features. |
