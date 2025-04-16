# Intro2DS Final Proj: Crime Prediction in Washington DC: A Geospatial Analysis with Machine Learning

## Team Members

*Troy Cheng, Ziqiao Shan, Minji Kang, Sarah Krause*

## Research Proposal

How accurately can we predict crime rates at the ward level in Washington DC by integrating machine learning methods? We are interested in the social determinants of crime and how that relates to the spatial layout of Washington DC. We will explore demographic variables such as distribution of race, age, gender, single parent status, education level, and socioeconomic status by ward. We are also interested in exploring ward-level variables such as number of grocery stores and alcohol consumption rates. We also aim to explore crime rates before and after the COVID-19 pandemic. Based on previous work and insights from Decoding FBI Crime Data and Crime by the Numbers: A Criminologist’s Guide to R by Jacob Kaplan, we dive deeper into crime-related data of DC using machine learning methods. By combining multiple analytical approaches and diverse data sources, we seek to create a more comprehensive understanding of crime patterns and their associations with socioeconomic, demographic, and environmental factors. 

Our approach includes the following steps: (1) data collection from multiple sources, including crime incident reports, demographic data, economic indicators, and location-based features; (2) exploratory data analysis to identify patterns and relationships between variables; (3) feature engineering to create meaningful predictors and temporal features, (4) development of potential predictive models using both traditional machine learning algorithms and more advanced techniques such as geographically weighted regression and neural networks; and (5) cross-validation for model selection, using appropriate metrics to evaluate performance and ensure the reliability of our predictions, including area under the ROC curve, precision-recall curves, and spatial autocorrelation measures. The major technical hurdles we anticipate include: (1) integrating data across different spatial units and temporal scales, which will require careful geocoding and aggregation techniques; (2) handling the complex temporal patterns in crime data; and (3) handling rare incidents of crime using multi-class classification methods to enhance model performance. 

## Comments

*by Prof. Alena Stern*

Nice work on the proposal! The topic meets the basic project requirements of articulating a policy-relevant question and using at least three of the data science tools covered in this class (listed in the assignment) - so I think you should feel free to move ahead!

Your proposal mentions predicting crime rates at the ward level. To train an effective ML model, you'll need far more observations than ward-level data would allow (8 observations). I'd recommend performing your analysis at the tract level. 

I also would recommend clarifying your exact predictive question. For example, are you trying to predict future crime rates? If so, how far in advance are you hoping to make that prediction? I would encourage you to think carefully about what data would be available to make a given prediction. For example, if you are trying to predict crime rates two years ahead, when predicting 2024 crime rates in 2022, you'd have to think about what ACS data would be available in 2022. Because ACS is published on a lag, this would be the 2016-2020 5-year ACS. 

This would also inform what years of crime data you'll use to create your outcome.

Another place to think about time is setting up your training and testing sets, as well as your resampling. I'd encourage you to check out these resources I shared on Slack:

Time-series resampling with tidymodels:

<https://www.tidymodels.org/learn/models/time-series/>

<https://rsample.tidymodels.org/reference/slide-resampling.html>

I'd note that the ACS demographic and economic variables are available at the tract level!

I would encourage you to think about opportunities for other spatial analysis. For example, you can look at crime rates within a given distance buffer around other points of interest, like metro stations. 

Finally, I'm excited about your interest in using methods we didn't cover in class like neural networks and geographically weighted regression. That isn't required, but it is definitely allowed!
