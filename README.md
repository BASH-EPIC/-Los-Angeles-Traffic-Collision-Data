# -Los-Angeles-Traffic-Collision-Data
![image](https://user-images.githubusercontent.com/81670865/177651329-442c3e26-358d-4e1e-b80f-590786f03948.png)
# Introduction to dataset:
This data set has 502848 observations with 24 variables. The purpose of this visualization is to identify common factors of crashes at location. Some important variables are as follows Date. Reported, Date Occurred, Time Occurred, area Name, Crime Code, Description, Victim Age, Victim Sex, Victim Descent, Premise Description & Address. There are various causes of collisions such as Speeding, raining, the person is drunk, vehicle skid etc. So, using this data set we’ll get to know the location of accidents, whether it’s male or female when the accident happened like in day or night. Also using location variables we get to know site, area route and mass action. So, after visualizing the data set we’ll get to know what the reason was and on which points the accidents happened mostly and if accidents happened mostly in nights then what we can do to decreased the collisions.

# Business Problem Statement:
1.	This is the Los Angeles Collision dataset of 2010 to 2019. 
2.	The Los Angeles Police Department's existing system for reporting traffic collisions and entering data into a computer database is old, time-consuming, and incomplete. The current flow pattern for completing a traffic collision report in the City of Los Angeles is as follows.
3.	How to decreases the Number of accidents in the highway area.
4.	Limit the False Alarm system.
# Variables of Interest:
Here we have taken some variables which are going to help us in predicting the final analysis. Mostly, here we have chosen those variables which have some categories. 
We have extracted month code and month name and year from date occurred column. Victim Age, Victim Sex, Premise Code, Time Occurred, Reporting District, Date Occurred, Area ID, Council Districts, Precinct Boundaries, Neighborhood Councils Certified, Census Tracts.
Moreover, we have categorized time into night and day with night as a code of 0 and day as a code of 1. Age is categorized as young and old with young as a code of 0 and old as a code of 1. Lastly, we have categorized victim sex where "F" ,"H","M", "N","X" are provided code 3, 5,2, 6, 1,4 respectively according to their frequency
# Data Description:
This data is copied from original traffic reports that were typed on paper, there may be some inaccuracies. (0°, 0°) is used to indicate missing data in several location fields. To ensure privacy, address fields are only provided to the closest hundred block.
Data having 50248 observations with 24 variables. Each variables description are as follows:
1.	DR NUMBER: Division of Records Number: Official file number made up of a 2-digit year, area ID, and 5 digits.

2.	DATE REPORTED: It’s in MM/DD/YYYY & in Time format.

3.	DATE OCCURRED: It’s in MM/DD/YYYY & in Time format.

4.	TIME OCCURRED: In 24-hour military time.

5.	AREA ID: The Los Angeles Police Department (LAPD), Within the LAPD, there are 21 Community Police Stations known as Geographic Areas. These Geographic Areas are numbered 1 through 21 in order.

6.	AREA NAME: The 21 Geographic Areas or Patrol Divisions are also given a name that refers to a local landmark or the community in which they are accountable.

7.	REPORTING DISTRICT: A code for grouping data into geographic sub-areas within an area in reports.

8.	CRIME CODE: Indicates the type of offense that was committed. All Crime Code 997 is included in this collection.

9.	CRIME CODE DISCRIPTION: The specified Crime Code is defined. All Traffic Collision is included in this dataset.

10.	MO CODES: The suspect's modus operandi refers to the activities that he or she engages in while committing the crime.

11.	VICTIM SEX: MALE/FEMALE.

12.	VICTIM AGE: Descent Code: 0 TO 100 YEARS OLD.
13.	VICTIM DESCENT: Descent Code: A - Other Asian B - Black C - Chinese D - Cambodian F - Filipino G - Guamanian H - Hispanic/Latin/Mexican I - American Indian/Alaskan Native J - Japanese K - Korean L - Laotian O - Other P - Pacific Islander S - Samoan U - Hawaiian V - Vietnamese W - White X - Unknown Z - Asian Indian

14.	PREMISE CODE: The sort of structure or setting in which the incident occurred.

15.	PREMISE DESCRIPTION: Defines the Premise Code provided.

16.	ADDRESS: To ensure anonymity, the street address of the crime incidence was rounded to the nearest hundred block.

17.	CROSS STREET: The rounded address's cross street.

18.	LOCATION: The site where the crime took place. For the sake of privacy, the actual address has been withheld. The nearest 100 block is represented by the XY coordinates.

19.	ZIP CODES 

20.	CENSUS TRACTS: Unknown 

21.	PRECINT BOUNDARIES: Police station boundaries.

22.	LA. SPECIFIC.PLANS: unknown

23.	COUNCIL DISTRICTS: Counties

24.	NEIGHBORHOOD CONCILLS: Districts 
1.	Hypothesis Testing
After performing two sample t test we can see that the p-value is more than alpha(0.05), i.e. 0.07186 hence we fail to reject null hypothesis. And hence the conclusion is, victim age and victim sex are independent variables
![image](https://user-images.githubusercontent.com/81670865/177651932-05360a3d-a835-4a62-84d9-05c4a7eee82e.png)
2. CHI SQUARE:
![image](https://user-images.githubusercontent.com/81670865/177651967-80bb4321-bb79-459b-b112-ccea9d7a3cff.png)
Here we have performed chi square test for the variables Census Tracts and Council Districts and we found that our chi square value is more than degree of freedom and the p significance level significance level 0.05 , we reject null hypothesis and concludes that the two variables are dependent on each other and have significance relationship.
3. ANOVA:
As the p value of all the predicted variables except victim age is less than significance level, hence we can say that all these variable will going to affect the census tract. But victim age will make no change in count of census tract. 
![image](https://user-images.githubusercontent.com/81670865/177652058-f915ab9f-031a-49bb-a8b7-11971490f7e2.png)
4. CONTINGENCY TABLE:
The below two table shows the accidents count by relating month with victim age in day and night. Moreover, from the table it is clearly seen that most of the accidents occurred at night time and majority of the victims affected were young.
![image](https://user-images.githubusercontent.com/81670865/177652118-e8c85989-0989-4e39-ac5a-bcdcd3b08965.png)
![image](https://user-images.githubusercontent.com/81670865/177652132-a9cc8e7c-08b4-4b56-aa58-142c8982ad68.png)
5. CO-RELATION TABLES:
After creation of the correlation matrix we noticed that strongest correlation is seen between Area.ID and reporting districts whose value is nearly equal to one which clearly means that change in area will let to chance in district. 
Moreover, it is seen that as the council district changes number of cases recorded also changes which also shows a strong correlation
![image](https://user-images.githubusercontent.com/81670865/177652162-bd0d8253-d385-42ba-8ef4-85b731c6e83f.png)
6. Linear Model
It is clearly seen that all the predictors are meaningful to our model because of low p value and are significant at 0.001. Moreover, it is said that lower the the residual better the model. High variance in the model can be predicted by looking at the high percentage of R Squared and Multiple R squared value. The F-test is statistically significant.  This means that the model have at least one variable that is significantly different than zero.
![image](https://user-images.githubusercontent.com/81670865/177652223-d5d18942-88f2-4f83-9046-bb6af7f8c482.png)
7.GLM with family Gaussian:
![image](https://user-images.githubusercontent.com/81670865/177652261-21368400-b1a9-4d80-bb6f-22b111d76661.png)
GLM with family Poisson

1. AIC value for Gaussian distributed model = 1512978
2. AIC value for Poisson distributed model = 31964558

After running poisson model we noticed that our AIC value has increased. Which clearly means that our GLM model with Poisson Family is not a good fit than our GLM model with Gaussian family. Moreover, in poisson distributed model, fisher's scoring algorithm needs 5 iteration to perform fit for the model which is more than that of Gaussian distributed model.
![image](https://user-images.githubusercontent.com/81670865/177652323-736311a5-9bb0-4a73-8d75-82079fbf68fa.png)

8. 	Odds Ratio :
Now we can say that for a one unit increase in our predictor variable, the odds of increase in cases in reporting districts increase by a factor of Actual Value. Here 2.5 is our coefficient and 97.5 is our confidence interval.  
![image](https://user-images.githubusercontent.com/81670865/177652378-91454f3b-9714-42e7-b76d-833ee7d6652d.png)

This is the odd ratio for GLM model with family Gaussian

![image](https://user-images.githubusercontent.com/81670865/177651554-6123c2f8-19b7-4435-9929-90304aec577d.png)
Ridge keeps all variables and shrinks the coefficients towards zero.The lambda values get small, that is unregularized. Using cross validation to pick the best value for lambda, the resulting plot indicates that the unregularized full model does pretty well in this case. As, we can see that our lamda are 1 and dev are 3.The RMSE vale of ridge are 10.44 which were quit good.
![image](https://user-images.githubusercontent.com/81670865/177651582-2edb545f-bcde-4949-be0a-e4f3b14efb0b.png)
![image](https://user-images.githubusercontent.com/81670865/177651591-5e114af3-c96e-4fc9-98bd-e0a2caebf50a.png)
Using cross-validation to select lambda, indicates that the unregularized model does a good job and that within one standard error at seventeen variables is also a good choice. Lasso minimizes the residual sum of squares plus a shrinkage penalty of lambda multiplied by the sum of absolute values of the coefficients. This model performs variable selection in that it restricts some of the coefficients to be exactly zero
![image](https://user-images.githubusercontent.com/81670865/177651603-a26ffe8c-3d5c-4b37-985d-a6c8b36f20ef.png)
![image](https://user-images.githubusercontent.com/81670865/177651644-80d0ef78-a213-452b-890c-ba270e9b4e23.png)
The coefficients here is penalized by the lasso model. As the value of coefficients increases from 0 this term penalizes, cause model, to decrease the value of coefficients in order to reduce loss. The difference between ridge and lasso regression is that it tends to make coefficients to absolute zero as compared to Ridge which never sets the value of coefficient to absolute zero. The zero coefficient are presneted in the table above. The RMSE OF lasso test are 10.34 and precition of lassi are 11.
![image](https://user-images.githubusercontent.com/81670865/177651664-79e7bff0-0692-4be6-bc78-1a690c54e4ec.png)
This graph depicts the majority of male, as in female there were some outliers present.
The age is in between 25 to 80.
![image](https://user-images.githubusercontent.com/81670865/177651705-21ce45e6-5a4f-4ec7-a6d9-7ea1f34a1d15.png)
Fig : Precints vs Mean_time ( Precidents = Police stations vs mean time means Military time).
The military army were present all day. The major timing was after the office hours and mid nights and most accidents happened on highway. As, we’re unable to plot a map as zip codes are wrong in these datasets.

# Analysis with second approach

# Root Mean Squared Error (RMSE): 
As the name suggests it is the square root of the averaged squared difference between the actual value and the predicted value of the target variable. It gives the average prediction error made by the model, thus decrease the RMSE value to increase the accuracy of the model. 
R2 Error: The value of the R-squared metric gives an idea about how much percentage of variance in the dependent variable is explained collectively by the independent variables. In other words, it reflects the relationship strength between the target variable and the model on a scale of 0 – 100%. So, a better model should have a high value of R-squared.

a.	 Ridge Regression
The output shows that the RMSE and R-squared values for the ridge regression model on the training data are 3.951 million and 99.9 percent, respectively.
For the test data, the results for these metrics are 3.940 million and 99.9 percent, respectively.
Output for train dataset
![image](https://user-images.githubusercontent.com/81670865/177652508-c55e9227-264a-42b5-90cb-fb4934eb57f2.png)

#  Conclusion:
Historical data on where and why accidents have happened will drive the improvements.

Drivers in Los Angeles are also expected to try to drive more safely. Drivers are encouraged to obey all posted traffic regulations, drive without distractions, and drive carefully. Physical adjustments to the roads may assist to reduce the number of fatal accidents, but drivers must accept full responsibility when operating a vehicle.
1.	During the peak of office hours, that is 4 to 6 in the evening lots of accidents happened.
2.	We can change the routes (where most accidents happened).
3.	During the Traffic time, Police department must be present at certain area to handle the traffic.
4.	The prediction model RMSE was 11, so can see that this model was way more effective.
As, these alone models cannot do good because there were various factors was present such as location, weather, snow, smoke etc.
5.	77th highway precedent are most active precedents in all our the dataset. 


# Things are missing in these datasets:
1.	Zip codes are wrong. As, this dataset was having only Los Angels data but zip codes having other countries and having 1 Massachusetts zip code are present.
2.	There were 16 NA’S values in Location Factor, as we cannot change or replace it into o to 1 as it’s changing the positions.
3.	Area Id having lot of missing data.

# prevention:
1	Pre-collision system on cars.
2	Slow down on accident areas.
3	Change the route or create new or alternative route.
4	Decrease the False Alarm as it creates lot of Traffic. 







