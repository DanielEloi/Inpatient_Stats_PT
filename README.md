# Trends in Hospital Inpatient Activity in Portugal

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-In%20Progress-orange)
![Focus](https://img.shields.io/badge/Focus-Pandas%20Portfolio-blue)
![Domain](https://img.shields.io/badge/Domain-Healthcare%20Analytics-teal)


## Overview

This project was defined as a personal milestone after learning pandas, both through the University of Michican's course "Introduction to Data Science in Python" (available through Coursera) and through the reading of "Python for Data Analysis", 3rd Edition (2022) by Wes McKinney (the original creator of pandas). 

The project serves both as a way to acquire proficiency with the library and to present insightful data regarding the portuguese National Health System's inpatient activity. It is a reproducible **health data analysis** project exploring monthly inpatient activity in Portuguese public hospitals, using open administrative data from the SNS Transparency Portal and the Portuguese Open Data Portal.

All data used in this project are aggregated, public, and non-identifiable, published by the Portuguese Ministry of Health through the SNS Transparency Portal and the Open Data Portal.

---

## Clinical context


In a perfect world, health care would be provided in a perfectly simmetrical fashion, covering equally all the extent of a country's territory and population. Unfortunately, a plethora of obstacles hinder the ability of health care professionals to reach citizens in need, and vice versa. One could be tempted to think that such fact might incur in poorer health outcomes for the involved citizens - mortality, morbidity, longer inpatient stay are some examples.morbi

On the other hand, the ever-increasing pressure on the urban hospital centers might also reduce the availability of prompt and ready healthcare, increasing the inpatient stays due to poorer health conditions of the patients. Or it might instead have the opposite effect - the implicit pressure to free hospital beds might have a systemic influence in shortening the number of days patients stay in the hospital.

Finally, a historical pandemic burst recently, profoundly changing all aspects of human life, healthcare included. 

This interesting multitude of conflicting factors is the backdrop for the analysis that this project shall present. How did the inpatient activity change over time in Portugal? How does it distribute throughout the country?

This project analyzes how hospital inpatient activity has evolved over time in Portugal and how it differs geographically, focusing on two key indicators:

- **Discharged patients**
- **Inpatient bed-days**

The main goal is to describe temporal trends, compare institutions, and derive simple indicators of care intensity from real-world administrative data. Hospital inpatient activity is a core dimension of health system performance, and tracking discharged patients and bed-days helps describe variation in demand and intensity of care across hospitals and across time.

### Research questions

This project is built around the following questions:

- How has the number of discharged patients evolved over time?
- How has the number of inpatient bed-days changed over time?
- Which hospitals show the highest inpatient activity volume?
- How does care intensity, measured as bed-days per discharged patient, vary across institutions and over time?

---

## Technical context

This project was designed also as a potential portfolio element and as a technical challenge for the author; it is intended to showcase:
- real-world data cleaning and transformation,
- reproducible analysis with public datasets,
- healthcare domain understanding,
- strong working knowledge of `pandas` for tabular data analysis.

In more concrete terms, this is a **pandas first** portfolio project. The analysis is designed to demonstrate hands-on proficiency in common real-world tabular workflows, including:
- `read_csv`
- column cleaning and renaming
- type conversion
- `to_datetime`
- filtering and subsetting
- `groupby`
- `agg`
- `transform`
- creation of derived indicators
- exporting outputs

It is also the first project of the author featuring the use of 
- Jupyter Notebooks (integrated into VS Code)
- matplotlib

---

## Data source

This project uses the **Hospital Inpatient Activity** dataset, available through:

- [SNS Transparency Portal](https://transparencia.sns.gov.pt/explore/dataset/atividade-de-internamento-hospitalar/?flg=en-us)
- [Portuguese Open Data Portal](https://dados.gov.pt/en/)

The dataset monitors the monthly evolution of:
- the number of discharged patients, and
- the number of inpatient bed-days,
by hospital institution and by specialty type (medical, surgical and other).

### Definitions used in the dataset

- **Discharged patients**: patients discharged from hospital during the reference period, excluding internal transfers.
- **Inpatient bed-days**: the total number of hospital days used by patients whose stay exceeded 24 hours, excluding the day of discharge.

---

## Methodology

1. **Choose a source**: dados.gov.pt was picked. Downloaded the CSV file at https://dados.gov.pt/pages/datasets/atividade-de-internamento-hospitalar-1
2. **Study the source file**: it is a simple semicolon-separated CSV file, with discharges and inpatient days discriminated by month, by institution and by specialty type. Each row also informs about the institution's region and geographical coordinates.
3. **Import the raw data, and standardize column names and data types**.
4. **Plan the outcomes**: To increase efficiency during coding and to make the project as informative as possible, several presenting formats were brainstormed; the selected ones are listed in "planned outputs".
5. **Investigate missing and duplicate data.** 
6. **Build dataframes with the necessary values for the planned outputs**. 
7. **Export the values into the planned outputs**.

---

## Planned outputs
- Figure 1: one subplot for each region, showing the evolution of the number of discharges (y axis) throughout the months (x axis). A fill-between pattern will be used to also show the maximum number of discharges achieved for each month throughout the years in the region.
- Figure 2: a figure equivalent to figure 1, but plotting the number of inpatient days.
- Figure 3: one global figure plotting the four quarters of a year (x axis) and the minimum, average and maximum number of discharges achieved throughout all years in the whole country; the discharges will be separated by specialties (Medical, surgical and other).
- Figure 4: a figure equivalent to figure 4, but plotting the number of inpatient days.

- Table: 

| Indicator                                                          | Value    |
|--|--|
|Total surgical discharges sum (entire period)                       | |
|Total medical discharges sum (entire period)                        | |
|Total other discharges sum (entire period)                          | |
|Total surgical bed days sum (entire period)                         | |
|Total medical bed days sum (entire period)                          | |
|Total other bed days sum (entire period)                            | |
|Surgical bed days per discharge                                     | |
|Medical bed days per discharge                                      | |
|Other bed days per discharge                                        | |
|Percentage change between the first and the last year in discharges | |
|Percentage change between the first and the last year in bed days   | |
|Coefficient of variation (standard dev / mean) of monthly bed days | |

---

## Repository structure

```bash
hospital-inpatient-activity-portugal/
├── README.md
├── notebooks/
│   ├── 01_data_import_and_cleaning.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   └── 03_final_visualizations.ipynb
├── data/
│   ├── raw/
│   │   └── hospital_inpatient_activity.csv
│   └── processed/
│       └── 01_inpatient_activity_clean.parquet
│       └── 02_fig1_data.parquet
│       └── 02_fig2_data.parquet
│       └── 02_fig3_data.parquet
│       └── 02_final_table_data.parquet
│       └── 02_coef_var_data.parquet
├── figures/
└── requirements.txt
```

> Some files (notebooks, processed data, figures) are still being created as the project evolves.

---

## Results preview

The final version of the project will include selected the figures and tables in this section.

> Add exported charts here once the analysis is complete.

---

## Author
**Daniel M. Eloi, MD** — Family Physician transitioning to Clinical Data Science  
📍 Aveiro, Portugal | [LinkedIn](https://www.linkedin.com/in/daniel-e-55b439b6/) | [GitHub](https://github.com/DanielEloi)
