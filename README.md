Time Series Analysis: Impact of Firearm and Homicide Laws in Australia and Florida
Author: Parth Chandan
Last Updated: April 2025

🧠 Overview
This repository contains time series analyses evaluating the causal impact of firearm-related legislation on mortality outcomes using both published datasets and original time series modeling techniques. The assignment is split into two major sections:

🔹 Section 1: Australia’s 1996 Firearm Law
📝 Reference Study
Ukert, Benjamin et al. (2018)
This study performs an Interrupted Time Series Analysis (ITSA) and robustness checks on the effect of Australia’s 1996 firearm law on cause-specific mortality.

📈 Key Insights:
A downward trend in firearm deaths from 1979–1996 was observed even before the law.

ARIMA(1) model with first differencing was applied to remove trends and capture autocorrelation.

Robustness checks showed the ARIMA model passed placebo tests, while Negative Binomial models did not.

🔹 Section 2: Florida’s 2005 "Stand-your-ground" Law
📁 Dataset:
Source: IJE 2020 Study – 10.1093/ije/dyaa152

Variable: Monthly homicide rate per 100,000 in Florida (Jan 2000 – Dec 2007)

🔍 Objective:
To evaluate whether the implementation of the Stand-your-ground law in October 2005 significantly affected homicide rates.

🧪 Methods Used
1. Visual Exploration
Time series plotted with intervention marked

Seasonal decomposition (trend, seasonality, irregularities)

2. Stationarity and Autocorrelation Checks
Log transformation + first differencing

ACF, PACF, and lag plots

3. Segmented Regression
Includes linear time trend, step function (policy), and slope change (policy_after)

Seasonal dummy variables added

Delayed intervention also tested (policy.lag1)

4. SARIMA Modeling
Fitted: SARIMA(0,1,1)(0,0,2)[12] with policy and policy_after as regressors

Residual diagnostics confirmed good fit

5. Counterfactual Analysis
Predicted homicide rates assuming no law was implemented

Compared observed vs counterfactual trends in Florida

📊 Key Results
Segmented Regression:

Immediate policy effect: borderline significant (p = 0.066)

Long-term slope effect: statistically significant (p = 0.005)

SARIMA Model:

Immediate policy effect: statistically significant (p = 0.044)

Slope effect: statistically significant (p = 0.005)

Best Model:
While SARIMA fit the data well, the Segmented Regression model provided more interpretable estimates and better visual counterfactual clarity.

🚨 Conclusion
The "Stand-your-ground" law in Florida appears to have led to a statistically significant long-term increase in homicide rates compared to the expected trend in its absence. Counterfactual analysis supports this interpretation.

🔎 Negative Controls Proposed
Non-firearm-related homicides in Florida – to ensure changes aren’t due to broader trends.

Firearm-related homicides in North Carolina – similar regional context, but no law implemented during the period.

📁 Files Included
flhom.csv: Florida monthly homicide rates (2000–2007)

firearm_analysis.Rmd: Full code for all analysis and plots

figure1a.png: Pre-intervention firearm deaths (Australia)

README.md: This document

📌 How to Run
Clone the repository

Open firearm_analysis.Rmd in RStudio

Knit to HTML or GitHub Document

Ensure required packages are installed (e.g., forecast, astsa, sjPlot)

📚 References
Ukert B, Andreyeva E, Branas CC. (2018). Time series robustness checks...

IJE. (2020). Impact of Stand-your-ground law on homicide rates

Wikipedia: Stand-your-ground Law

