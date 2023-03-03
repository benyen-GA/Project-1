### Background

The Housing & Development Board (HDB) (Malay: Lembaga Perumahan dan Pembangunan; Chinese: 建屋发展局; Tamil: வீடமைப்பு வளர்ச்சிக் கழகம்) or often referred to as the Housing Board, is a statutory board under the Ministry of National Development responsible for Singapore's public housing. Founded in 1960 as a result of efforts in the late 1950s to set up an authority to take over the Singapore Improvement Trust's (SIT) public housing responsibilities, the HDB focused on the construction of emergency housing and the resettlement of kampong residents into public housing in the first few years of its existence.
The resale market in Singapore in recent years has known to be more competitive due to the lack of housing and with more citizen being weathier. There are many factors involving the resale prices. By using past sales data and building of a model, we are able to predict the HDB resale prices.
We will be using a training set provided to train our model before using the test set to test our model. The main feature that we are looking out for is the 'resale prices' feature.

### Problem Statement

I'm a Business analyst that was commissioned by the Housing Board Authority (HDB) to help analyze and predict the current trend of resale prices from 2012 - 2021.
As there are many factors involving the prediction of HDB resale prices, this include the flat type, town area, flat model, floor area. It is necessary to develop a model to help predict the resale price based on the mentioned factors.
The datasets used are listed below to help develop our model. The evaluation metric for the model used will be the Root Mean Square Error (RMSE) which measures the difference between the predicted and actual prices. The lower the RMSE,it indicate better accuracy of the model.

### Dataset

There are 3 datasets included in the data folder for this project.
train.csv: This data contains all of the training data for model. The target variable (SalePrice) is removed from the test set
test.csv: This data contains the test data for your model. You will feed this data into your regression model to make predictions.
sample_sub_reg.csv: An example of a correctly formatted submission for this challenge (with a random number provided as predictions for SalePrice. Please ensure that your submission to Kaggle matches this format.


### Data Cleaning

1) Checked for missing values
2) Checked for NaN values
3) Converted Dtypes
4) Ammended wrong values/ incorrect data
5) Dropped unnecessary columns
6) Renaming columns
7) Merging dataframes

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|maximum_rainfall_in_a_day|float|rainfall-monthly-highest-daily-total|This dataset shows the maximum rainfall in mm that is record in a single day a particular month for the past 40 years in singapore.|
|mean_temp|float|surface-air-temperature-monthly-mean|This dataset shows the the monthly mean temperature in degC for the past 40 years in singapore. | 
|mean_rh|float|relative-humidity-monthly-mean|This dataset shows the average relative humidity recorded in Singapore for the past 40 years| 
|mean_sunshine_hrs|float|sunshine-duration-monthly-mean-daily-duration|This dataset shows the average hours of Sunshine exposure monthly for the past 40 years| 
|no_of_rainy_days|Int|rainfall-monthly-number-of-rain-days|This dataset shows the amount of days that rained per month in Singapore for the last 40 years |
|total_rainfall|float|rainfall-monthly-total|This dataset knows the monthly average of rainfall occur in singapore for the past 40 years| 
|year|object|df|Year Date of the dataset| 
|month|object|df|Month Date of the dataset| 


### Exploratory Data Analysis

1. Based on the data, we can see that the Northeast Monsoon season occurs between Sep to Nov in the space of 10 years difference with the highest rainfall occur Sep and Nov. 
2. From 2010 to 2020 onwards, the highest rainfall record belongs to the Southwest Moonsoon. 
3. A adverse event that occured in 2000 where the min amount of rainfall occurred in Sep as compared to the rest of the other years period. This could be due to climate change where it was reported in 2020, the temperature was the highest as compared to the other years. 
4. The record dry spell that occurred in 2014 over Singapore–Malaysia was caused by the southward contraction of the intertropical convergence zone. This means that there were a lack of wind activities which indirectly help to move thunderstorm clouds. 
5. The wettest season in the data of 40 years was known in 2006. This was due to increase acitvities of the sumatra qualls.
6. As in 1990, it was recordest the highest month to be the wettest which significent contribute to to the the highest amount of rainfall. The only differnce is that in 2010, the month of Nov shows that that it had the highest number of days rained.
7.  the highest amount of rainfall record was in July 2010. Hence, We can assumed that in that month, there were days that the it rained longer than usual although the days rained are lesser. More in-depth investigation should be done to verified this assumption.


### Recomendation and Conclusion

###### Conclusion
Rainfall contribute directly to the temperature which can impact food delivery orders and types of food delivery.

Temperature plays a major role in the types of food that people ordered. For example, people in hot and humid conditions will like to eat cold food to regulate their body temperature. They also tends to avoid savory food. However, in cold and wet conditions, people tends to eat warm food like soups and spicy dishes to bring up their temperature and to stay warm. 

it was also found that poor air quality will increase takeaway orders as people will avoid going out on poor air quality conditions which increase online shopping or takweaways. 

Overall, there have been talks of climate change and global warming. From the data analysis, the data showed that there were any increase of tempeature of a period of 40 years. This data is extremely important as it helps to tells us the challenges and difficult that climate change might do to us. For example, with the change of climate and uncommon rainfall or drought, normal harvest of crops are delayed which will affect the supply chain network which might cause higher spending.

###### Recomendation

Due to the wet weather season from October to January, it is recommended that delivery platform to add in additional drivers to meet the demand. This will help to increase sales and business and at the same time lower the demand price of a particular service. This is specially important because the period of thre monsoon season falls during the festive period which people will come out to do more spending. 

With the data showing that the wet season are mainly from October – January. This correspond with the spending season such as Christmas and New year hence some program incentive should be implemented.

As relationships between weather and takeaway food are different on different days of the week and different seasons of the year. it is recommended that the research findings could help the delivery food platform and settled businesses to find out consumer preferences on takeaway food in different weather conditions, formulate corresponding promotion programs and better to meet consumer demand.

### Citations

Source 1: https://www.data.gov,sg

Source 2: https://www.researchgate.net/publication/349514304_Effect_of_weather_on_online_food_ordering

Source 3: https://www.grab.com.sg
