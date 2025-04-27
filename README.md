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


## Data Sources

### Bank Locations
- [Bank Locations - DC Open Data](https://opendata.dc.gov/datasets/dfc51a5bd29347d0a2399743d3144d31_0/explore?location=38.894827%2C-77.015000%2C10.41)

### Crime Incidents (2008–2025)
- [Crime Incident 2025 - DC Open Data](https://opendata.dc.gov/datasets/74d924ddc3374e3b977e6f002478cb9b_7/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2024 - DC Open Data](https://opendata.dc.gov/datasets/c5a9f33ffca546babbd91de1969e742d_6/explore?location=0.998437%2C-77.012050%2C0.00)
- [Crime Incident 2023 - DC Open Data](https://opendata.dc.gov/datasets/89561a4f02ba46cca3c42333425d1b87_5/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2022 - DC Open Data](https://opendata.dc.gov/datasets/f9cc541fc8c04106a05a1a4f1e7e813c_4/explore?location=38.950761%2C-77.098817%2C12.80)
- [Crime Incident 2021 - DC Open Data](https://opendata.dc.gov/datasets/619c5bd17ca2411db0689bb0a211783c_3/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2020 - DC Open Data](https://opendata.dc.gov/datasets/f516e0dd7b614b088ad781b0c4002331_2/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2019 - DC Open Data](https://opendata.dc.gov/datasets/f08294e5286141c293e9202fcd3e8b57_1/explore)
- [Crime Incident 2018 - DC Open Data](https://opendata.dc.gov/datasets/38ba41dd74354563bce28a359b59324e_0/explore)
- [Crime Incident 2017 - DC Open Data](https://opendata.dc.gov/datasets/6af5cb8dc38e4bcbac8168dd1b98adf7a_38/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2016 - DC Open Data](https://opendata.dc.gov/datasets/bda20763840448b58f8383bae800a843_26/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2015 - DC Open Data](https://opendata.dc.gov/datasets/35034fcb3b36499c84c94c069ab1a966_27/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2014 - DC Open Data](https://opendata.dc.gov/datasets/6eaf3e9713de44d3aa103622d51053b5_9/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2013 - DC Open Data](https://opendata.dc.gov/datasets/5fa2e43557f7484d89aac9e1e76158c9_10/explore?location=38.904052%2C-77.012050%2C10.80)
- [Crime Incident 2012 - DC Open Data](https://opendata.dc.gov/datasets/010ac88c55b1409bb67c9270c8fc18b5_11/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2011 - DC Open Data](https://opendata.dc.gov/datasets/9d5485ffae914c5f97047a7dd86e115b_35/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2010 - DC Open Data](https://opendata.dc.gov/datasets/fdacfbdda7654e06a161352247d3a2f0_34/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2009 - DC Open Data](https://opendata.dc.gov/datasets/73cd2f2858714cd1a7e2859f8e6e4de4_33/explore?location=38.904042%2C-77.012050%2C10.75)
- [Crime Incident 2008 - DC Open Data](https://opendata.dc.gov/datasets/180d56a1551c4e76ac2175e63dc0dce9_32/explore?location=38.904042%2C-77.012050%2C10.75)

### Census & Boundaries
- U.S. Census: [DC Census Tract Shapefiles (TIGER/Line 2024) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2024/TRACT/)

### Points of Interest & Other Zones
- [Grocery Store Locations - DC Open Data](https://opendata.dc.gov/datasets/1d7c9d0e3aac49c1aa88d377a3bae430_4/explore)
- [Alcohol License Businesses Locations- DC Open Data](https://opendata.dc.gov/datasets/cabe9dcef0b344518c7fae1a3def7de1_5/explore?location=38.902438%2C-77.008884%2C10.87)
- [Alcohol License Moratorium Zones - DC Open Data](https://opendata.dc.gov/datasets/1092394719a44d72af2c9b6ddb269551_35/explore?location=38.916698%2C-77.024780%2C12.41)
- [Low Food Access Zones- DC Open Data](https://opendata.dc.gov/datasets/9b4355a8e1e345ea8350b77516163dd4_61/explore?location=0.998270%2C-77.012623%2C0.00)
- [Military Bases - DC Open Data](https://opendata.dc.gov/datasets/21ee426eddc14014b80535cd6b8316e7_11/explore?location=38.882176%2C-77.038358%2C11.28)
- [Police Sectors- - DC Open Data](https://opendata.dc.gov/datasets/6ac17c2ff8cc4e20b3768dd1b98adf7a_23/explore?location=38.890765%2C-77.026467%2C10.99)
- [Street Vending Zones - DC Open Data](https://opendata.dc.gov/datasets/e05b93650d0a47ab846db46d2ba08b05_159/explore?location=38.894827%2C-77.015000%2C10.41)
- [DC Government WiFi Hotspots - DC Open Data](https://opendata.dc.gov/datasets/0a73011064ae4580a4a8539de03060d1_14/explore?location=38.881298%2C-77.013764%2C10.23)
