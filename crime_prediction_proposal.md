# Crime Prediction in Washington DC: A Geospatial, Machine Learning, and Text Analysis Approach

## Team Members

-   Troy Cheng
-   Ziqiao Shan
-   Minji Kang
-   Sarah Krause

## Research Proposal

Our team aims to develop a predictive model for crime rates at the census tract level in Washington DC by integrating geospatial analysis, machine learning, and text modeling techniques. The motivation for this project stems from the need for more accurate crime prediction models that can help law enforcement agencies allocate resources efficiently and implement targeted crime prevention strategies. By combining multiple analytical approaches and diverse data sources, we seek to create a more comprehensive understanding of crime patterns and their relationships with socioeconomic, demographic, and environmental factors.

Our approach will involve several steps: (1) data collection and preprocessing from multiple sources, including crime incident reports, demographic data, economic indicators, and location-based features; (2) exploratory data analysis to identify patterns and relationships between variables; (3) feature engineering to create meaningful predictors, including spatial lag variables, temporal features, and text-derived sentiment indicators; (4) development of predictive models using both traditional machine learning algorithms and more advanced techniques such as geographically weighted regression and neural networks; and (5) model evaluation and interpretation to assess performance and identify key factors influencing crime rates. We will implement a rigorous cross-validation strategy to ensure the reliability of our predictions and use appropriate metrics to evaluate model performance, including area under the ROC curve, precision-recall curves, and spatial autocorrelation measures.

The major technical hurdles we anticipate include: (1) integrating data across different spatial units and temporal scales, which will require careful geocoding and aggregation techniques; (2) handling the complex temporal patterns in crime data, including seasonality, trends, and special events; and (3) addressing class imbalance issues in crime categories, which may require specialized sampling or cost-sensitive learning approaches. Additionally, extracting meaningful features from text data in crime reports will present challenges in terms of preprocessing, tokenization, and sentiment analysis that accurately captures the nuances of crime-related text.

## Data Sources

### 1. DC Crime Incidents Data (2008-2025)

**How the data are created**: This dataset is compiled by the Metropolitan Police Department (MPD) of Washington DC and includes reported crime incidents. The data is collected through police reports filed by officers responding to crime scenes or reports from citizens.

**Data dictionary**: A clear data dictionary is available, defining fields such as offense type, method, location (block level), date/time, and geographic coordinates.

**Unit of analysis**: Individual crime incidents.

**Dimensions**: The dataset contains approximately 34,000+ records per year (based on 2023 data), with 25 variables including spatial coordinates, crime type, date/time information, and location details.

**Missingness**: There is some missingness in certain fields, particularly in the method of crime and specific location details. Geographic coordinates are generally complete for recent years but may have more missing values in older data.

**Limitations**: The data only includes reported crimes, which may underrepresent certain types of crimes that go unreported. The spatial precision is limited to block level for privacy reasons, which may affect the accuracy of spatial analyses at very fine scales. Additionally, changes in reporting practices over time may affect trend analyses.

### 2. American Community Survey (ACS) 5-Year Demographic, Economic, and Housing Characteristics

**How the data are created**: These datasets are produced by the U.S. Census Bureau through ongoing surveys that gather information about demographics, housing, education, income, and other socioeconomic factors.

**Data dictionary**: Comprehensive data dictionaries are available from the Census Bureau, with detailed descriptions of each variable.

**Unit of analysis**: Census tracts within Washington DC.

**Dimensions**: The demographic dataset contains 1 record (representing DC as a whole) with 119 variables. The economic dataset contains 1 record with 138 variables. The housing dataset contains 207 records (representing individual census tracts) with 143 variables.

**Missingness**: Some census tracts may have missing values for certain variables, particularly in areas with small populations where privacy concerns limit data release.

**Limitations**: ACS data are estimates based on samples, not complete counts, and thus have margins of error that must be considered in analyses. The 5-year estimates, while more reliable than 1-year estimates, represent average characteristics over the period and may not capture rapid changes in neighborhood composition.

### 3. Liquor Licenses and Grocery Store Locations

**How the data are created**: These datasets are maintained by DC government agencies that regulate businesses. Liquor license data comes from the Alcoholic Beverage Regulation Administration, while grocery store location data is compiled by various DC agencies.

**Data dictionary**: Both datasets include clear definitions of fields, including business names, addresses, license types, and geographic coordinates.

**Unit of analysis**: Individual business establishments (liquor stores, restaurants with liquor licenses, grocery stores).

**Dimensions**: The liquor license dataset contains approximately 2,400+ records with 40 variables. The grocery store dataset contains approximately 90+ records with 28 variables.

**Missingness**: There is minimal missingness in the core fields (location, business type), though historical presence indicators may have some gaps.

**Limitations**: The datasets may not include all informal or temporary establishments. Changes in business ownership or licensing may not be immediately reflected in the data. The classification of business types (e.g., what constitutes a "grocery store") may be inconsistent or subjective.

### 4. Additional Potential Data Sources

-   **COVID-19 Weekly Cases**: This dataset provides information on COVID-19 cases by census tract, which could be used to explore relationships between the pandemic and crime patterns.

-   **Bias Crime Data**: This dataset focuses specifically on hate crimes and bias-motivated incidents, which could provide additional context for understanding patterns of targeted violence.

-   **Text Data from Crime Reports**: We plan to extract and analyze textual descriptions from crime reports to identify patterns and sentiments that may not be captured in structured data fields.

By integrating these diverse data sources, we aim to create a comprehensive model that captures the complex interplay of factors influencing crime rates at the census tract level in Washington DC. Our analysis will go beyond simple correlations to explore spatial dependencies, temporal patterns, and textual nuances that contribute to a deeper understanding of crime dynamics in urban environments.
