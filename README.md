# Strategic Market Analysis for International Expansion (Part I)

## 📄 Business Problem & Project Goal

This project tackles a core strategic challenge for a fictional Japanese holding company, "N&D.hol": selecting a new country for international expansion. The goal is to replace subjective decision-making with a rigorous, data-driven methodology.

This repository represents **Part I** of the analysis, focusing on the critical initial phases of the data science lifecycle: **Business Understanding, Data Collection, and intensive Data Preparation**. The ultimate objective of this phase is to build a single, unified, and clean dataset that will serve as the foundation for the predictive modeling and market ranking in Part II.

## ✨ Analysis Highlights & Methodology

The project's strength lies in its meticulous approach to data integration and preparation, transforming multiple raw, disconnected datasets into a reliable source for strategic analysis.

*   **Multi-Source Data Integration:** Gathered and consolidated data from over seven distinct sources, including The World Bank, OECD, WHO, and ILO, covering metrics across demographics, economics, healthcare, and business confidence.

*   **Systematic Data Cleaning:**
    *   Standardized country codes and entity names to create reliable primary keys for joining.
    *   Cleaned and harmonized temporal dimensions, filtering all datasets to a consistent period (2015-2020).
    *   Identified and removed irrelevant or redundant columns to create a focused analytical dataset.

*   **Advanced Missing Value Imputation:** Implemented a sophisticated, variable-by-variable imputation strategy, demonstrating a deep understanding of data quality challenges:
    *   For key continuous variables like **GDP and Government Spending (`imf_index`)**, missing values were imputed using a rolling average of adjacent years for the same country.
    *   Where yearly data was insufficient, a **regional imputation strategy** was developed, filling remaining `NA`s with the average value of the corresponding geographical or economic region (e.g., EU, Asia, Africa).
    *   For sparse time-series data like **Healthcare Personnel Density (`phy_index`)**, values were propagated forward and backward (`fill`) to ensure temporal consistency within each country.

*   **Feature Engineering:** Created new binary features to enrich the dataset for future modeling, such as:
    *   `opep`: Is the country an OPEC member?
    *   `kyoto`: Is the country a signatory to the Kyoto Protocol?
    *   `war`: Is the country in a recent or ongoing conflict?

## 💻 Technologies Used

*   **Language:** R
*   **Core Libraries:**
    *   **Tidyverse:** (including `dplyr` for data manipulation, `readr`, etc.)
    *   **janitor:** (for cleaning column names and initial data exploration)
*   **Environment:** RStudio with R Markdown

## 🏆 Project Outcome: A Unified Dataset for Analysis

The primary deliverable of this repository is the fully prepared dataset, `pra1.csv`. This dataset is the cornerstone for the subsequent strategic analysis and modeling.

*   **Final Dataset:** `1,408` clean records (rows) and `51` analytical variables (columns).
*   **Scope:** Covers `235` unique countries and entities from 2015 to 2020.
*   **Status:** All missing values, inconsistencies, and formatting issues from the raw datasets have been systematically addressed.

### Next Steps (Part II)

The dataset generated in this project is ready to be used in the next phase of the analysis, which will focus on:
1.  Developing a weighted scoring model.
2.  Ranking the candidate countries based on the defined business KPIs.
3.  Providing a final, data-backed expansion recommendation.

## 🚀 Getting Started

To explore the data preparation process:
1.  Clone the repository.
2.  Ensure you have R and RStudio installed.
3.  Install the necessary packages (e.g., `tidyverse`, `janitor`).
4.  Open the `.Rmd` or script file to review the step-by-step data cleaning and imputation logic.

## 👤 Author

**Antonio Barrera Mora**

*   **LinkedIn:** https://www.linkedin.com/in/anbamo/
*   **GitHub:** @Kamaranis