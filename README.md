# Global Vertebrate Population Declines

### Identifying high-risk population trends and geographic hotspots using the Living Planet Database

**Data analysis project | Python | Biodiversity analytics | Stakeholder communication**

---

## Project overview

Biodiversity loss is often communicated through global averages. These averages are useful, but they can hide important differences between animal groups, ecosystems, and regions.

This project uses the **Living Planet Database 2024** to analyse long-term population trends in vertebrates worldwide. The goal is to turn scientific monitoring data into clear, decision-oriented insights that could support conservation planning, communication, and prioritisation.

The main question is:

> **Which vertebrate groups and world regions show the strongest signs of population decline, and where are high-risk populations geographically concentrated?**

The project follows a full analytical workflow: from data exploration and trend calculation to risk classification, spatial analysis, and stakeholder-readable visual communication.

---

## Why this project is relevant

Conservation organisations often need to communicate complex scientific evidence to mixed audiences: researchers, policy teams, donors, project managers, and the public.

This project therefore focuses not only on analysis, but also on **translation of scientific data into accessible visual insights**.

The analysis demonstrates how population-monitoring data can help identify:

- which monitored populations are declining most strongly;
- which vertebrate groups are most affected;
- which regions contain higher shares of high-risk populations;
- where high-risk population records are geographically clustered;
- where monitoring data is limited and should be interpreted carefully.

---

## Dataset

**Source:** Living Planet Database 2024  
**Unit of analysis:** monitored vertebrate populations  
**Main data type:** long-term population time series

The dataset includes monitored populations from major vertebrate groups, including birds, mammals, reptiles, amphibians, ray-finned fishes, sharks and rays, and several smaller vertebrate classes.

The analysis focuses on populations monitored for at least 10 years to reduce the influence of very short-term fluctuations.

---

## Important data note: monitoring coverage is uneven

The Living Planet Database does not represent all animal groups equally. Some vertebrate classes contain thousands of monitored population records, while others contain only a small number.

This does **not** mean that small groups are unimportant. In some cases, they may represent rare or poorly monitored lineages. However, very small sample sizes can make comparative charts misleading.

For this reason, the project uses two complementary views:

1. **Scientific workflow:** all available classes are retained in the analytical dataset.
2. **Stakeholder-facing figures:** well-represented groups are shown in the main comparative charts, while underrepresented groups are shown separately as a monitoring-coverage caveat.


![Monitoring coverage by vertebrate class](outputs/stakeholder_figures/04_01_monitoring_coverage_by_class.png)



---

## Research questions

1. What are the overall population trends in the Living Planet Database?
2. Which vertebrate classes show the strongest population declines?
3. Which regions contain the highest share of high-risk populations?
4. Which combinations of vertebrate class and region show the clearest risk patterns?
5. Where are high-risk populations geographically concentrated?
6. Which parts of the dataset require careful interpretation due to limited monitoring coverage?

---

## Analytical workflow

### 1. Initial exploration

The first notebook explores the structure of the Living Planet Database, including taxonomic coverage, geographic coverage, ecosystem types, and monitoring duration.

Notebook:

[00_lpd_initial_exploration.ipynb](notebooks/00_lpd_initial_exploration.ipynb)

### 2. Population trend calculation

The second notebook calculates long-term population trends. Population change is measured using log trend between the first and last available observation for each monitored population.

Notebook:

[01_population_trend_calculation.ipynb](notebooks/01_population_trend_calculation.ipynb)


### 3. Risk classification

Each monitored population is classified into one consistent risk category:

| Risk category | Interpretation |
|---|---|
| Critical decline | severe long-term decrease |
| High decline | strong decrease |
| Moderate decline | noticeable decrease |
| Stable / near stable | little overall change |
| Increase | positive trend |

Populations classified as **Critical decline** or **High decline** are treated as **high-risk populations** throughout the project.

Notebook:

[02_risk_analysis.ipynb](notebooks/02_risk_analysis.ipynb)

### 4. Spatial analysis

The spatial notebook maps monitored populations, high-risk populations, regional patterns, and exploratory hotspot grids.

Notebook:

[03_spatial_analysis.ipynb](notebooks/03_spatial_analysis.ipynb)

### 5. Stakeholder-readable figures

The final notebook creates presentation-ready figures with readable labels for animal groups and regions. These figures are designed for README, portfolio, and stakeholder communication.

Notebook:

[04_stakeholder_readable_figures.ipynb](notebooks/04_stakeholder_readable_figures.ipynb)

---

## Key findings

### 1. Population declines are not evenly distributed across vertebrate groups

