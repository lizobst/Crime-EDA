For this project, I conducted exploratory data analysis on crime data from the Little Rock Police Department. Data can be found [here](https://data.littlerock.gov/Safe-City/Little-Rock-Police-Department-Statistics-2017-to-Y/bz82-34ep/about_data). The data spans years 2017-Present and I filtered the data to exclude 2024 so that I was only working with dataset for entire years. For my analyses, I was interested in exploring the data and discovering any possible trends.

#### Tools used
I conducted the analysis in Python, mostly creating visualizations with matplotlib and using the Folium library for geospatial analysis. For statistical analysis, I utilized seaborn and statsmodels.

#### Data Processing
Since I was interested in temporal trends, it was necessary to convert the data to a more useable format. I utilized datetime to convert the reported incidents into datetime format and extract the Year, Month, Day, and Hour to create new columns with this data.


#### Visualizations
In these visualizations, I was interested in seeing how the amount of crimes vary with time.


![image](https://github.com/user-attachments/assets/16c4784b-3423-40f9-ae19-457c2ec42434)

I was surprised to see 2017 much higher than 2023. I was worried about the possibility of earlier years having less data due to technology changes or crime code reclassifications.

![image](https://github.com/user-attachments/assets/2b2e3753-835c-4125-9980-dea8921aac05)  

Crimes appear to increase in April and reach their peak in August. In October they appear to decrease.

![image](https://github.com/user-attachments/assets/09b8322b-3dbb-442e-bcbc-85b1e069a805)  

Monday and Friday appear to have the highest number of crimes.

![image](https://github.com/user-attachments/assets/05c9c3a2-739b-421a-9d95-e543bef8147a)
Crimes appear to increase at around 5:00 and continue to increase until 17:00 when they begin to decrease.

![image](https://github.com/user-attachments/assets/cb8e9c91-b14a-4ac3-b984-6ad165355ded)
This heatmap displays the density of each crime for each hour of the day. Aggravated assaults are highest from 21:00 to 23:00. Theft from motor vehicle seem to occur all throughout the day from 8:00 to 22:00.

![image](https://github.com/user-attachments/assets/3fe25f6f-5b2c-4173-890c-cf825ad03258)
Aggravated assaults and Theft from motor vehicle are the two most frequent types of crime in Little Rock.

#### Geospatial Analysis

Heatmap of Aggravated assaults in Little Rock.
![image](https://github.com/user-attachments/assets/478018c5-00fb-4920-a62b-a7cd3a7039cf)

Heatmap of Motor vehicle theft in Little Rock.
![image](https://github.com/user-attachments/assets/146dd898-92a1-4614-8620-d8e30c17a4d6)


#### Statistical Analysis

Correlation matrix:
![image](https://github.com/user-attachments/assets/51157ffb-0b0a-48a5-838c-5803f72555a2)  

Interpretation: 
High positive correlations: 
- Aggravated assault and All other larceny: Correlation of 0.86
- Motor vehicle theft and Theft from motor vehicle: Correlation of 0.82

Negative Correlations:
- Purse snatching and Theft from motor vehicle parts: Correlation of -0.83
- Shoplifting and Theft from motor vehicle parts: Correlation of -0.71
- Robbery and Theft from motor vehicle parts: Correlation of -0.72

Overall interpretation:
Some crime types tend to cluster together such as theft related crimes like Burglary/B&E, All other larceny, and Motor vehicle theft. They show moderate to strong positive correlations with each other.

Crimes like Theft from motor vehicle parts and Purse snatching are mutually exclusive crimes. They appear to be inversely related, suggesting that areas with a high prevalence of one type tend to have a low prevalence of the other.

This correlation matrix provides insights into which types of crime tend to occur together and which are less likely to occur. This can help inform strategies for crime prevention and resource allocation.


Regression analysis calculated using statsmodels:  

![image](https://github.com/user-attachments/assets/74dfd8d2-a692-455c-b6e7-9ca4c373d2c1)

Interpretation:
R-squared value: 0.319
This indicates that approximately 31.9% of the variation in Incident_Count can be explained by the independent variables Hour and Day.

Adj. R-squared value: 0.315
This value is slightly lower and suggests the model is a reasonable fit but not highly predictive.

Hour: 7.0382
This positive coefficient suggests that for each hour of the day, Incident_Count increases by 7.038 incidents. This suggests crime rates tend to increase throughout the day.

Day: -1.1317
This negative coefficient suggests that for each additional day, Incident_Count decreases by 1.1317 incidents. This suggests that crime rates decrease slightly as the week progresses.

The p-values for Hour and Day are highly significant. This means they are statistically significant predictors of Incident_Count.
The F-statistic is 86.43 with a p-value of 1.64e-31 which indicates that the overall model is statistically significant.

Summary:
The model indicates that crime incidents increase with each hour of the day, while decreasing slighly with each additional day in the dataset. The R-value suggests the model explains a moderate amount of variance, so it may not capture all factors contributing to crime incidents. Additional variables or non-linear modeling could improve predicting power.

#### Conclusions
Overall, this project was fun to explore and the city of Little Rock provides great data for their city.

#### Future Analysis
For future analysis, I would like to convert the crime locations to the block groups so that I can aggregate crimes occurring in the same area/neighborhood. With this information, I would like to compare it against socioeconomic data to determine correlations between the frequency of crime and socioeconomic factors. Also, I would be interested in looking at what other factors influence crime. Since the data involves human nature, relationships between factors are not so cut and dry and it is important to take confounding factors into account in order to make the most reliable judgements and interpretations.

