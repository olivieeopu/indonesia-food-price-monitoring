# indonesia-food-price-monitoring
Exploratory monitoring of food-price shocks, persistence, recovery, and regional disparities across Indonesian provinces.

overview data :
- 32 provinces
- 12 commodities
- 60 months
- 23,040 observations
- 22,979 observed prices
- 61 missing values
- Snapshot 2025: 20 commodities dan 38 province (tidak digunakan untuk processing)

# From Price Spike to Monitoring Signal

An exploratory food-price monitoring project that distinguishes localized price fluctuations from widespread and persistent shocks across Indonesian provinces.

	⁠*Analysis period:* January 2021–December 2025  
	⁠*Balanced panel:* 12 commodities, 32 provinces, 60 months  
	⁠*Tools:* Python, pandas, DuckDB SQL, Tableau, Matplotlib, and Seaborn

# Project overview

Average price rankings alone cannot show whether a price movement is unusual, geographically widespread, persistent, or slow to recover. This project develops a monitoring framework based on six dimensions:

• price-change magnitude;
• spike frequency;
• geographical breadth;
• persistence after the initial spike;
• recovery duration; and
• regional price disparity.

The result is a set of analytical tables and interactive Tableau dashboards for identifying commodity shocks and province–commodity combinations that may require closer monitoring.

# Data scope

Longitudinal analysis

• 23,040 expected province–commodity–month observations

• 22,979 observed prices and 61 retained missing values

• 382 eligible province–commodity series; 2 structurally incomplete series excluded

• 12 consistently recorded commodities across 32 provinces

• 60 consecutive months from January 2021 to December 2025


Missing prices were retained rather than imputed to avoid introducing artificial price movements. Later-introduced provinces and commodities were excluded from the longitudinal panel to preserve comparability.

Additional 2025 snapshot

A separate 2025 snapshot covers 20 commodities across all 38 provinces, with 9,120 expected observations and 8,867 observed prices. It is kept separate from the longitudinal analysis because the wider coverage does not have equivalent five-year history.

# 4. Business Questions

This project addresses the following decision-oriented questions:

1. How did food prices change between 2021 and 2025?

2. Which commodities experienced the greatest long-term price increases and volatility?

3. Which price spikes were isolated local events, and which developed into geographically widespread shocks?

4. Which commodity shocks combined the greatest geographical breadth with the highest price-change intensity?

5. Which provinces tended to show early price-pressure signals before similar movements appeared more broadly?

6. Which provinces recovered most quickly after a food-price spike?

7. Which commodities were most likely to remain elevated after an initial spike?

8. Which commodities frequently experienced simultaneous price pressure?

9. Did regional price disparities return to normal after a shock or remain persistently wide?

10. Which province–commodity combinations should be prioritized in a food-price monitoring watchlist?


# Key findings

• Packaged cooking oil recorded the largest increase in the national median price index, reaching 164.38 in December 2025 relative to January 2021 = 100. Shallots followed at 155.32.
• The framework identified 332 commodity-month shock events, including 24 priority monitoring signals.
• Curly red chili generated the most priority monitoring signals (8), followed by shallots (7) and bird’s-eye chili (6).
• The most intense median spike occurred for bird’s-eye chili in December 2021: 119.58%, with 80.65% of valid provinces affected.
• Across 2,131 eligible provincial spike events, 40.2% recovered within the observation window.
• Local/loose granulated sugar showed the highest six-month persistence rate at 85.03%.
• Medium and premium rice had the strongest shock co-occurrence: 5 simultaneous months, 55.56% Jaccard similarity, and 6.15× lift.
• The highest-ranked monitoring combination was packaged cooking oil in East Nusa Tenggara, with a monitoring score of 77.12.

# Analytical workflow

1. Standardized province codes, province names, commodity names, dates, and price values.
2. Constructed a balanced monthly panel for fair longitudinal comparison.
3. Calculated month-to-month and year-on-year price changes.
4. Measured commodity volatility and cross-province price disparity.
5. Identified price spikes using commodity-specific empirical thresholds.
6. Evaluated shock breadth, intensity, persistence, recovery, and co-occurrence.
7. Combined the indicators into a province–commodity monitoring score and priority category.
8. Built interactive Tableau dashboards for exploration and communication.

# Dashboard

https://public.tableau.com/views/FoodPriceMonitoringDashboardIDN/IndonesiaFoodPriceMonitoring?:language=en-GB&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

The packaged Tableau workbook should be placed in dashboard/, and direct PNG exports of the four dashboard pages should be placed in assets/.

## Dashboard Pages

### 1. National Overview
Provides a summary of data coverage, monthly price trends, commodity volatility, and regional price differences across Indonesia.
<img width="1302" height="909" alt="image" src="https://github.com/user-attachments/assets/4ebadff4-b52b-452e-b5f1-3498665ea67a" />

### 2. Shock Analysis
Identifies localized and widespread price shocks based on their geographical breadth, price-change intensity, and priority classification.
<img width="1328" height="887" alt="image" src="https://github.com/user-attachments/assets/59d9681d-92d2-45fc-bac4-ab8b35acd589" />


### 3. Regional Resilience
Evaluates how provinces and commodities recover after price spikes, including recovery rates, recovery duration, persistence, and regional disparity.
<img width="1299" height="911" alt="image" src="https://github.com/user-attachments/assets/b284aa04-bbc6-4ded-8b95-6b3953c6fddc" />


### 4. Monitoring Watchlist
Ranks province–commodity combinations based on spike magnitude, frequency, breadth, persistence, recovery duration, and regional price disparity.
<img width="1301" height="900" alt="image" src="https://github.com/user-attachments/assets/bc7e1519-e151-45fc-879d-765ea1a9ce3c" />



# Data source

Provincial-level consumer food-price data from Badan Pangan Nasional, distributed through Indonesia’s open-data portal, Satu Data Indonesia.

Important limitations

• The dataset contains food prices, not official inflation rates.
• Provincial averages are not used to reproduce an official national price index.
• The data does not include consumption weights or explanatory variables such as production, weather, transportation, distribution, demand, or policy.
• The analysis identifies descriptive patterns and monitoring priorities; it does not establish causality.
• Lead–lag results do not prove price transmission between provinces.
• Shock classifications and monitoring scores are project-specific analytical indicators, not official government classifications.

Author

Fransciska Olivia Warae
Data Science undergraduate, BINUS University
