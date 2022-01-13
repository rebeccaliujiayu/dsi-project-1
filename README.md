
# Project 1: Household income, district funding, and the effects on SAT / ACT performance

### Problem Statement
This project aims to identify the districts in California that have the worst overall student performance on the SAT and ACT tests, and identify possible reasons for the performance gap between these districts and the best performing districts. It also aims to identify potential reasons for poor participation rate in the SAT and ACT. This will allow the state of California to recommend programs to increase test performance and test participation rates, and in doing so, hopefully enable more students to go to college.

### Contents
- [Background](#Background)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)
- [Rubrics](#Rubrics)

### Background
Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from students' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry. Lately, more and more schools are opting to drop the SAT/ACT requirement for their Fall 2021 applications ([*read more about this here*](https://www.cnn.com/2020/04/14/us/coronavirus-colleges-sat-act-test-trnd/index.html)).

Prior research seems to show that household income is a major predictor of SAT and ACT scores, with richer students outperforming poorer students.<sup>[1]</sup> Two decades ago, criticisms that tests contain cultural biases (such as the use of "regatta" in a vocabulary tests, which critics argued was a word more likely to be known by privileged students) eventually led to the University of California system successfully lobbying for changes that would remove cultural biases from the test.<sup>[2]</sup> However, performance gaps between higher and lower income groups continue to persist.

Reasons often cited for the divide between rich and poor students include ability to pay for private test prep courses, and the fact that students living in wealthier districts typically attend better-funded schools.<sup>[3]</sup> However, research seems to indicate that private test prep has limited effect on test grades.<sup>[4]</sup> This project thus uses an external dataset to explore how school funding and income may influence SAT and ACT scores, so as to inform resource-allocation by the state of California.

<br>

<sup>[1]</sup> Mark Kantrowitz (2021). *[How Admissions Tests Discriminate Against Low-Income And Minority Student Admissions At Selective Colleges](https://www.forbes.com/sites/markkantrowitz/2021/05/21/how-admissions-tests-discriminate-against-low-income-and-minority-student-admissions-at-selective-colleges/?sh=263a4f0e3cc1)*. Forbes. Retrieved 5 October 2021.

<sup>[2][4]</sup> Josh Zunbrun (2014). *[SAT Scores and Income Inequality: How Wealthier Kids Rank Higher](https://www.wsj.com/articles/BL-REB-28270)*. Wall Street Journal. Retrieved 5 October 2021.

<sup>[3]</sup> Abigail Johnson Hess (2019) *[Rich students get better SAT scores — here’s why](https://www.cnbc.com/2019/10/03/rich-students-get-better-sat-scores-heres-why.html)*. CNBC. Retrieved 5 October 2021.

### Datasets
* [`act_2019_ca.csv`](../data/act_2019_ca.csv): 2019 ACT Scores in California by School
* [`sat_2019_ca.csv`](../data/sat_2019_ca.csv): 2019 SAT Scores in California by School
* [`district_income.csv`](../data/district_income.csv): 2019 Most and Least Equitable School Districts in California [[source]](https://wallethub.com/edu/e/most-least-equitable-school-districts-in-california/77056)

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**district_name**|*object*|2019 Census|The name of the school district| 
|**expenditure_per_student**|*integer*|2019 Census|Public expenditure per student in the district| 
|**income**|*integer*|2019 Census|Average household income of students in the district| 
|**pct_erw_above_bench**|*float*|2019 Dept. of Edu.|Percent of students who scored above the mean for Reading & Writing| 
|**pct_math_above_bench**|*float*|2019 Dept. of Edu.|Percent of students who scored above the mean for Math| 
|**pct_both_above_bench**|*float*|2019 Dept. of Edu.|Percent of students who scored above the mean for combined score| 
|**participation_sat**|*float*|2019 Dept. of Edu.|Percent of enrolled seniors who took the SAT| 
|**ave_read**|*float*|2019 Dept. of Edu.|Average reading score for students in the district| 
|**ave_math**|*float*|2019 Dept. of Edu.|Average reading score for students in the district| 
|**ave_sci**|*float*|2019 Dept. of Edu.|Average reading score for students in the district| 
|**pct_above_21**|*float*|2019 Dept. of Edu.|Percent of students who scored above the benchmark composite score of 21| 
|**participation_act**|*float*|2019 Dept. of Edu.|Percentage of enrolled seniors who took the ACT|

### Conclusions and Recommendations
The aim was to investigate SAT and ACT score performance, with a specific focus on possible reasons for variation in score performance across various districts. In particular, our study focused on the impact of average household income and school district funding on score performance.

#### Key Takeaways
1. **Districts with high SAT scores are extremely likely to have high ACT scores as well.**
2. **The strongest predictor of test performance was household income:** This held for both the SAT and ACT. It doesn't appear that one test is more "equitable" than the other.
2. **However, it's untrue that schools are better funded in districts with high average incomes:** There is little correlation between expenditure per student and income.
4. **In fact, districts that were better-funded performed more poorly:** Unexpectedly, test performance and expenditure per student was very weakly correlated, and the correlation was negative. This means that test scores *decrease* on average with increased funding.
    - <ins>This might suggest that funds are being poured into inefficient programs,</ins> and that funding must go into the *right* programs to achieve results.
    - <ins>An alternative explanation is that funding might be allocated based on the district's overall test performance,</ins> such that poorly-performing districts get more funding. Time series data would be needed to rule out or confirm this explanation, by investigating if sustained periods of increased funding improve test performances.
5. **Better test performance was not associated with better test participation rates:** If low participation rates is a concern, it must be addressed separately from test performance. Improving test performance will not necessarily increase participation rates.
6. **However, higher household income and district funding seemed to moderately increase test participation rates!**

#### Recommendations
1. **Time series data should be collected to properly investigate the long-term effect of district funding on test performance:** Time series data would allow the state of California to ascertain if  funding truly translations into improvements in test scores, and to what extent. It would also allow us to estimate how much funding is needed, and how long it must be sustained to achieve improvements in overall test performance.

2. **Data should be collected to estimate the efficiency of ongoing or potential programs:** Investing wisely in evidence-based interventions is likely to achieve greater results than blindly spending on programs that show little effect. Data can be collected from schools in California, or by exploring the literature on evidence-based interventions being carried out outside of California.

3. **More research should be done to figure out exactly what explains the relationship between income and test performance:** Qualitative research such as observing the school and home environments of students in high-performing and poor-performing schools may enable us to better ascertain why income is such strong predictors of test performance.

4. **Increasing funding for a district might improve participation rates:** But low participation rates must be addressed separately from test performance, as the two are poorly correlated. HOWEVER...

5. **In the short-run, the heavy use of SAT and ACT scores in the college admission process will only reinforce income inequality:** Until more can be done to lessen the score gap between high and low income students, temporary measures should be established to enable poorer students to also enter universities. This could include:
    - <ins>Encouraging universities to adopt affirmative action policies based on family income,</ins> which would mean entry requirements are lower for students from low-income families.
    - <ins>Encouraging universities to adopt alternative ways of assessing candidates.</ins> An increasing number of universities are making submission of SAT or ACT scores optional. Candidates may instead be assessed based on testimonials or personal statements. However, it should be noted that such methods of assessing candidates may not necessarily be more equitable than admitting candidates based on SAT or ACT scores.
