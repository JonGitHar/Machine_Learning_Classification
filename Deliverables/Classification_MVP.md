The project was revised midway from predicting Olympic medaling to predicting approval of US permanent work visa. All the available data for 2020 and 2021 were obtained from the Department of Labor website (https://www.dol.gov/agencies/eta/foreign-labor/performance). The total entries after imgesting the two tables into data frames and concetenation yielded 129,996 entries with 154 columns, but the initial trimming to consider only certified(approved) and declined cases narrowed this down to 91,735. 

The baseline model only considered a very tiny subset of the 154 features were considered: skill level, wage, fulfilling required experience, and presence of special skills. Of the KNN, logistic regression, and random forest classifier models attemped thus far, KNN produced the best balance of accuracy, precision, recall, and F1 values.

Further feature engineering will be performed to introduce additional columns, such as 
- If decision date was during Trump or Biden administration (0 if the date was before January 20, 2021 when President Biden took oath of office and 1 otherwise)
- If the candidate is employed by a prominent company (considering FAANG at this point as a categorical variable)
- Additional column to indicate whether or not candidate has a Bachelor's degree (anyone whose highest degree is a Master's or PhD will be assumed to automatically fulfill this)

Also, country specific information will be obtained to be merged with the application data frame.

Lastly, additional models will be used for analyses with more fine-tuning of parameters.
