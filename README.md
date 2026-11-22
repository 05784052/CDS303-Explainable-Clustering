# CDS303 Group 9 Final Project 2

**Research question:** What common patterns of floating population and estimated sales characterize Seoul commercial districts in 2025 Q1?

This project integrates district-level floating-population and estimated-sales indicators and uses principal component analysis (PCA) to examine their main directions of variation. The analysis covers **1,572 matched Seoul commercial districts** in 2025 Q1. It is exploratory, not causal or predictive.

## Project files

- [Final project report](Final_Project_2_Report.md) — research question, audience, data preparation, PCA findings, and limitations
- [Reproducible Jupyter notebook](Final_Project_2.ipynb) — integration of the supplied district-level CSVs, preprocessing, PCA, and figures
- [Floating-population input](data/floating_population_2025Q1.csv)
- [Estimated-sales input](data/estimated_sales_2025Q1.csv)
- [Integrated analysis dataset](data/analysis_2025Q1.csv)
- [PCA component coefficients](data/pca_loadings.csv)
- [Scree plot](figures/scree.png)
- [Cumulative explained variance plot](figures/cumulative.png)
- [PC1–PC2 biplot](figures/biplot.png)

## Data sources and access

The two source datasets are from **Seoul Open Data Plaza** ([data.seoul.go.kr](https://data.seoul.go.kr/)):

1. **서울시 상권분석서비스(길단위인구-상권)** — floating population by commercial district and quarter.
2. **서울시 상권분석서비스(추정매출-상권)** — estimated sales and transaction counts by commercial district, quarter, and industry category.

To locate the original datasets, search the Korean titles on the Seoul Open Data Plaza website. The original XLSX files were supplied separately by the project team; **they are not included in this project folder**. The two CSV input files linked above are the included, already-prepared **2025 Q1 district-level summaries**. The floating-population summary contains weekday, weekend, male, and female measures. The sales summary contains estimated sales and transactions summed across industry categories within each district. The upstream extraction and aggregation from the original XLSX files are **not reproduced in the notebook**.

In the original 2025 Q1 source data, there were 1,650 floating-population districts and 1,572 estimated-sales districts; 1,572 district codes matched. The supplied floating-population CSV already contains only these 1,572 matched districts. Because both input CSVs represent 2025 Q1 and do not contain a quarter column, the notebook joins them **on `district_code` alone** using a validated one-to-one inner join. The 78 floating-population districts without a sales match are outside the integrated analysis; they are not rows deleted for missing PCA values.

## Method and key findings

The notebook checks district-code uniqueness and validates the six PCA inputs for missing, non-finite, and negative values. It excludes the district identifier from PCA, applies `log1p` to the six nonnegative indicators to reduce skewness, and standardizes them before fitting PCA. The six inputs are weekday and weekend floating population, male and female floating population, estimated sales, and estimated transactions. No categorical variables are encoded.

PC1 explains **76.47%** of the variance and PC2 explains **22.27%**; together they explain **98.74%**. The analysis retains **two components** using a project-selected 80% cumulative explained variance threshold. PC1 primarily reflects overall district activity, while PC2 contrasts sales-related indicators with floating-population indicators. These patterns support exploratory comparisons but do not establish clusters, business success, or causal relationships.

## Reproducing the analysis

Install the dependencies in [`requirements.txt`](requirements.txt), open `Final_Project_2.ipynb`, and run all cells **with the project root as the working directory**. The notebook reads the two input CSVs in `data/` and saves the three plots to `figures/`. It does not automatically regenerate every supplemental CSV, JSON, or NPZ artifact or the upstream source-data summaries. The report provides the full interpretation and limitations.