Well-represented vertebrate classes show different population-trend distributions. Some groups have stronger negative trends than others, indicating that biodiversity pressure is not uniform across the tree of life.



![Population trend distribution by vertebrate class](outputs/stakeholder_figures/04_02_population_trends_well_represented_classes.png)



---

### 2. Underrepresented groups should not be ignored, but they require careful interpretation

Some vertebrate classes have very few monitored population records in the dataset. These groups are retained in the analysis but separated from main comparative charts because small sample sizes can create misleading visual patterns.

This distinction matters because a small number of population records can indicate either limited monitoring coverage or genuinely rare lineages. In both cases, the correct interpretation is caution rather than deletion.


![Underrepresented vertebrate classes](outputs/stakeholder_figures/04_03_underrepresented_vertebrate_classes.png)



---

### 3. A substantial share of monitored populations is declining

Risk classification shows that many monitored populations fall into moderate, high, or critical decline categories. This suggests that biodiversity loss is visible not only at the level of individual species, but across many monitored populations.


![Risk category distribution](outputs/stakeholder_figures/04_04_risk_category_distribution.png)


---

### 4. Biodiversity risk is geographically uneven

The share of high-risk populations differs across broad biogeographic regions. This means that conservation priorities cannot be based only on global averages.


![High-risk share by region](outputs/stakeholder_figures/04_05_high_risk_share_by_region.png)


---

### 5. Risk depends on both geography and animal group

The strongest patterns appear when region and vertebrate class are examined together. Some region-class combinations show a higher share of high-risk populations than others.

This type of analysis can support targeted conservation communication: not only “where is biodiversity declining?”, but also “which animal groups are most affected in each region?”


![Region and class high-risk heatmap](outputs/stakeholder_figures/04_06_region_class_high_risk_heatmap.png)


---

### 6. Monitoring coverage is geographically concentrated

The map of all monitored populations shows where the Living Planet Database has stronger data coverage. This is important because spatial patterns of risk should be interpreted together with spatial patterns of monitoring effort.


![Global monitoring coverage map](outputs/stakeholder_figures/04_07_global_monitoring_coverage_map.png)


---

### 7. High-risk populations are geographically clustered

High-risk population records are not evenly distributed across the globe. They appear in spatial clusters, suggesting that some regions may deserve closer conservation attention or more detailed follow-up analysis.


![Global high-risk population map](outputs/stakeholder_figures/04_08_global_high_risk_population_map.png)


---

### 8. Exploratory hotspot screening can support prioritisation

The hotspot grid aggregates population records into broad 10-degree cells. Bubble size reflects monitoring volume, while colour reflects the share of high-risk populations.

This is not a formal conservation-priority model, but it is a useful exploratory screening tool for communicating where risk and monitoring data overlap.


![Exploratory high-risk hotspot grid](outputs/stakeholder_figures/04_09_exploratory_high_risk_hotspot_grid.png)


---

## Main conclusion

The analysis shows that vertebrate population decline is not evenly distributed. Risk varies by animal group, region, and the combination of both.

A key methodological lesson is that biodiversity data must be communicated with attention to monitoring coverage. Groups with limited records should not be ignored, but they should be separated from broad comparative claims.

This project therefore combines two goals:

1. **scientific analysis** of long-term population trends;
2. **clear stakeholder communication** that makes complex biodiversity data understandable without hiding uncertainty.

---

## Tools used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- GeoPandas
- Jupyter Notebook

---

## Repository structure

```text
├── data
│   ├── raw
│   └── processed
│
├── notebooks
│   ├── 00_lpd_initial_exploration.ipynb
│   ├── 01_population_trend_calculation.ipynb
│   ├── 02_risk_analysis.ipynb
│   ├── 03_spatial_analysis.ipynb
│   └── 04_stakeholder_readable_figures.ipynb
│
├── outputs
│   ├── figures
│   └── stakeholder_figures
│
├── src
│
├── requirements.txt
└── README.md
```

---

## How to reproduce the workflow

Run the notebooks in this order:

```text
00_lpd_initial_exploration.ipynb
01_population_trend_calculation.ipynb
02_risk_analysis.ipynb
03_spatial_analysis.ipynb
04_stakeholder_readable_figures.ipynb
```

The stakeholder-ready figures will be saved to:

```text
outputs/stakeholder_figures/
```

---

## Author

**Mariya Aravina**

Research background: molecular biology, reproductive genetics, animal-focused scientific work  
Current focus: data analytics, project management, scientific communication, translating complex data into actionable insights
