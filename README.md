# Project 1: Standardized Test Analysis

 - [Problem Statement](#Problem-Statement)
 - [Background](#Background)
 - [Executive Summary](#Executive-Summary)
 - [Data Sources](#Data-Sources)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusions & Recommendations](#Conclusions-&-Recommendations)


### Problem Statement
The California Department of Education(CDE) would like to evaluate the performance of SAT & ACT in the counties of California, with the aim to increase participation rate and scores of students in California. The first step would be figure out what is the gaps between the counties in the state and explore the factors that contributed to this. As the data scientist appointed, we would like to study the correlation between the tests and macroeconomic effect (GDP) on the participation rate across the state. Does the students in different counties have different performance? Does GDP really has effect on the performance and participation rate? 

---
### Background
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). 

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

---
### Executive Summary
**INTRODUCTION**

To conduct an analysis on the tests in California, datasets from both the SAT and ACT were used. Each dataset contains county-by-county average test scores and participation rates in 2019. Analyzing test scores and participation rates between the SAT and ACT allowed for a point of comparison between the counties. 
Besides that,the counties' GDP and population dataset in 2019, California were used to investigate the association between the wealthiness of the counties and performance/participation rate of the tests.

**METHODOLOGY**

A **data science workflow** was implemented to conduct this analysis. Firstly, the **problem statement** was defined???the California State of Education to determine how to improve the performance and participation rate of ACT and SAT tests. Next, **data scraping** was performed by locating credible sources that housed the appropriate datasets: ACT and SAT test scores and participation rates of California in 2019, GDP and population of California in 2019. Before beginning any analysis of the data, each individual dataset was imported to a **Pandas DataFrame**. Next, **data cleaning** was conducted to ensure that all datatypes were accurate and any other errors were fixed. All datasets were merged into a singular DataFrame. Using all data, an **exploratory data analysis** was conducted to explore the differences in test performances and participation rate between the ACT and SAT for each county in California. The counties in California was classified into 3 caucuses :Urban, Suburban and Rural in order to simplify the comparison between the counties. The performance and participation rate of students across the counties are summarised and ranked in this analysis. Lastly, the relation between GDP per capita and test participation rate is identified and basic calculations were made for clearere insight.
**data visualization**. The following data visualizations were used to display the data: 
- heat map
- scatterplots 
- regression plots
- density plots

Once all data was visualized and all statistical summaries were conveyed, **Conclusion and Recomendation** can be drawn in order to recommend macro policies to help increase the participation rate of SAT and ACT test in California.

**SIGNIFICANT FINDINGS**

When analyzing the datasets, observed that the performance of both test are similar and equally distributed across the counties. Hence,  for the most significant findings, focusing primarily on the participation rate and it's association with GDP. 

### Data Sources
The sources of the datasets used in this analysis: 

* [`act_2019_ca.csv`](./data/act_2019_ca.csv): 2019 ACT Scores in California by School
* [`sat_2019_ca.csv`](./data/sat_2019_ca.csv): 2019 SAT Scores in California by School
* [`GDP_data_by_county_2017_2019.csv`](./data/GDP_data_by_county_2017_2019.csv): 2017-2019 GDP in California by County
* [`datapile_-_headline_datasets_-_current.xlsx`](./data/datapile_-_headline_datasets_-_current.xlsx): Multiple macroeconomic factors in California by County

### Data Dictionary
**Data Dictionary for cleaned combine dataset**
 
|Feature|Type|Dataset|Description|
|---|---|---|---|
|sat_enroll12|float64|combined_data|SAT Enrollment of Grade 12 in Califonia, 2019|
|sat_numtsttakr12|float64|combined_data|SAT Number of Test Takers of Grade 12 in Califonia, 2019|
|sat_totnumbothbenchmark12|float64|combined_data|The total number of students who met the benchmark of both Evidence-Based Reading & Writing (ERW) and Math, 2019| 
|sat_pctbothbenchmark12|float64|combined_data|The percent of students who met the benchmark of both Evidence-Based Reading & Writing (ERW) and Math), Califonia 2019|
|cname|string|combined_data|County Name in Califonia| 
|act_enroll12|float64|combined_data|ACT Enrollment of Grade 12 in Califonia, 2019| 
|act_numtsttakr|float64|combined_data|ACT Number of Test Takers of Grade 12 in Califonia, 2019|
|act_numge21|float64|combined_data|Number of Test Takers Whose ACT Composite Scores Are Greater or Equal to 21 Califonia, 2019| 
|act_pctge21|float64|combined_data|Percent of Test Takers Whose ACT Composite Scores Are Greater or Equal to 21 Califonia, 2019|
|GDP|float64|combined_data|GDP number for every county in Califonia in year 2019|
|state|string|combined_data|Indication of state of Califonia, 2019|
|population|int64|combined_data|Distribution of population in every county of Califonia in year 2019|
|median_household_income|int64|combined_data|Describe the average household income for every county county of Califonia in year 2019|
|unemployment_rate|float64|combined_data|Average unemployment rate for every county county of Califonia in year 2019|

### Conclusion and Recommendations
There is a distinct positive correlation between two tests (ACT and SAT) in terms on their scorings and participation rates across the counties, where both participation rate and test score positively associated with the urbanization of the counties. However, the participation rate shows much stronger correlation than scores.As such, the data scientists from California Department of Education decided to have further analysis on the participation rate with macroeconomic factor(GDP).
 
This map shows the correlation between GDP per capita and participation rates for counties of California in 2019. When a county has higher GDP, it has darker map colour and same goes to participation rate which represented by brown circles. 
![Participation Rates v GDP/Cap](./code/Part_rate_vs_GDP.png)

From the results, it can be concluded there is a positive correlation between participation rate of tests with GDP of county. That is significatly true for urban counties, all the urban counties has participation rate in SAT test that higher than the mean (26.2%).  
However, the rural counties did not have this similar correlation, which might probably due to the following reasons:
1. Cultural norms and historical effect, where they can make good living with farming and mining in the past.
2. Contend with drug and mental-health issues, poverty, and a lack of high-speed access to the internet
3. Remote areas can???t attract enough teachers to offer college-preparatory classes

**Recommendations**

In order to achieve a growth in overall pasticipation rate of both SAT and ACT test in California, we recommend the following:  
- Allocate more budget to establish scholarship programs for students in lower GDP counties.
- Improve the educational institution and facilities in counties with lower GDP.
- Organise campaign that involves school from multiple counties to connect the students and convince the students from the rural counties that colleges and universities are able to provide the necessary skills. 
- Increase the salary or paying more incentives for teachers who giving college-preparatory classes in rural counties. 
- Provide free/subsidized preparation courses and test for low-income students



