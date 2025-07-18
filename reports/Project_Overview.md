\# Project Overview



\## 1. Objective  

Briefly: build and reconcile 2024 sales forecasts.



\## 2. Data Sources  

\- Company Data (discarded after comparison)  

\- Product Sales (final modeling)



\## 3. Methods  

1\. Data cleaning \& imputation  

2\. Feature engineering  

3\. Model training (XGBoost, Prophet, SARIMA)  

4\. Residual bias correction



---



\## 5. Data Imputation  

After cleaning, I compared Company vs. Product data imputation results:



!\[Imputation comparison](figures/data\_imputation\_comparison.png)  

\*Figure: Comparison of imputed revenue values between Company Data and Product Sales.\*



---



\## 6. Initial Forecast vs. Actuals

\*\*Accuracy (MAE \& RMSE)\*\*  



&nbsp;  !\[Error metrics](figures/model\_errors.png)  

&nbsp;  \*Figure: XGBoost delivers lowest errors across all metrics.\*



\*\*Forecast Statistical Comparison\*\*  



&nbsp;  !\[Forecast distributions](figures/statistical\_comparison.png)  

&nbsp;  \*Figure: XGBoost forecasts (green box) are significantly flatter (low max and 75%, high min and 25%,very low std) compared to others.\*



\*\*Takeaway:\*\* XGB is the most accurate model but under‑captures seasonal swings. To combine accuracy with realistic variability, I proceed to a hybrid approach—using XGB as the baseline and borrowing shape from SARIMA/Prophet via residual correction.



---



\## 7. Hold‑out Model Performance  

!\[Residual distribution](figures/holdout\_performance.png)  

\*Figure: Hybrid‑SARIMA errors in 2023—the median error is +7.6 K, and 50 % of months lie within ±3.2 K (IQR), giving the smallest spread of all models.\*



---



\## 8. 2024 Forecast  

!\[Total forecast for 2024](figures/total\_forecast\_lines.png)  

\*Figure: Total‑company forecast for 2024 highlighting H1 strength and H2 softness.\*



---



\## 9. SKU‑Level Breakdown  

!\[SKU forecast breakdown](figures/sku\_small\_multiples.png)  

\*Figure: Monthly forecast lines for each SKU (Alpha, Beta, Delta, Gamma).\*



---



\## 10. Key Findings  

\- Overall model accuracy  

\- Product‑level drift adjustments



\## 11. Next Steps  

\- Integrate into Power BI dashboard  

\- Monitor performance against live data

