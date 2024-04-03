---
title: "Does Airbnb Listing Price affect London Housing Price"
collection: projects
permalink: /projects/airbnb-housing/
excerpt: ""
---

## Introduction

This tiny data science project investigated the affect of London Airbnb Listing Prices on London Housing Prices. It made 
use of techniques such as data importation, data wrangling, data merging, data visualisation, log transformation, 
outliers identification, robust stats, PCA analysis, Pearson correlation, Spearman correlation, and time lagged 
cross-correlation.

The Airbnb dataset is from insideairbnb.com, and the housing dataset is from HM Land Registry. Code can be found in this
[GitHub Repo.](https://github.com/qisuqi/Does-Airbnb-Listing-Price-affect-London-Housing-Price) Relevant information 
from both datasets are used to identify if there is a correlation between London House Prices (HP) and London Airbnb 
Listing Prices (ALP), then if ALP affect HP by a time lagged cross-correlation analysis. Then, a regression model is 
built to predict HP with ALP. 

## Results - Images coming soon:

* Airbnb only started to gain a significant amount of listings in 2015, and grew rapidly from less than 5,000 listings
40,000 listings in 2019.
* The postcode districts with the most airbnb listings are E2, W1, N1, NW1, SE1, SW1, WC1, and RM1.
* The postcode districts with the most houses sold are E1, W2, N1, and EN3, and all the postcode districts in NW, SW,
SE, and Central London (except EC4 and EC3) have equal amount of houses sold - questionable.
* W1S has the most expensive house prices and NW2 has the most expensive airbnb listing prices. 
* Time lagged cross-correlation confirms airbnb listing prices indeed indicate changes in house prices in London, as
airbnb listing prices is the leading interaction and the Pearson Correlation is maximised when house prices is pulled
forward 1 frame (1 year). 
