# HR Analytics Case Study
## Analyzing and Modeling Employee Turnover

Retaining employees and limiting their turnover is important for any company to do, as there are many negative ways that can impact a business, from hurting workforce planning to limiting productivity.

By providing insight via modeling and an easy-to-use dashboard, our goal is to enable leaders to easily view what employees are at risk for turnover while understanding the "why" behind it.

ETL techniques were utilized to bring the data from SQL Tables into Python, and to join relevant data together. SQL was also utilized to create new features from certain tables, like employee time, to add into our main dataframe.

Exploratory Data Analysis (EDA) was performed to see any trends or interesting facets of the data and help shape any hypotheses we had around turnover, as well as how it aligned with much of the literature reviews that were done on this topic. 

EDA uncovered some data quality issues, that include nulls, outliers, poorly labeled features, and more. These were taken care of with imputation methods, whether with logical functions using other features or with K-nearest neighbor imputation. It also uncovered a high imbalance of our target feature, attrition, which was balanced utilizing SMOTE on our training set.

Transformations, standardization and normalization were performed on data to get it pre-processed and ready to model. Feature engineering and further feature selection was performed as well to limit the complexity and drive good generalization of models.

Models we trained and tested this on were linear based (Logistic Regression, LDA, and SGD), distance based (KNN), and tree based methods (Decision Tree, Random Forest, AdaBoost, XGBoost). The tree based methods consistently provided higher scores of metrics, especially for recall which was our most important to maximize. 

There was constant iteration of these models to ensure there wasn't any overfitting, utilizing training and validation sets, while saving the test sets for the final models. After continual tuning and training, the final and best model was the XGBoost model, which had a very high recall score of .99. This utilized just 11 features, compared to the initial 24 we started with, while have a limited depth of the trees used in the ensemble (max depth of 4). 

Some of the most important features -- both for XGBoost and the rest of the models -- were consistently around pay, age, satisfaction, and distance from home. 

We created a Tableau dashboard, which can be found via this link (https://public.tableau.com/app/profile/ryan.dunn4243/viz/EmployeeAttritionRiskManagement/EmployeeAttritionDashboard?publish=yes) to help discover which employees in this data set are at high risk of turnover, to help inform managers and leaders. With this as well as information derived from models, strategies can be put in place to limit turnover at their organization.

