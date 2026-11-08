# CDS303-Explainable-Clustering
# Explainable Clustering of Seoul Commercial Districts Based on Transaction Volume and Average Transaction Value

**Course:** CDS 303 – Scientific Data Mining  
**Team:** G9  
**Team Members:** Hyukjoon Choi and Yujin Yang

## Project Overview

This project aims to identify and explain distinct types of commercial districts in Seoul based on transaction volume and average transaction value. Using estimated sales data from 2025, we will examine differences in commercial activity and identify groups of districts with similar transaction characteristics.

Our analysis focuses on two aspects of commercial activity: how many transactions occur within a commercial district and how much is spent per transaction on average. These measures may reveal different commercial activity profiles, such as districts characterized by high transaction volumes and relatively low average transaction values or districts with fewer transactions but higher average transaction values.

We will use an explainable clustering framework to identify these profiles and investigate the characteristics that distinguish them. The findings may provide useful insights for small-business support organizations and commercial district policy planners seeking to understand differences in commercial activity across Seoul.

## Research Question

**What distinct types of Seoul's commercial districts can be identified based on transaction volume and average transaction value, and which features best explain these differences?**

## Dataset

**Dataset:** Seoul Commercial District Analysis Service — Estimated Sales by Commercial District (2025)

**Source:** [서울특별시_우리마을가게 상권분석서비스(상권-추정매출)](https://www.data.go.kr/data/15076355/fileData.do)

The dataset contains estimated sales amounts, transaction counts, commercial district identifiers, service industry classifications, and sales information categorized by day of the week, time period, gender, and customer age group.

The original data is organized by year-quarter, commercial district, and service industry. For this project, we will aggregate the records to the commercial district level for cluster analysis.

## Unit of Analysis and Key Variables

**Unit of analysis:** Commercial district × quarter  
**Study period:** 2025, Q1–Q4

Each observation will represent one commercial district in a particular quarter. This approach allows us to examine quarterly differences in commercial activity. A district may therefore belong to different clusters across quarters.

We will focus on two clustering features:

1. **Transaction volume:** The total estimated number of transactions within a commercial district during a quarter. We plan to apply a log(1 + x) transformation to reduce the influence of extremely large transaction counts.
2. **Average transaction value:** Total estimated sales divided by total estimated transaction counts for each district–quarter observation.

Both features will be standardized before clustering. Observations with zero transactions will be examined separately because their average transaction value cannot be calculated.

The log transformation will reduce differences in scale but will not eliminate the influence of district size. Accordingly, the analysis will characterize commercial activity patterns that may also reflect differences in the scale of commercial districts.

## Proposed Analytical Framework

We will follow the four-stage explainable clustering framework introduced in the assigned research papers:

1. **Data preprocessing:** Aggregate the original records, calculate average transaction value, examine data quality, and transform and standardize the selected features.
2. **Dimensionality reduction:** Evaluate whether dimensionality reduction is appropriate given the two-feature clustering design. We will avoid reducing dimensions solely to apply a technique if doing so would unnecessarily discard useful information.
3. **Clustering:** Identify groups of district–quarter observations based on transaction volume and average transaction value. The number of clusters will be selected through evaluation rather than predetermined.
4. **Classification for explainability:** Use the generated cluster labels as classification targets to identify the features that distinguish the resulting groups.

We may also examine service industry composition and sales patterns by time of day, day of the week, and customer age group to provide additional context for interpreting the clusters. These characteristics are not part of the initial two-feature clustering design.

## Expected Contribution

The project seeks to develop interpretable profiles of commercial districts based on their transaction characteristics. Rather than assuming a fixed set of district types, we will determine the number and characteristics of clusters through analysis.

The resulting profiles may help describe how commercial activity differs across Seoul's districts and quarters. Any interpretations will be based on the observed data and evaluated clustering results rather than predefined categories.
