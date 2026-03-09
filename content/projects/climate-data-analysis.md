---
title: "Climate Data Analysis and Visualization Platform"
date: 2025-03-20
description: "An interactive dashboard for analyzing 40 years of regional climate data."
tags: ["Data Science", "Climate", "Visualization", "Python"]
categories: ["Research"]
summary: "Built an interactive dashboard to explore 40 years of temperature, precipitation, and extreme weather data for climate research."
ShowToc: true
---

## Overview

This project delivers an **interactive web dashboard** for exploring four decades of regional climate observations. It enables researchers to identify trends in temperature, precipitation, and extreme weather events through dynamic visualizations and statistical summaries.

## Motivation

Climate researchers often work with massive, unwieldy datasets. This tool provides an accessible interface for exploring spatial and temporal patterns without writing custom analysis scripts each time.

## Technical Approach

1. **Data Pipeline** — ETL pipeline ingests raw NOAA and ERA5 reanalysis data, cleans missing values, and stores results in a Parquet-based data lake.
2. **Statistical Analysis** — Trend detection using Mann-Kendall tests; anomaly detection relative to 1981–2010 baselines.
3. **Dashboard** — Plotly Dash application with interactive maps, time-series charts, and downloadable reports.
4. **Deployment** — Containerised with Docker; deployable to cloud or local HPC clusters.

## Key Results

| Metric | Value |
|---|---|
| Data coverage | 1980 – 2024, 1200+ stations |
| Mean temp trend (global) | +0.18 °C / decade |
| Dashboard load time | < 3 s for 10-year query |

## Technologies

- **Python** — pandas, xarray, scipy
- **Plotly Dash** — interactive visualizations
- **DuckDB / Parquet** — analytical data storage
- **Docker** — reproducible deployment

## Links

- 📂 [GitHub Repository](https://github.com/yourusername/climate-dashboard)
- 🌐 [Live Demo](#)
