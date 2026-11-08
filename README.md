# CDS303-Explainable-Clustering
# Explainable Clustering of Seoul Commercial Districts Based on Sales Patterns

**Course:** CDS 303 – Scientific Data Mining  
**Team:** G9  
**Team Members:** Hyukjoon Choi and Yujin Yang

## Project Overview

This project investigates patterns of commercial activity across Seoul's commercial districts using an explainable clustering framework. Building on our initial exploration of estimated sales data, we aim to identify groups of district–quarter observations with similar sales characteristics and explain the features that distinguish these groups.

Our analysis focuses on the composition of sales across weekdays and weekends, times of day, and customer age groups, rather than relying solely on total sales volume. Understanding these differences may provide useful context for small-business support organizations and commercial district policy planners.

## Research Question

**What distinct types of commercial districts in Seoul can be identified based on their sales patterns, and which characteristics best explain the differences among these groups?**

Because the unit of analysis is a commercial district in a particular quarter, the identified clusters will represent district–quarter profiles. The same district may belong to different clusters in different quarters.

## Current Dataset

**Dataset:** Seoul Commercial District Analysis Service — Estimated Sales by Commercial District (2025)

**Source:** [Public Data Portal](https://www.data.go.kr/data/15076355/fileData.do)

The dataset contains 85,732 records and 55 variables covering four quarters of 2025. It includes commercial district and service industry identifiers, estimated sales amounts, transaction counts, and sales breakdowns by weekday, time period, gender, and customer age group.

The original records are organized by year-quarter, commercial district, and service industry. They cover 1,577 distinct commercial districts and 62 service industry categories. The dataset contains 6,276 distinct commercial district–quarter combinations before preprocessing.

## Unit of Analysis

**Commercial district × quarter**

We plan to aggregate service industry records within each commercial district and quarter to construct the analytical dataset. This approach retains quarterly variation while allowing comparisons of sales patterns across districts.

Candidate features include weekend sales share, evening sales share, and sales shares associated with different customer age groups. The final feature set will be determined through variable selection and data quality assessment.

## Proposed Methodology

The project follows a four-stage explainable clustering framework:

1. **Data preprocessing:** Aggregate industry-level records, assess data quality, and prepare suitable analytical features.
2. **Dimensionality reduction:** Evaluate methods for reducing redundant information among the selected features.
3. **Clustering:** Identify groups of district–quarter observations with similar sales patterns.
4. **Classification for explainability:** Use the resulting cluster labels as classification targets to identify characteristics that distinguish the groups.

The current session focuses on research design, variable selection, and supplementary data planning. Clustering and classification results have not yet been produced.
