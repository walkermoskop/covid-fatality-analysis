# covid-fatality-analysis
An analysis of COVID fatality rates in Midwestern counties

# Overview
The analysis markdown file (and corresponding HTML output) in this repository contains an analysis of county-level COVID-19 fatality rates in Midwestern states conducted for an advanced linear modeling graduate course at Indiana University. The analysis primarily uses linear mixed effects models (and tests applied to those models) to identify whether various government mandates (including their duration), reported mask usage, and partisan political preference could explain variation in COVID death rates between counties.

The data-processing.Rmd file reads in and merges the following county-level datasets, which are then used for the analysis:
* COVID deaths
* population totals
* race
* ethnicity
* income
* transporation usage
* occupation category
* mask use
* presidential election results
* health insurance rates
* temperature
* mask mandates
* stay at home orders
* bar closings
* restaraunt closings

The variables under specific consideration were the enactment of stay at home orders, mask mandates, bar closures, and restaurant closures, the share of population who reported "frequently" or "always" wearing a mask, and the Republican pct. vote margin in the 2020 presidential election. To test whether these variables were influential, they were compared to a baseline model containing data about each county that was uninfluenced by COVID, such as population density, racial and ethnic makeup, income, temperature, the pct. of residents working in high-risk occupations (i.e. food preparation), the pct. of residents with underlying health conditions, median age, and the pct. of residents using public transportation. (A full description of all data is contained in the end of the analysis file.) A secondary, broader question explored in this analysis was to identify which variables (including the baseline variables) best explained variation in death rates.

# Important caveats
This analysis was last run in early-May, so it isn't up-to-date. To re-run this with updated COVID death data, the datasets for mask mandates, bar and restaurant closures, weather, etc. would also need to be updated. This is by no means intended to be a journal-ready publication; the primary aim of this project was to develop a research question that could be analyzed using publicly available COVID-related to datasets and then to address the question by applying many of data exploration, modeling and testing approaches covered in the course. A crucial caveat about this is that the models used here didn't weight counties by population because the wide ranges in population, used as the offset parameter when running models using R's [lme4 package](https://cran.r-project.org/web/packages/lme4/vignettes/lmer.pdf), created instability and prevented models from converging, a software issue I simply wasn't able to resolve before my deadline.

Additionally, three datasets are missing because they were too large to upload. They can be downloaded from the CDC:

* [Mask mandates](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i)
* [Restaurant closures](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Orders-Closing-and-Reope/azmd-939x)
* [Bar closures](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Orders-Closing-and-Reope/9kjw-3miq)
