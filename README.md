# Predicting school closings from the DOE College Scorecard
## Kirsten Regier

# Introduction
According to the https://www.statista.com/ data 'Number of higher education institutions in the U.S. 1980-2017' data, between 2012 and 2017, the number of higher education institutions decreased by roughly 400. It could be useful to have a model that is able to predict colleges and universities that are in danger of closing. Colleges and universities could use information about common features of schools that have closed to examine their own operational systems, particularly as they face financial difficulties from the coronavirus, which compound the previously existing demographic trends that challenge college enrollment. Insight into which factors that have contributed most significantly in the closing of other colleges could allow current college administrators to make informed decisions about how to protect the future of their institution.

# The Data
The data was gathered from the US Department of Education’s College Scorecard, which is available from https://collegescorecard.ed.gov/data/. The database contains information about schools participate in the Title IV program and accept or distribute federal financial aid to students. Annual data is available from 1996 to 2013; the current analysis focusses on data from 2010 and beyond.
The database includes information about the institution, its finances, federal financial aid and student debt, completion and retention rates, and student demographics. A subset of 12 features was selected for the final analysis. The target variable was a boolean variable that indicates whether the school is currently operating.

## Currently operating schools by governance and cost
The schools in the data are divided into three categories based on the type of governance - public schools, private nonprofit schools, and private for-profit schools. The following figure shows the cost of currently operating institution based on their governance structure, and the predominant degree awarded by the institution. Private nonprofit schools have higher costs in general, but offer higher degrees than public and private for-profit schools. Public schools generally have lower costs in all degree categories.

![Swarmplot of Cost by Predominant degree and Governance structure for currenlty operating institutions](/figures/currentPriceDegreeSwarm.png)

# Modeling and Results
A Decision Tree model formed the base for an AdaBoost model which was trained to predict school closings from the data. The AdaBoost model achieved an overall accuracy of 92%, with a recall of 93% and precision of 89% with respect to closed schools.

# Future directions
The most recent data in the DOE College Scorecard data was 2013. It would be interesting to compare the predictions made by the 2013 model to the actual current data, and see how the model and predictions would change if retrained on the more current data. If the goal is of using the model is to help schools weather the financial and economic uncertainty surrounding the coronavirus pandemic, having accurate *current* information about the schools and their financial status would be important.

While the current scorecard data reports on several institutional financial metrics, like tuition revenue and instructional expenditure, other financial metrics may provide useful information about the financial status of the institution, that would help make more accurate predictions.

Finally, another popular resource for evaluating colleges and universities is the annual US News and World Report rankings. Including information from these rankings, or accessing the data on which the rankings are based, could provide additional metrics and useful features for predicting the closure of institutions.
