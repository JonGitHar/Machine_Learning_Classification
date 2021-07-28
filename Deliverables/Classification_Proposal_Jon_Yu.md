## Project Proposal
Authored by Jon Yu \
on July 28, 2021

### Question/need:
The purpose of this classification project is to arrive at a model that can reasonably predict whether or not a particular athlete will obtain a medal at the Olympics. On a national level, this model can be used to direct funding to specific individuals for long-term development regardless of performance in the national Olympic qualifiers.

### Data Description:
120 years' worth of Olympic history is available on Kaggle (https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results) to be downloaded in *.csv format and can be brought into Python via use of DB Browswer for SQLite and SQLAlchemy. This table contains 271,116 entries with each row corresponding to a particular athlete and the particular sport/event/year he/she competed in. Of note is that one athlete can appear multiple times due to competition in multiple sports/events/years.

As this table has limited information on the athlete (with only seemingly relevant features being age/height/weight), feature engineering will be performed to introduce new columns, such as whether or not the particular athleted medaled in the event previously, whether or not the athlete's nation has medaled in the event previously, how long the country has been represented in the sport in the Olympics, and whether or not the the athlete belongs to the host country. 

Additional information will be sought out for merging, such as a nation's spending on athlete development, nation's GDP, athlete's recent placings in international (non-Olympic) tournaments, recent injuries, etc.

Careful consideration will be given to the predictors as the "optimal" physical traits are specific to each sport. The data set will either be broken down into the sport with the most number of entries and if not, a decision tree will be utilized.


### Tools: 
* Selenium for web scraping
* Python to ingest and aggregate raw data into a SQL database
* Pandas for exploratory data analysis and cleaning
* MatPlotLib and Seaborn to plot data for correlation analysis
* StatsModel and SciKit Learn for logistic regression
* (Potentially) Streamlit to deploy the classification model and allow for inputs to predict output

### MVP Goal:
The minimum viable product (MVP) will be a binary classification model predicting whether or not a particular athlete will medal. Final project will break the medal category into the respective placings - gold/silver/bronze.
