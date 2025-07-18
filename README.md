# Sales_Forecasting_2024
📈 2024 Monthly Revenue Forecast (Hybrid XGBoost + SARIMA + Prophet)

**Goal:** Produce an accurate, low‑bias 2024 forecast for four SKUs (Alpha, Beta, Delta, Gamma) by combining machine‑learning and classical time‑series methods, and surface the results in a Power BI dashboard for planning and budgeting.

**Why Hybrid?** Baseline XGBoost delivered the lowest hold‑out MAE but flattened seasonal amplitude. SARIMA and Prophet preserved seasonal shape but had higher error variance. I therefore use XGBoost for level + residual correction, and inject seasonal structure from SARIMA/Prophet, yielding realistic variability with strong accuracy.

**Workflow Notebooks**
1. **Data Preparation & Feature Engineering**  
   `01_data_cleaning.ipynb` · `02_feature_engineering.ipynb` · `03_compare_revenue.ipynb`
2. **Model Training & Evaluation**  
   `04_prophet_project2.ipynb` · `05_sarima_project2.ipynb` · `06_xgboost_project2.ipynb`
3. **Forecast Generation & Hybrid Assembly**  
   `07_xgboost_forecast.ipynb` · `08_hybrid_forecasts.ipynb`

**Methods Used:**  
XGBoost (non‑linear / promotion effects) · Prophet (trend + multiple seasonalities) · SARIMA (classical benchmark) · Residual bias correction & reconciliation.

---

## 🗂️ Repository Structure

```
project-root/
├── data/                   # Raw and processed datasets
│   ├── raw/                # Original input files
│   └── processed/          # Cleaned and engineered data
├── notebooks/              # Jupyter notebooks for each step
│   ├── 01-product_sales_processing.ipynb
│   ├── 02-company_data_processing.ipynb
│   ├── 03-Compare_Revenue.ipynb
│   ├── 04-Prophet_Project2.ipynb
    ├── 05-SARIMA_Project2.ipynb
    ├── 06-XGBoost_Project2.ipynb
    ├── 07-XGBoost_Project2_Forecast.ipynb
│   └── 08-Hybrid_Forecasts.ipynb
├── models/                 # Serialized model files (e.g. .pkl, .joblib)
├── powerbi/                # Power BI desktop files (.pbix) and exported assets
├── reports/                # Narrative deliverables (Markdown)
│   └── figures/            # PNG exports of Power BI visuals and charts
├── env/                    # Environment definitions (environment.yml / requirements.txt)
├── .gitignore              # Git ignore rules
├── .gitattributes          # Git attributes & LFS configurations
├── LICENSE                 # MIT License
└── README.md               # Project introduction and instructions
```

---

## 📦 Datasets

I used two source files:

* **Company Data** (`data/raw/company_data.csv`): contained overall company revenue records. I performed initial imputation of missing (`NaN`) values here and compared its `Revenue` column against the product-level data—however, values did not align or correlate, so I did not use this dataset for final modeling.

* **Product Sales** (`data/raw/product_sales.csv`): contains revenue by month and SKU. After cleaning and imputing missing values, I used it as the sole basis for feature engineering, model fitting, and forecasting.

---

## ⚙️ Prerequisites & Setup

1. **Clone the repo**

   ```bash
   git clone https://github.com/yourusername/sales-forecasting-2024.git
   cd sales-forecasting-2024
   ```

2. **Python environment**

   * Using Conda:

     ```bash
     conda env create -f env/environment.yml
     conda activate sales-forecasting-2024
     ```
   * Or with pip:

     ```bash
     pip install -r env/requirements.txt
     ```

3. **Power BI**

   * Open `.pbix` files in the `powerbi/` folder with Power BI Desktop (version ≥ 2.XX).
   * **View the live dashboard:** [Power BI Service Link](https://app.powerbi.com/view?r=eyJrIjoiM2JlMGRkODAtNzg0MC00NzNiLTgzYmEtMTYxZDhlNDY1MzVkIiwidCI6IjQxOTI3ZjQyLTQ2NWMtNDFmOS1iYzAwLTUxMTVjM2QzNTE3NCIsImMiOjl9)

4. **Data**

   * Place raw data files in `data/raw/`. Processed CSVs will be generated in `data/processed/` by running the cleaning notebook.

---

## 🚀 Usage

1. **Run notebooks in order** (01 → 05) to reproduce data cleaning, feature engineering, model training, and forecasting.
2. **Inspect model performance** in the holdout evaluation notebook (`04_holdout_2023_eval.ipynb`).
3. **Export forecasts**: The final CSV (`Hybrid_Reconciled_Products_2024.csv`) is created in the Power BI project for visualization and further analysis.
4. **Build your Power BI report** using `.pbix` in `powerbi/`, then export summary visuals to `reports/figures/` for inclusion in `reports/`.

---

## 📑 License

This project is licensed under the **MIT License** – see [LICENSE](LICENSE) for details.

---

## 👤 Author

**Evgeny Zosimov**
Data Scientist & Analyst

Feel free to open issues or pull requests for suggestions, improvements, or bug fixes!
