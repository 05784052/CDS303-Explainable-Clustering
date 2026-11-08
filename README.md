# CDS303-Explainable-Clustering
# Explainable Clustering of Seoul Commercial Districts Based on Sales Patterns

**Course:** CDS 303 – Scientific Data Mining  
**Team:** G9  
**Team Members:** Hyukjoon Choi and Yujin Yang

## Project Overview

This project aims to identify and interpret distinct types of commercial districts in Seoul based on their sales patterns. Building on our initial exploration of Seoul's commercial district data, we plan to apply an explainable clustering framework to examine how commercial activity varies across weekdays, weekends, times of day, and customer age groups.

Rather than focusing solely on total sales volume, the proposed analysis emphasizes differences in the composition of sales. The resulting district profiles may help small-business support organizations and commercial district policy planners better understand variations in local commercial activity.

## Research Question

What distinct types of commercial districts in Seoul can be identified based on their sales patterns, and which characteristics best explain the differences among these groups?

## Current Dataset

**Dataset:** Seoul Commercial District Analysis Service — Estimated Sales by Commercial District (2025)

**Source:** [Public Data Portal](https://www.data.go.kr/data/15076355/fileData.do)

The dataset contains 85,732 observations and 55 variables covering commercial districts in Seoul during all four quarters of 2025. It includes estimated sales amounts, transaction counts, commercial district identifiers, service industry categories, and sales breakdowns by day of the week, time period, gender, and age group.

The original records are organized by year-quarter, commercial district, and service industry. We propose aggregating industry-level records into commercial district–quarter observations for clustering. This would allow us to examine sales patterns across districts while retaining quarterly variation.

## Proposed Analytical Approach

We plan to follow the four-stage explainable clustering framework:

1. **Data preprocessing:** Aggregate records, assess data quality, and prepare relevant features.
2. **Dimensionality reduction:** Examine whether correlated or redundant features can be represented more compactly.
3. **Clustering:** Identify groups of district–quarter observations with similar sales patterns.
4. **Classification for explainability:** Use the resulting cluster labels as targets to investigate which characteristics distinguish the identified groups.

The methodology and variable choices will be developed further during Session 1. No clustering or classification results are reported at this stage.
