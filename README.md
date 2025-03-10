# SEIR Beta Random Walk (SEIR-BRW) 

This repository is dedicated to the generation and validation of forecasts using the SEIR Beta Random Walk (SEIR-BRW) model. This model was primarily developed and applied during the 2024-2025 season for RespiCast, the first European respiratory diseases forecasting hub. The SEIR-BRW model has been implemented for forecasting COVID-19 hospital admissions, but can also be adapted to forecast Influenza-Like Illness (ILI) and Acute Respiratory Infection (ARI).

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [File Structure](#file-structure)
- [Usage](#usage)
  - [1. Generating Simulations](#1-generating-simulations)
  - [2. Validation and Forecast Generation](#2-validation-and-forecast-generation)
- [Configuration](#configuration)
- [License](#license)
- [Sources](#sources)

## Overview

The project includes two main stages:

1. Simulation Generation: Generating stochastic SEIR simulations with a beta parameter evolving according to a random walk.

2. Forecast Validation and Dataset Generation: Selecting the top 100 simulations based on MAPE (Mean Absolute Percentage Error) of observed data, and using these simulations to generate median forecasts and quantiles for submission.

## Prerequisites

- Python 3.7 or higher

## File Structure

- **simulation.py**: Generates stochastic SEIR simulations and stores results in simulations_data/.

- **validation.py**: Validates simulation results, computes forecast quantiles and median forecasts, creates plots, and outputs CSV files for submission.

- **population_data.csv**: Contains country populations (Country_Code, Population).

- **simulations_data/**: Folder where generated simulations are saved.



## Usage

### 1. Generating Simulations

Run `dataset_generation.py` to download snapshot files, calculate revision metrics like revision status and data age, and save the processed dataset.

Run `simulation.py`: simulations will be saved in the `simulations_data/` folder.

### 2. Validation and Forecast Generation

After simulations are generated, run the `validation.py` script to:

- Select the top 100 simulations based on MAPE.

- Compute median forecasts and quantiles.

- Generate forecast plots and CSV files for submission to RespiCast.

CSV output files follow this naming convention:

```bash
YYYY-MM-DD-ISI-SEIR_BRW_COVID_{country}.csv
```


## License

## Sources

- **RespiCast:** [European respiratory diseases forecasting hub](https://github.com/european-modelling-hubs/RespiCast-Covid19)

- **Data Source:** Hospital admissions data are provided by the [RespiCast Covid-19 repository](https://github.com/european-modelling-hubs/RespiCast-Covid19).

##

Following these instructions will allow users to replicate forecasts, and adapt the model for other respiratory diseases (ILI and ARI).
