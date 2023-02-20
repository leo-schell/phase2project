![textme_cover.png](https://github.com/leo-schell/phase2project/blob/main/Images/textme_cover.png?raw=true)

**Authors**: John Nahra, Gligor Vasilev, Leo Schell Villanueva

<details><summary>TABLE OF CONTENTS</summary>
<p>
    - Bottom Line and Background
    - Analyzing the Data
    - Notebook Summaries
    
</p>
</details>

# Overview


We have a plan to provide immediate relief for Seattle's housing affordability crisis. The newly created Seattle Social Housing Authority (SSHA) should buy 1000 homes and rent them out to middle-income households.

This is the most ***cost- and time-effective*** option to free up entry-level affordable housing currently occupied by middle-income households. 

After an ***initial investment of $650-$950 million***, Seattle Social Housing will ***own these properties and collect rent*** from middle-income tenants.

# Business Understanding

Seattle's problem is it has a major housing shortage.

In April 2021, the City of Seattle released a [Market Rate Housing Needs and Supply Analysis](https://www.seattle.gov/Documents/Departments/OPCD/OngoingInitiatives/HousingChoices/SeattleMarketRateHousingNeedsAndSupplyAnalysis2021.pdf) detailing the complexities of the housing shortage in the area:
- There is specifically a shortage in affordable and available rental units available to families making under 80% of Seattle’s Area Median Income (AMI).
- Seattle’s middle-income families have been priced out of home ownership and “down-rent” units that would otherwise be available to low-income families.
- Nearly 46,000 households in the area are considered ‘cost-burdened’, as they spend more than half of their income on rent each month. 

Frustrations over the housing crisis have reached a boiling point and Initiative 135 was put to vote in the local election on February 14th, 2023. If passed, the city will create a new Seattle Social Housing Authority to address the housing shortage. As of today, February 19th, votes are still being counted but we remain optimistic. 

The Seattle’s Social Housing Authority’s main goal is to build housing for those making under the city’s median income. However, we propose that the city also consider acquiring housing attractive to middle-income families immediately.


## Seattle's Middle-Income Households

***As of 2022, Seattle’s Area Median Income (AMI) is $120,907[^1].***

In this analysis, we define middle-income families as two-person, three-person, or four-person households who make 80-120\% of Seattle's AMI.


Using a 30\% rent to income ratio means they can spend between \\$2400 and \\$3600 a month on rent. Median single family monthly rent in the area is around \\$3000. Thus, if we can buy up median-priced homes, we would only need to discount up to \\$600 for the lower range of the income threshold.

This is much more affordable than if they were to try and purchase these homes themselves, as the median mortgage payment is over \\$5000 per month.


# The Data

We aquired data from the following sources:
- King County 2021-2022 Home Sales data
- IRS SOI Tax Stats - Individual Income Tax Statistics - ZIP Code Data[^2]
- The Seattle Office of Housing Needs & Supply Analysis

We focused on home sales data in the city of Seattle for 2-3 bedroom homes. We filtered for homes under $2 million, located in zipcodes with mean incomes under $200k, and lot square footage under 10,000 to minimize budget costs.

# Notebook Summaries

The 'Notebooks' folder contains early data exploration conducted by individual team members. Final findings are presented in the ***Final_Notebook***.

## Final_Notebook






## Appendix i

This notebook contains the beginnings of further data exploration. In this notebook, we seek to understand the cost of expanding this project to commutable suburbs of Seattle.


You are in the README.md. 



```
├── README.md                           <- The top-level README for reviewers of this project
├── Index.ipynb                         <- Narrative documentation of analysis in Jupyter notebook
├── Slides.pdf                          <- PDF version of project presentation
├── Appendixi.ipynb                     <- Narrative documentation of analysis in Jupyter notebook
├── data                                <- Both sourced externally and generated from code
├── notebooks                           <- Individual exploratory notebooks
└── images                              <- Both sourced externally and generated from code
```



### Footnotes
[^1]: Seattle's AMI is defined in the [Seattle Office of Housing 2022 Income and Rent Limits](https://www.seattle.gov/documents/Departments/Housing/PropertyManagers/IncomeRentLimits/Income-Rent-Limits.pdf) report.
[^2]: IRS Tax Return Data