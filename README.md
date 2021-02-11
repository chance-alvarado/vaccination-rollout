# vaccination_rollout

Forecasting bulk and stratified vaccination numbers under a phased rollout approach

**View a copy of the rendered notebook with *[nbviewer](https://nbviewer.jupyter.org/github/chance-alvarado/vaccination-rollout/blob/main/vaccination_rollout.ipynb)* or directly on [GitHub](https://github.com/chance-alvarado/vaccination-rollout/blob/main/vaccination_rollout.ipynb).**

---

[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

## Introduction

The COVID-19 pandemic and subsequent global rush for vaccination have placed healthcare providers into a once-in-a-lifetime situation of mass public vaccination. With limited availability and phased distribution, its is unclear when an acceptable proportion of the population will be vaccinated. The following notebook aims to generalize [The Center for Disease Control's](https://www.cdc.gov/coronavirus/2019-ncov/vaccines/recommendations.html) vaccine rollout guidelines and make predictions for a specified population (default being the state of Ohio).

### This notebook operates under the following assumptions

- Some proportion of the population will be ineligible to vaccinate. For example, children are currently unable to receive a COVID-19 vaccine. 

- Some proportion of the population will refuse the vaccine. These individuals are distributed uniformly across all groups.

- Vaccinations are administered at a constant rate daily. These rates are distributed in phases begining on some specified date.

- Individuals are stratified into mutually exclusive groups where they are teired by priority. The default is age but this need not be the case.

- Some proportion of the daily available doses are reserved for the highest priority group. Remaining daily doses 'trickle down'.

- The remaining available doses are uniformly distributed among remaining willing and eligible individuals. This can be used to simulate individuals receiving the vaccine due to their career or risk-status.

**Note: While current COVID-19 vaccines require two doses, we only forecast when individuals receive their first dose.**

---

## Parameters

| Parameter | Type | Example | Description | 
|-----------|------|---------|-------------|
|state_population|int|11690000|Total number in population|
|precent_eligible|float|0.80|Percent of population eligible to vaccinate|
|refusal_rate|float|0.25|Percent of poulation who will refuse vaccinate|
|phase_dates|list of str|['12/15/2020', '01/17/2021', '02/28/2021', '03/31/2021']|List of phase start dates|
|phase_daily_doses|list of int|[20_000, 25_000, 35_000, 50_000]|List of daily doses by phase. Should match length pf ```phase_dates```|
|stratification_labels|list of str|['85+', '75-84', '65-74', '45-64', '25-44', '16-24']|Mutually exclusive groups to divide eligible into. Groups receive prioirity by index.|
|stratification_proportions|list of float|[0.02, 0.07, 0.14, 0.34, 0.31, 0.12]|Proportion of eligible population within each group in ```stratification_labels```. Element of list should sum to 1|
|priority_proportion|float|0.9|Proportion of daily doses to be alotted to highest priority group|

---

## Prerequisites

This repository is written using [Python](https://www.python.org/) v3.7.4 and [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/) v6.0.3. 

The following packages are required for proper function. Compatibility tested with listed versions:

Requirement | Version
------------|--------
[Matplotlib](https://matplotlib.org/) | 3.3.2
[Numpy](https://numpy.org/) | 1.19.2
[Datetime](https://docs.python.org/3/library/datetime.html) | -

Installation instructions for these packages can be found in their respective documentation.

---

## Cloning

Clone this repository to your computer [here](https://github.com/chance-alvarado/vaccination-rollout).

---

## Author

- **Chance Alvarado** 
    - [LinkedIn](https://www.linkedin.com/in/chance-alvarado/)
    - [GitHub](https://github.com/chance-alvarado/)

---

### License

This repository's contents is licensed under the MIT license.

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)

---
