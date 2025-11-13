🚗 U.S. Car Accident Severity Prediction (2016-2023)
Objective
This project analyzes over 500,000 U.S. car accidents (2016–2023) to predict crash severity and identify the key environmental, demographic, and situational factors that contribute to severe outcomes.
Using R, I developed and compared multiple machine learning models—including k-Nearest Neighbors (k-NN), Classification Trees, and Bagging—to classify accidents into four severity levels and uncover patterns that inform road safety insights.
Table of Contents
Dataset
Technologies
Data Preparation
Exploratory Data Analysis (EDA)
Modeling and Evaluation
k-Nearest Neighbors (k-NN)
Classification Trees and Bagging
Logistic Regression
Key Findings
Future Work
Dataset
Source: Kaggle - U.S. Accidents Dataset (2016–2023)
Size: 500,000 sampled accidents across 49 U.S. states
Target Variable: Severity (1–4 scale)
Features: Weather, environmental, and demographic factors including humidity, temperature, visibility, distance, population, and density
Data Collection:
The dataset aggregates data from traffic sensors, law enforcement reports, and departmental APIs.
Data Integration:
An external U.S. Census dataset was joined by State and City to incorporate demographic context such as population and population density.
Technologies
Category	Tools / Packages
Language	R
Data Wrangling	tidyverse, readr
Visualization	ggplot2, GGally
Modeling	caret, class, rpart, rpart.plot, ipred, bestglm
Environment	RStudio
Data Preparation
Import and Cleaning
Removed missing values (NA) from key features.
Selected relevant predictors such as humidity, temperature, distance, and demographic variables.
Standardized continuous predictors for model comparability.
Merging External Data
Joined the accident dataset with U.S. Census data on State and City to add population and density variables.
Feature Selection
Retained predictors with meaningful variance and interpretability for modeling tasks.
Exploratory Data Analysis (EDA)
EDA focused on understanding relationships between severity levels and environmental or demographic features.
Visualizations (produced in code):
Distribution of accident severity (bar plot)
Correlation heatmap between numerical predictors
Boxplots comparing severity by humidity, temperature, and population density
Geographic trends in severity by state
(Insert generated visuals here once available)
Modeling and Evaluation
k-Nearest Neighbors (k-NN)
Implemented using the class package.
Tuned neighborhood size (k) for optimal accuracy.
Evaluated performance via confusion matrices.
Insight:
Accident severity patterns showed non-linear relationships between environmental variables, with k-NN providing moderate accuracy but sensitivity to feature scaling.
Classification Trees and Bagging
Built a decision tree using rpart and visualized with rpart.plot.
Applied bagging with the ipred package to improve model stability and reduce variance.
Variable importance plots were used to identify influential predictors.
Key Results:
Population emerged as the strongest predictor of crash severity.
Population density and humidity were secondary contributors.
Distance was a key split variable distinguishing low- from high-severity crashes.
Example Findings from Tree Splits:
Low distance + low humidity → higher likelihood of Severity 3 crashes
High population → increased probability of Severity 4 (most severe)
Low population → linked to moderate (Severity 2) crashes
Bagging emphasized urban context and environmental conditions as major factors.
Logistic Regression
Tested logistic regression models using bestglm, but they offered limited predictive power for the four-class severity target.
Non-linear decision boundaries in environmental variables made tree-based models more suitable.
Key Findings
Factor	Relationship to Severity
Population	Strongest predictor; high population → more severe crashes
Population Density	Amplifies severity when combined with high population
Humidity	Low humidity linked to higher severity
Distance	Shorter travel distance associated with higher severity
Weather Variables (Temperature, Visibility)	Moderate influence but less significant than demographics
Overall, demographic context outweighed weather features in predicting crash severity, highlighting the importance of population-related infrastructure factors.
