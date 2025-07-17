# Assignment3_VaccinationRates
Interactive dashboard to explore the vaccination rates for common vaccines between subgroups (race/ethnicity, urbanicity, and insurance coverage) in Pennsylvania.


# Vaccination Coverage Among Youth in Pennyslvania
#### An Investigation into Vaccination Rates Across Dimensions: Race/Ethnicity, Urbanicity, and Insurance Coverage

As a data scientist in the heathcare space in Pennsylvania, I regularly view health data and investigate social determinants of health (SDOH). These refer to non-medial attributes that influence an individual's health and well-being, such as location, salary, and education. In thise case, I will look specifically at race and ethnicity, urbanicity, and insurance coverage. Another attribute that contributes to health and is frequently associated with SDOH is race and ethnicity [meta-analysis on race and SDOH](https://bmcpublichealth.biomedcentral.com/articles/10.1186/s12889-023-15274-x).

Vaccines have been a controversial topic since the first vaccine at the end of the 18th century. I want to investigate relationships between vaccine coverage and SDOH (including race and ethnicity) in my home state of Pennsylvania. 

#### About the Data
The data is sourced from [Centers for Disease Control and Prevention](https://data.cdc.gov/). It is a combination of [Vaccination Coverage among Adolescents (13-17 Years)](https://data.cdc.gov/Teen-Vaccinations/Vaccination-Coverage-among-Adolescents-13-17-Years/ee48-w5t6/about_data) and [Vaccination Coverage among Young Children (0-35 Months)](https://data.cdc.gov/Child-Vaccinations/Vaccination-Coverage-among-Young-Children-0-35-Mon/fhky-rtsk/about_data). The datasets contain information about estimated vaccine rates within selected sociodemographic characteristics; this dashboard focuses specifically on Race and Ethnicity, Urbanicity, and Insurance Coverage. 

#### Cleaning the Data
The two datasets have similar structure. They are both on the vaccine type, geography, dimension-level. The first step in cleaning the data is renaming columns so they match across both datasets. Then, the columns of interest are selected, and the data is joined using `pd.concat()`. Lastly, the data is filtered to only include `Geography = 'Pennsylvania'` and `Dimension Type = 'Race and Ethnicity' 'Urbanicity' or 'Insurance Coverage'`

The columns in the complete dataset are `Vaccine`, `Dimension Type`, `Dimension`, `Estimate (%)`, `95% CI (%)`, and `Sample Size`. 

Once creating the visuals, I filtered on `Dimension Type` and `Vaccine` within the functions to select the subsets of interest. 

# Visualization Technique
### Barplots, summary table, and interactivity

The nature of the cleaned and formatted data is multiple categorical variables and two quantitative variables. To visualize this, I chose to use barplots and a summary table with interactive widgets to select subgroups and one or more vaccines. 

1. Select the subgroup with toggle buttons - this can be either Urbanicity (the type of city), Race/Ethnicity, or Insurance coverage. The purpose of this filtering option is to create more meaningful groups of the vaccine statistics.
2. Select one or more vaccines to view - a viewer can choose as many vaccines as desired, and the corresponding values are the average vaccination rates and total sample sizes.
3. Compare the subgroup vaccination rates and sample size views - the side-by-side barplots allow the reader to gain a better understanding of the vaccine rate metric by accounting for sample size. For example, White/Non-Hispanic race has the largest sample size, and the HPV vaccination rates are the lowest of the four race subgroups. This is an interesting note when comparing to other vaccines.
4. Compare the subgroup vaccination rates to the overall vaccination rates - the reader can gain insight into how different the vaccination rates in certain subgroups are from the general estimates. 

