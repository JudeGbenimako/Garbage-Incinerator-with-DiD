# Impact of Waste Incinerator Proximity on House Prices | R and Difference-in-Differences

**NOVA IMS | R Markdown / Econometrics | January 2025**

## Overview

This independent R-based econometric study examines whether the change in house prices near a proposed/constructed garbage incinerator differs from the change for properties farther away. It uses the North Andover, Massachusetts housing-price setting described in **Kiel and McClain (1995)** and explores proximity, house characteristics, and distance-related heterogeneity.

The analysis is an **observational Difference-in-Differences (DiD) exercise**, not a controlled experiment or a definitive incinerator siting recommendation.

## Research questions

- How are changes in home sale prices associated with proximity to the incinerator?
- How do home and neighborhood characteristics influence the estimated difference?
- How does the model-implied proximity effect vary with distance?

## Methods

1. **Data exploration:** Assessed 321 observations across 25 variables, then removed a duplicate and examined influential observations.
2. **Covariate selection:** Evaluated correlations, model specifications, and multicollinearity using variance inflation factors.
3. **Difference-in-Differences:** Modeled log real housing prices using period (`y81`), proximity (`nearinc`), and their interaction.
4. **Adjusted models:** Compared specifications with housing and neighborhood covariates, then fitted a model with neighborhood fixed effects and neighborhood-clustered standard errors using `fixest`.
5. **Distance interaction:** Added a treatment-by-log-distance interaction to investigate how fitted effects change over distance.
6. **Diagnostics and plots:** Explored residuals, specification checks, and a pre-period group comparison.

The zero-crossing distance in the model is a **model-dependent threshold**, not an empirically established optimal or safe location.

## Interpretation and limitations

- **Parallel trends cannot be verified** using only one pre-treatment period. A pre-period comparison of group levels does not test similarity of earlier trends.
- The fixed-effects and clustered-standard-error estimates depend on model assumptions. Inference may be fragile with a small number of neighborhood clusters.
- Removing influential observations can change effect estimates and should be evaluated with sensitivity analyses.
- The evidence is observational and does not establish a generally applicable causal effect or policy-optimal distance.

## Technologies

R, R Markdown, `fixest`, `lmtest`, `sandwich`, `car`, `ggplot2`/`tidyverse`, `stargazer`, `openxlsx`, and regression diagnostics.

## Repository contents

- [Rmarkdown_Script_incinerator.Rmd](Rmarkdown_Script_incinerator.Rmd) — Source analysis in R Markdown.
- [Data_Incinerator.xlsx](Data_Incinerator.xlsx) — Dataset currently published in this repository.
- [Incinerator_poster.pdf](Incinerator_poster.pdf) — Academic presentation poster.
- `README.md` — Research overview and project documentation.

## Reproducing the analysis

Open the `.Rmd` in RStudio with a compatible R environment and install the required packages. **Before running**, update the data import filename inside the script from `data_group_45.xlsx` to the repository's actual `Data_Incinerator.xlsx` (or rename your local file to match).

The script has not been independently rerun or reproduced as part of this documentation review.

## Academic context

**Jude Gbenimako** — NOVA Information Management School (NOVA IMS), 2025.
