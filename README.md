**Sales Forecasting 2024 Project**

*This repository contains code, data, and deliverables for forecasting monthly sales of multiple products in 2024 using a hybrid modeling approach.*

---

## 📄 Project Overview

I first built a base annual sales forecast for 2024, then—where that overall model performed well—generated product-level forecasts for four SKUs (Alpha, Beta, Delta, Gamma). Our hybrid pipeline blends classical and machine‑learning techniques to optimize accuracy through:

Data Preparation & Feature Engineering (Notebooks 01_data_cleaning.ipynb, 02_feature_engineering.ipynb; with additional feature engineering steps in the modeling notebooks)

Model Training & Evaluation (Notebooks 03_model_training.ipynb, 04_holdout_2023_eval.ipynb)

2024 Forecast Generation (Notebook 05_forecast_2024.ipynb)

I incorporate XGBoost (non‑linear/promotion effects), Prophet (trend/seasonality), SARIMA (classical benchmark), and residual bias correction to produce final reconciled forecasts.

---

## 🗂️ Repository Structure

```
project-root/
├── data/                   # Raw and processed datasets
│   ├── raw/                # Original input files
│   └── processed/          # Cleaned and engineered data
├── notebooks/              # Jupyter notebooks for each step
│   ├── 01_data_cleaning.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_holdout_2023_eval.ipynb
│   └── 05_forecast_2024.ipynb
├── models/                 # Serialized model files (e.g. .pkl, .joblib)
├── powerbi/                # Power BI desktop files (.pbix) or exported assets
├── reports/                # Narrative deliverables (Markdown, PPTX, PDF)
│   └── figures/            # PNG exports of Power BI visuals and charts
├── env/                    # Environment definitions (environment.yml / requirements.txt)
├── .gitignore              # Git ignore rules
├── .gitattributes          # Git attributes & LFS configurations
├── LICENSE                 # MIT License
└── README.md               # Project introduction and instructions
```

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
   * View the live dashboard:** [Power BI Report](https://app.powerbi.com/view?r=eyJrIjoiM2JlMGRkODAtNzg0MC00NzNiLTgzYmEtMTYxZDhlNDY1MzVkIiwidCI6IjQxOTI3ZjQyLTQ2NWMtNDFmOS1iYzAwLTUxMTVjM2QzNTE3NCIsImMiOjl9) 

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




(https://app.powerbi.com/view?r=eyJrIjoiM2JlMGRkODAtNzg0MC00NzNiLTgzYmEtMTYxZDhlNDY1MzVkIiwidCI6IjQxOTI3ZjQyLTQ2NWMtNDFmOS1iYzAwLTUxMTVjM2QzNTE3NCIsImMiOjl9)
