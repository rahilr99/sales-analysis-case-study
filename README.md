# Sales Data Analysis 

## Overview

This repository contains a data analysis project completed as part of a take-home assignment for data science recruitment at **23andMe**.
The task focuses on exploring timestamped sales records, identifying behavioral shifts, and deriving insights about customer demographics and purchasing patterns.

## Problem Statement

Given 50 CSV files (one for each week), each containing:

* `sale_time` – timestamp of the purchase
* `purchaser_gender` – gender of the buyer (male / female)

The goals were to:

1. Plot daily sales over all 50 weeks.
2. Detect and date any sudden change in daily sales.
3. Test whether the change is statistically significant and report its p-value.
4. Examine if the shift is related to changes in the proportion of male vs. female customers.
5. Break each day into four **dayparts** (night, morning, afternoon, evening) and determine their contribution to overall sales.

> The emphasis was on clarity of reasoning, reproducible workflow, and concise communication of results rather than optimizing for runtime or styling.

## Project Structure

```
.
├── datasets/           # 50 weekly CSV files with raw sales data
├── src/
│   └── SalesAnalysis.ipynb  # Main analysis notebook
└── README.md
```

## Approach & Methodology

* **Data ingestion**: Loaded and concatenated all weekly CSVs into a single DataFrame.
* **Data cleaning & preprocessing**: Parsed timestamps, extracted dates, dayparts, and genders.
* **Exploratory analysis**:

  * Visualized daily sales trends.
  * Identified abrupt level shifts using time-series plots.
* **Statistical testing**: Two-sample t-test to confirm significance of the observed change.
* **Gender split**: Compared male vs. female proportions before and after the shift.
* **Daypart analysis**: Calculated percentage contribution of each daypart to total sales.

## Results & Insights

* Clear step change in daily sales was observed around a specific date, confirmed by statistical testing (p-value < 0.05).
* Gender distribution did not explain the increase — proportions remained relatively stable.
* Afternoon and evening periods accounted for the largest share of sales, while overnight activity was minimal.

## Running the Notebook

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/sales-analysis-23andme.git
   cd sales-analysis-23andme
   ```
2. Install dependencies (Python ≥3.9 recommended):

   ```bash
   pip install -r requirements.txt
   ```

   > Typical packages: `pandas`, `matplotlib`, `seaborn`, `scipy`, `numpy`.
3. Launch Jupyter and open the notebook:

   ```bash
   jupyter notebook src/SalesAnalysis.ipynb
   ```

## License

This project is provided for educational and portfolio purposes only.

