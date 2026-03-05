# Vitality Health Project – Diabetes Readmission Analysis

**Overview**  
The Vitality Health Project analyzes diabetic patient data to understand patterns in hospital readmissions and to stratify patients by risk using a custom **Vitality Complexity Index (VCI)**. The project combines **data cleaning, enrichment, exploratory data analysis (EDA), web scraping, and visualization** to provide actionable insights for healthcare decision-making.

---

## Features

- **Data Cleaning & Preprocessing**  
  - Handled missing values and removed irrelevant columns (e.g., `weight`).  
  - Removed expired patients to ensure accurate readmission analysis.  
  - Eliminated duplicates for a clean dataset.

- **Data Enrichment**  
  - Scraped ICD-9 code descriptions for the top 20 diagnoses using **BeautifulSoup** and **requests**.  
  - Integrated diagnosis descriptions into the main dataset.

- **Exploratory Data Analysis (EDA)**  
  - Visualized readmission trends, age distribution, demographics (race & gender), and medication impact.  
  - Examined operational metrics such as hospital stay duration, lab procedures, and emergency visits.  
  - Generated insightful plots: count plots, bar charts, scatter plots, box plots, and heatmaps.  

- **Vitality Complexity Index (VCI)**  
  - Custom risk score calculated using:  
    - **L**: Length of Stay  
    - **A**: Acuity of Admission  
    - **C**: Comorbidity Burden  
    - **E**: Emergency Visit Intensity  
  - Stratified patients into **Low, Medium, High Risk** categories.  
  - Validated risk stratification against readmission within 30 days.

---

## Technologies Used

- **Python**: Data processing, analysis, and visualization  
- **Pandas & NumPy**: Data manipulation and calculations  
- **BeautifulSoup & Requests**: Web scraping ICD-9 descriptions  
- **Matplotlib & Seaborn**: Visualizations for EDA and validation  
- **CSV**: Dataset storage and export  

---

## Data

- **Raw Dataset**: `diabetic_data.csv`  
- **Processed Dataset**:  
  - `diabetic_data_cleaned.csv` → cleaned data  
  - `diabetic_data_enriched.csv` → data with ICD-9 descriptions  
  - `diabetic_data_final_with_VCI.csv` → final dataset including VCI scores and risk categories  

> Note: ICD-9 codes and discharge disposition mappings are based on `IDs_mapping.csv` as per project specification.

---

## Project Structure

```

Vitality_Health_Project/
│
├── data/
│   ├── raw/                       # Original dataset
│   └── processed/                 # Cleaned, enriched, final datasets
│
├── reports/
│   └── figures/                   # EDA & validation plots
│
├── scripts/
│   └── data_pipeline.py           # Main Python script for cleaning, enrichment, VCI
│
├── README.md                       # Project documentation
└── requirements.txt                # Python dependencies

````

---

## Usage

1. Clone the repository:

```bash
git clone https://github.com/ShashinduMalshan/Vitality_Health_Project.git
cd Vitality_Health_Project
````

2. Install required packages:

```bash
pip install -r requirements.txt
```

3. Run the data pipeline:

```bash
python scripts/data_pipeline.py
```

4. Check `data/processed/` for the cleaned, enriched, and final dataset.
5. Visualizations are saved in `reports/figures/`.

---

## Key Insights

* Most patients are readmitted after **>30 days**, but `<30 days` readmission is strongly associated with high VCI scores.
* Age, gender, and race impact readmission patterns.
* Medication changes, especially insulin use, influence readmission probability.
* Discharge to **Skilled Nursing** vs **Home** affects readmission risk.

---

## Author

**Shasidu Malshan Fernando**

* Email: `shasidumalshan9579@gmail.com`
* LinkedIn: [`LinkedIn Profile`](https://www.linkedin.com/in/shasidumalshan/)
---

```
## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

```
