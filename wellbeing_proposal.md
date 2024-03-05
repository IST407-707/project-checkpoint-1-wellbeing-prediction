# Wellbeing Predictions: The search for signs of Burnout

## Introduction

“Health is more than the absence of disease,” according to the Centers for Disease Control and Prevention. To date extensive study has been done on measures of physical health at the individual and societal level. With metrics that assess health factors focusing on diet and exercise, alcohol and drug use, access to care and the impact of the physical environment. However, metrics to assess quality of life on the basis of mental and emotional health, happiness, purpose, or love are few and not approached with the same level of empirical rigor. 

In recent years, Burn-out has emerged as a significant public health concern affecting individuals across various professions, demographics, and geographies. In 2019, the World Health Organization (WHO) included Burn-out in the 11th revision of the International Classification of Diseases (ICD-11). Burn-out is defined in ICD-11 as, “a syndrome conceptualized as resulting from chronic workplace stress that has not been successfully managed.” They characterize burnout as feelings of energy depletion or exhaustion; increased mental distance from one’s job, or feelings of negativism or cynicism related to one's job; and reduced professional efficacy.

Based on this definition, if left unaddressed, burnout poses a threat to the economy. As the pipeline from disillusioned and disengaged employees to attrition fuels a growing labor shortage, reduces productivity, and inflates health care costs. 

With 'Burn-out' being a relatively 'new' phenomenon recognized by Public Health institutions, there are not many metrics available to identify this phenomenon, track it, provide stopgaps and supporting resources to aid populations who may be in crisis. Currently methods that aim to measure burnout focus exclusively on exhaustion, use only one- or two-item indicators, or rely heavily on employee surveys. 

Understanding the complex interplay of factors contributing to burnout is crucial for developing effective interventions and support systems to mitigate its prevalence. This project seeks to leverage a data-driven to explore the underlying determinants of burnout by integrating health indicators and socioeconomic measures into spatial analysis frameworks, to gain insights into the geographic distribution of burnout and its associated risk factors. Through rigorous statistical analysis and predictive modeling techniques, we aim to provide actionable insights to employers, policymakers, healthcare providers, and other stakeholders for resource allocation and targeted interventions.

## Literature Review

#### Data and Methods

**Data**

Data from the County Health Rankings from 2018 to 2023 will be used to evaluate the spatial distribution and temporal change for variables such as the average number days of poor physical health and poor mental health reported as well as their correlation to: Unemployment rate, Food Insecurity, Excessive Drinking, Insufficient Sleep, Income Inequality Ratio, Frequent Mental Distress, Frequent Physical Distress, Disconnected Youth, Child Poverty rate, Suicide rate, Firearm Fatality rate, Median Household Income by race and Life Expectancy by race. 

The County Health Rankings datasets are a collaboration between the Robert Wood Johnson Foundation and the University of Wisconsin Population Health Institute, which compiles county-level measures from a variety of national and state data sources that aims to measure the health of nearly all counties in the nation and rank them. These data sources include the Behavioral Risk Factor Surveillance System Survey Data, the Bureau of Labor Statistics, and the American Community Survey. These measures are standardized and combined using scientifically informed weights.

[add data dimension info, select demo data from census and add]

**Methods**

Using the WHO definition of Burnout as a guide, this project aims to: 

P1. Conduct a comprehensive analysis to understand the relationships between health indicators, socioeconomic measures, and burnout at the county level. Calculate Pearson and Spearman correlation coefficients, to identify variables with the strongest associations with burnout.

P1. Use regression techniques such as Recursive Feature Elimination (RFE) and Lasso Regression to perform feature selection and identify the most relevant predictors of burnout. Evaluate the performance of the selected features using appropriate metrics such as R-squared or Mean Squared Error (MSE). Select a subset of key variables, to develop parsimonious models that capture the essential drivers of burnout while minimizing overfitting.

P1. Construct composite indices of burnout risk by standardizing and weighting individual indicators. Leverage algorithms such as Random Forest or Gradient Boosting to uncover nonlinear relationships and interactions between variables, enhancing our understanding of dynamics surrounding burnout. Use machine learning models to predict burnout and extract feature importance scores to identify key predictors. With stakeholder input, aggregate multiple dimensions of burnout risk into a single metric as this may provide a holistic way to assess hotspots. 

P2. Apply spatial analysis techniques such as kernel density estimation and spatial clustering to identify geographic hotspots. Use appropriate bandwidth selection and clustering algorithms to detect spatial clusters of elevated risk. 

P2. Access API and integrate census demographic data at the census tract level (1,400 to 8000 people per subdivision)  with spatial analysis results to assess disparities in risk among different populations. Perform spatial join operations to link demographic information to spatial units.

P2. Conduct exploratory data analysis to identify temporal patterns and relationships between variables. Visualize time series plots and heatmaps to identify trends, seasonality, and potential outliers.

P3. Select appropriate exploration and forecasting models based on the characteristics of the data. Options include: 

  Neural Network Model: Implement a neural network model using libraries like TensorFlow or PyTorch to capture complex patterns in burnout data. Experiment with different architectures and hyperparameters to optimize model performance and interpretability.

  Geographically Weighted Regression (GWR): Implement GWR using PySal to estimate spatially varying regression coefficients for predictors of burnout. Assess the spatial autocorrelation of model residuals and visualize spatial patterns of predictor effects to understand local variations in burnout risk.

P3. Evaluate model performance and fine-tune parameters using techniques such as grid search or cross-validation. Optimize model hyperparameters to improve forecasting accuracy and robustness.

P3. Identify current geographic areas and demographics at risk of burnout. Generate 2- or 5-year forecast, visualize values and confidence intervals to communicate uncertainty and provide actionable insights.


| Period         | Activity                                                      | Milestone                                               |
|----------------|---------------------------------------------------------------|---------------------------------------------------------|
| 2/22 - 3/4     | Data Collection, Initial data Exploration, engage stakeholders and get feedback | Data compiled and stakeholders identified               |
| 3/4 - 3/15     | P1 Tasks                                                      | Preprocessing complete, features selected, indices created, and stakeholder signoff attained |
| 3/16 - 4/2     | P2 Tasks                                                      | Spatial analysis complete, Census successfully merged and weighted. Exploratory data analysis of completed data set done |
| 4/3 - 4/14     | P3 Tasks                                                      | Model type selected, pipeline created, model trained and refined |
| 4/15 - 4/20    | Testing and Optimization                                      | Valuable insights attained and report complete          |


## Risks 

# Spatial Analysis Risks

Spatial analysis techniques such as kernel density estimation and spatial clustering require careful parameter selection and interpretation, risking misinterpreting results or overlooking important spatial patterns, especially without appropriate expertise.

MAUP (Modifiable Areal Unit Problem) Issues:

The Modifiable Areal Unit Problem (MAUP) may affect the spatial analysis results, as aggregation or disaggregation of data into different geographic units can lead to different conclusions or biases. Health and Socioeconomic data are available at the county level while census data is available at both the county and tract level. The intent is to use census data at the tract level, but this will need to be discussed with stakeholders. 

Mitigation: Conduct sensitivity analysis to assess the impact of different geographic units on the analysis results. Use appropriate techniques (spatial interpolation or aggregation methods) to minimize the effects of MAUP. Flesh out the rationale behind the choice of geographic units and potential implications on the analysis outcomes. Engage with stakeholders to ensure transparency and understanding of the spatial analysis methods used.

## Citations

