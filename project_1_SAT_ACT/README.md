# General_Assembly_projects
# SAT & ACT Analysis

### SAT and ACT data analysis in 2016 and 2018 years by states of the United States of America.

The College Board released a new version of the Standardized Tests (SAT). The New SAT made its debut in March 2016 and impacts students in the class of 2017 or younger. We aim to analyze the data about ACT and SAT scores and participation rate in 2017 and 2018 years, the major trends and difference.

### Contents:
- 2017 Data Import & Cleaning
- 2018 Data Import and Cleaning
- Exploratory Data Analysis
- Data Visualization
- Descriptive and Inferential Statistics
- Colorado, Illinois and North Carolina participation trends
- Conclusions and Recommendations

## Data files:

- [act_2017.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_1_SAT_ACT/data/act_2017.csv)
- [act_2018.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_1_SAT_ACT/data/act_2018.csv)
- [sat_2017.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_1_SAT_ACT/data/sat_2017.csv)
- [sat_2018.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_1_SAT_ACT/data/sat_2018.csv)

### Additional data files:

- combined_2017.csv
- final_df.csv

## The sources of the data:

- [SAT](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
- [ACT](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)

___________________________________________________________________________________

## A data dictionary provides a quick overview of features/variables/columns, alongside data types and descriptions.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|act_2017|List of states and territories of the United States.|
|participation_ACT17|float64|act_2017|The share of high school graduates in a particular geographic entity who take the ACT, in percentages (%).|
|english_ACT17|float64|act_2017|The first section is the 45-minute English test covering usage/mechanics, sentence structure, and rhetorical skills. Scored on a scale of 1–36.|
|math_ACT17|float64|act_2017|The second section is a 60-minute, 60-question math test with the usual distribution of questions being approximately 14 covering pre-algebra, 10 elementary algebra, 9 intermediate algebra, 14 plane geometry, 9 coordinate geometry, and 4 elementary trigonometry questions. Scored on a scale of 1–36.|
|reading_ACT17|float64|act_2017|The reading section is a 35-minute, 40-question test that consists of four sections, three of which contain one long prose passage and second one contains two shorter prose passages. Scored on a scale of 1–36.|
|science_ACT17|float64|act_2017|The science test is a 35-minute, 40-question test. The content of the science test includes biology, chemistry, physics, and the Earth/space sciences. Scored on a scale of 1–36.|
|composite_ACT17|float64|act_2017|The Composite score is the average of four test scores, rounded to the nearest whole number. Fractions less than one-half are rounded down; fractions one-half or more are rounded up. Scored on a scale of 1–36.|
|||||
|state|object|sat_2017|List of states and territories of the United States|
|participation_SAT17|float64|sat_2017|The share of high school graduates in a particular geographic entity who take the ACT, in percentages (%).|
|reading_writing_SAT17|int64|sat_2017|The Reading Test is made up of one section with 52 questions and a time limit of 65 minutes. Scored on a scale of 200–800. All questions are multiple-choice and based on reading passages. The Writing and Language Test of the SAT is made up of one section with 44 multiple-choice questions and a time limit of 35 minutes. It coundes equally toward combined Reading and Writing score.|
|math_SAT17|int64|sat_2017|Math Test in total is 80 minutes long and includes 58 questions: 45 multiple choice questions and 13 grid-in questions. Scored on a scale of 200–800. The multiple choice questions have four possible answers; the grid-in questions are free response and require the test taker to provide an answer.|
|total_SAT17|int64|sat_2017|Overall score, combination of section scores with range of 400-1600|

________________________________________________________________

## Conclusions and Recommendations

Based on the analysis carried out, it can be noted that the overall participation rate for ACT is significantly higher than for SAT. At the same time, rates from 2017 to 2018 have changed. While ACT showed a slight decline, SAT showed a good increase in participation. SAT demonstrated good policy due to which 33 states increased in their participation rates and only 4 states showed a drop. For example, states such as Illinois and Colorado have grown significantly in participation because SAT has become mandatory for students entering universities.

It shows that **partnering** with states' school administrators and universities is the most effective way to increase participation.

Taking North Carolina state as an example, we can observe a high participation rate in both tests in 2017 and 2018 years. The reasons for this can be the acceptance of both tests and free test preparation courses. The same strategy can be implemented for other states which accept both tests. 

Ohio can be a potential client for SAT test because the state accepts both tests and [form 2017](https://www.dispatch.com/news/20170228/ohio-schools-must-now-give-act-or-sat-to-all-juniors) students don’t have to pay test's fee. Often students take two tests because they can take one for free, so attracting students in a given state can not only increase participation but also **draw conclusions on the content of the test** (there is a possibility to compare the difficulty of the test and verify the grading scale).

The methods listed above, such as partnerships with school and university administrations and attracting students in states where payment is cancelled and both tests are accepted, must be combined with:
- Active SMM on the Internet, promotion of articles on the benefits of SAT compared to ACT.
- Promotion of videos with a detailed description of how to prepare for the test.
- Using platforms such as Coursera and EdX.
- Retain partnership with Khan Academy.
- Establishing new scholarships for students who can creatively share their positive experience of - passing the test on social networks.
- Cost reduction or cancellation for low-income students.


Recommendations for further research:
- Explore the states of Arizona, District of Columbia, Florida and Nevada in more detail in connection with a decrease in the participation rate.
-  Analyse the choice of the students in those states where they can take both tests. Collect data on the desired universities for admission, school performance, demographic characteristics.
- Analyze the performance of the test by students who passed both tests. To study the features of assessment, the complexity of the test and subtests.
