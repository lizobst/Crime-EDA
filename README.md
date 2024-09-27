### Exploratory Data Analysis of Crime Trends in Little Rock, Arkansas
This project provides a comprehensive exploratory data analysis (EDA) of crime data sourced from the Little Rock Police Department. The primary objectives are to identify temporal trends, analyze geospatial distribution of crime incidents, and uncover trends that may inform law enforcement and public safety strategies.

#### Data Source and Preprocessing
The dataset was obtained from the Little Rock Police Department's public records, covering crime incidents reported between 2017-2023. Data for 2024 was excluded to ensure complete year-over-year analysis. Preprocessing steps involved handling missing values, converting datetime columns, and geocoding latitude and longitude for spatial analysis. The final dataset includes 19 columns and 115,887 rows, offering a comprehensive overview of crime in Little Rock.

#### Visualizations
##### Temporal Analysis

Crime rates in Little Rock peak during August, with a general upward trend from April through summer. The data also shows that crimes tend to occur more frequently during late afternoons and evenings, peaking around 17:00 and gradually decreasing after midnight.

![image](https://github.com/user-attachments/assets/16c4784b-3423-40f9-ae19-457c2ec42434)

Yearly Crime Trend: 2017 recorded a significantly higher number of incidents compared to 2023.

![image](https://github.com/user-attachments/assets/2b2e3753-835c-4125-9980-dea8921aac05)  

Monthly Crime Trend: Crimes appear to increase in April and reach their peak in August. In October they appear to decrease.

![image](https://github.com/user-attachments/assets/09b8322b-3dbb-442e-bcbc-85b1e069a805)  

Day of the Week Trend: Mondays and Fridays exhibit the highest number of reported crimes, suggesting potential correlations with weekday activities or events.

![image](https://github.com/user-attachments/assets/05c9c3a2-739b-421a-9d95-e543bef8147a)
Hourly Distribution: Crimes appear to increase at around 5:00 and continue to increase until 17:00 when they begin to decrease.

![image](https://github.com/user-attachments/assets/cb8e9c91-b14a-4ac3-b984-6ad165355ded)
Heatmap analysis: Aggravated assaults are highest from 21:00 to 23:00. Theft from motor vehicle seem to occur all throughout the day from 8:00 to 22:00.

![image](https://github.com/user-attachments/assets/3fe25f6f-5b2c-4173-890c-cf825ad03258)
Aggravated assaults and Theft from motor vehicle are the two most prevalent types of crime in Little Rock.

#### Geospatial Analysis
Heatmaps were generated to identify hotspots for Aggravated assault and Motor Vehicle theft. The spatial analysis show that the two heatmaps overlap, indicating that these crimes tend to occur in the same areas. This suggests these regions may share underlying risk factors such as higher population density, lower socioeconomic status, or other social determinants that contribute to increased crime rates. Further investigation into these factors could help pinpoint the root causes and aid in developing targeted intervention strategies.

Heatmap of Aggravated assaults in Little Rock.
![image](https://github.com/user-attachments/assets/478018c5-00fb-4920-a62b-a7cd3a7039cf)

Heatmap of Motor vehicle theft in Little Rock.
![image](https://github.com/user-attachments/assets/146dd898-92a1-4614-8620-d8e30c17a4d6)


#### Statistical Analysis

Correlation matrix:
![image](https://github.com/user-attachments/assets/51157ffb-0b0a-48a5-838c-5803f72555a2)  

Correlation Analysis: 
High positive correlations: 
- Aggravated assault and All other larceny (r=0.86)
- Motor vehicle theft and Theft from motor vehicle (r= 0.82)

Negative Correlations:
- Purse snatching and Theft from motor vehicle parts (r=-0.83)
- Shoplifting and Theft from motor vehicle parts (r=-0.71)
- Robbery and Theft from motor vehicle parts(r=-0.72)

These results suggest that certain types of crime tend to occur together, while otherrs are inversely related. These correlations could occur since some crime types tend to cluster together such as theft related crimes like Burglary/B&E, All other larceny, and Motor vehicle theft. These crimes show moderate to strong positive correlations with each other. Crimes like Theft from motor vehicle parts and Purse snatching are mutually exclusive crimes. They appear to be inversely related, suggesting that areas with a high prevalence of one type tend to have a low prevalence of the other.


Regression Analysis:

![image](https://github.com/user-attachments/assets/74dfd8d2-a692-455c-b6e7-9ca4c373d2c1)

A linear regression model was built using Hour and Day as predictors for Incident_Count. The model explains that approximately 31.9% of the variance in crime rates (R-squared = 0.319), indicating a moderate fit. Crime rates increase significantly with each hour of the day (p<0.05) but show a slight decrease as the week progresses.


#### Conclusions
The EDA revealed key temporal and spatial patterns in crime distribution across Little Rock. Crime incidents are highest during the summer months and tend to increase in the late afternoon and evening. Understanding these patterns can inform police resource  allocation and community outreach strategies.

#### Future Work
Future analysis will involve mapping crime data to neighborhood block groups to facilitate comparisons with socioeconomic indicators such as median income, unemployment rates, and educational attainment. Incorporating additional variables or employing non-linear models could improve predictive power and lead to more nuanced interpretations of the factors influencing crime trends.
