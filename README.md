![textme_cover.png](https://github.com/leo-schell/phase2project/blob/main/Images/textme_cover.png?raw=true)

**Authors**: John Nahra, Gligor Vasilev, Leo Schell Villanueva

# Overview


We have a plan to provide immediate relief for Seattle's housing affordability crisis. The newly created Seattle Social Housing Authority (SSHA) should buy 1000 homes and rent them out to middle-income households.

This is the most ***cost- and time-effective*** option to free up entry-level affordable housing currently occupied by middle-income households. 

After an ***initial investment of $650-$950 million***, Seattle Social Housing will ***own these properties and collect rent*** from middle-income tenants.

# Business Understanding

Seattle's problem is it has a major housing shortage.

In April 2021, the City of Seattle released a [Market Rate Housing Needs and Supply Analysis](https://www.seattle.gov/Documents/Departments/OPCD/OngoingInitiatives/HousingChoices/SeattleMarketRateHousingNeedsAndSupplyAnalysis2021.pdf) detailing the complexities of the housing shortage in the area:
- There is specifically a shortage in affordable and available rental units available to families making under 80% of Seattle’s Area Median Income (AMI).
- Seattle’s middle-income families have been priced out of home ownership and “down-rent” units that would otherwise be available to low-income families.
- Nearly 46,000 households in the area are considered ‘cost-burdened’ as they spend more than half of their income on rent each month. 

Frustrations over the housing crisis have reached a boiling point and Initiative 135 was put to vote in the local election on February 14th, 2023. If passed, the city will create a new Seattle Social Housing Authority to address the housing shortage. As of today, February 19th, votes are still being counted but we remain optimistic. 

The Seattle’s Social Housing Authority’s main goal is to build housing for those making under the city’s median income. However, we propose that the city also consider acquiring housing attractive to middle-income families immediately.


## Seattle's Middle-Income Households

***As of 2022, Seattle’s Area Median Income (AMI) is $120,907[^1].***

In this analysis, we define middle-income families as two-person, three-person, or four-person households who make 80-120% of Seattle's AMI.

![Middle-Income Families.png](https://github.com/leo-schell/phase2project/blob/main/Images/Middle-Income%20Families.png)

Using a 30% rent to income ratio means they can spend between $2400 and $3600 a month on rent. Median single family monthly rent in the area is around $3000. Thus, if we can buy up median-priced homes, we would only need to discount up to $600 for the lower range of the income threshold.

This is much more affordable than if they were to try and purchase these homes themselves, as the median mortgage payment is over $5000 per month.


# The Data

We aquired data from the following sources:
- King County 2021-2022 Home Sales data
- IRS SOI Tax Stats - Individual Income Tax Statistics - ZIP Code Data[^2]
- The Seattle Office of Housing Needs & Supply Analysis

This analysis estimates the budget needed for the SSHA to buy 1000 homes for middle-income families. To do this, we created a linear regression model that predicts price based on select characteristics of a home:
- `bedrooms`: only 2-3 bedrooms
- `price`: under $2 million
- `zipcode`: within zip codes containing mean incomes under $200k
- `sqft_lot`: lot square footage under 10,000 to minimize costs
- `grade`: only with a construction quality of improvements score above 4
- `condition`: homes that are immediately inhabitable



# Notebook Summaries

The 'Notebooks' folder contains early data exploration conducted by individual team members. Final findings are presented in the ***Final_Notebook***.

## Final_Notebook

Our final sample contained 5260 houses to use for our model.

First, we ran a baseline dummy regressor model using mean price as the explanatory variable. Unsurprisingly, this model wasn't great, with an R-squared of 0 and a Root Mean Squared Error (RMSE) of almost $300,000

Next, we ran a simple linear regression model using living space square footage as the only explanatory variable. Living space square footage was chosen because it had the highest correlation with price.

For our final model, we did a multiple linear regression model using living space square footage and dummy variables for number of bedrooms, condition of the house, year of the home sale, and average zipcode income bins.


## Appendix i

This notebook contains the beginnings of further data exploration. In this notebook, we seek to understand the cost of expanding this project to commutable suburbs of Seattle.


# Data Visualization

***Homes in Sufficient Condition Sell for More***

![Condition.png](https://github.com/leo-schell/phase2project/blob/main/Images/Condition.png)

In our model, homes in good condition cost about $100k more than homes in bad condition all else equal.

***2021 and 2022 Were Two Different Housing Markets***

![Year.png](https://github.com/leo-schell/phase2project/blob/main/Images/Year.png)

Homes were selling for more in the first half of 2022 than in 2021. However, mortgage rates have since risen dramatically and home prices have begun to fall. We are assuming in our budget estimates that 2023 prices may be more similar to 2021 than 2022.


***More Bedrooms, Higher Price***

![Bedrooms.png](https://github.com/leo-schell/phase2project/blob/main/Images/Bedrooms.png)

According to our model, a 3-bedroom home costs $15,000 more than a 2-bedroom home all else equal.

***Wealthier Neighborhoods Command Higher Home Prices***

![Zip Code.png](https://github.com/leo-schell/phase2project/blob/main/Images/Zip%20Code.png)

Our fourth variable is zipcodes grouped into 3 mean income bins: 50 to 100 k, 100 to 150 k, and 150 to 200 k. Homes tend to be more expensive in wealthier neighborhoods.

***Living Space Square Footage Most Positive Correlated with Price***

![Square Foot.png](https://github.com/leo-schell/phase2project/blob/main/Images/Square%20Foot.png)

The final variable in our model is square footage of living space. Our model suggests that each square foot of living space is associated with on average a $320 increase in home price all else equal.

# Conclusion

Based on our model, we can derive budget estimates for the Seattle Social Housing Authority. 

![Budget Estimates.png](https://github.com/leo-schell/phase2project/blob/main/Images/Budget%20Estimates.png)

We calculated estimates for average-sized 2-3 bedroom homes in good condition for each income zipcode, ranging from $650 million at the low end to $930 million at the high end. 

We can also calculate rough rental market rates based on these home prices, which range from $2600-$3700 per month. Recall that our middle-income households can afford $2400-$3600, so we should be able to rent out these homes without discounting significantly.

# Next Steps

Ultimately, the long-term fix to a limited affordable housing supply is to build more homes.

However, given the time it takes to identify land, acquire zoning permits, design and build homes, and the urgency of the crisis, buying 1000 single-family rental properties for middle-income families will provide some quick relief in the meantime.

This plan frees up entry-level housing for low-income households. And it will be the most cost-effective for Seattle, as middle-income households can afford the market rental rate for median-priced homes.


# Repository Map

```
├── README.md                           <- The top-level README for reviewers of this project
├── Final_Notebook.ipynb                <- Narrative documentation of linear regression model in Jupyter notebook
├── presentation.pdf                    <- PDF version of project presentation
├── Appendixi.ipynb                     <- Further analysis in Jupyter notebook
├── data                                <- Both sourced externally and generated from code
├── notebooks                           <- Individual exploratory notebooks
└── images                              <- Content repository
```



### Footnotes
[^1]: Seattle's AMI is defined in the [Seattle Office of Housing 2022 Income and Rent Limits](https://www.seattle.gov/documents/Departments/Housing/PropertyManagers/IncomeRentLimits/Income-Rent-Limits.pdf) report.
[^2]: IRS [Tax Return Data](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-zip-code-data-soi)