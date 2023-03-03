### Background

The Housing & Development Board (HDB) (Malay: Lembaga Perumahan dan Pembangunan; Chinese: 建屋发展局; Tamil: வீடமைப்பு வளர்ச்சிக் கழகம்) or often referred to as the Housing Board, is a statutory board under the Ministry of National Development responsible for Singapore's public housing. Founded in 1960 as a result of efforts in the late 1950s to set up an authority to take over the Singapore Improvement Trust's (SIT) public housing responsibilities, the HDB focused on the construction of emergency housing and the resettlement of kampong residents into public housing in the first few years of its existence.
The resale market in Singapore in recent years has known to be more competitive due to the lack of housing and with more citizen being weathier. There are many factors involving the resale prices. By using past sales data and building of a model, we are able to predict the HDB resale prices.
We will be using a training set provided to train our model before using the test set to test our model. The main feature that we are looking out for is the 'resale prices' feature.

### Problem Statement

I'm a Business analyst that was commissioned by the Housing Board Authority (HDB) to help analyze and predict the current trend of resale prices from 2012 - 2021.
As there are many factors involving the prediction of HDB resale prices, this include the flat type, town area, flat model, floor area. It is necessary to develop a model to help predict the resale price based on the mentioned factors.
The datasets used are listed below to help develop our model. The evaluation metric for the model used will be the Root Mean Square Error (RMSE) which measures the difference between the predicted and actual prices. The lower the RMSE,it indicate better accuracy of the model.

### Dataset

1) train.csv: This data contains all of the training data for model. The target variable (SalePrice) is removed from the test set
2) test.csv: This data contains the test data for your model. You will feed this data into your regression model to make predictions.
3) sample_sub_reg.csv: An example of a correctly formatted submission for this challenge (with a random number provided as predictions for SalePrice) 


### Data Cleaning

1) Sorting and Renaming of Columns (Training Set)
2) Checking and cleaning of Null Value for Training Set
3) Converted Dtypes
4) Checking and cleaning of Null Value for Test Set
5) Removing of columns for Training Set
6) Removing of columns for Test Set

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
id|int64||N/A  
town|object||HDB township where the flat is located, e.g. BUKIT MERAH
flat_type|object||type of the resale flat unit, e.g. 3 ROOM
storey_range|object||storey_range
flat_model |object||HDB model of the resale flat, e.g. Multi Generation
lease_commence_date |int64||commencement year of the flat unit's 99-year lease
resale_price|float64||This is the target variable for the modelling
tranc_year|int64||year of resale transaction
tranc_month|int64||month of resale transaction
lower|int64||lower value of storey_range
upper|int64||upper value of storey_range
mid|int64||middle value of storey_range
floor_area_sqft|float64||floor area of the resale flat unit in square feet
hdb_age|int64||number of years from lease_commence_date to present year
max_floor_lvl|int64||highest floor of the resale flat
year_completed|int64||year which construction was completed for resale flat
multistorey_carpark|object||boolean value if resale flat has a multistorey carpark in the same block
precinct_pavilion|object||boolean value if resale flat has a pavilion in the same block
1room_sold|int64||number of 1-room residential units in the resale flat
2room_sold|int64||number of 2-room residential units in the resale flat              
3room_sold|int64||number of 3-room residential units in the resale flat
4room_sold|int64||number of 4-room residential units in the resale flat
5room_sold|int64||number of 5-room residential units in the resale flat
exec_sold|int64||number of executive type residential units in the resale flat block               
multigen_sold|int64||number of multi-generational type residential units in the resale flat block
studio_apartment_sold|int64||number of studio apartment type residential units in the resale flat block 
1room_rental|int64||number of 1-room rental residential units in the resale flat block
2room_rental|int64||number of 2-room rental residential units in the resale flat block    
3room_rental|int64||number of 3-room rental residential units in the resale flat block
other_room_rental|int64||number of "other" type rental residential units in the resale flat block 
latitude|float64||Latitude based on postal code
longitude|float64||Longitude based on postal code
mall_nearest_distance|int64||distance (in metres) to the nearest mall
mall_within_500m|int64||number of mall within 500 metres
mall_within_1km|int64||number of mall within 1 kilometre
mall_within_2km|int64||number of mall within 2 kilometres
hawker_nearest_distance|int64||number of hawker food stalls in the nearest hawker centre
hawker_within_500m|int64||number of hawker centres within 500 metres
hawker_within_1km|int64||number of hawker centres within 1 kilometre
hawker_within_2km|int64||number of hawker centres within 2 kilometres
hawker_food_stalls|int64||number of hawker food stalls in the nearest hawker centre
hawker_market_stalls|int64||number of hawker and market stalls in the nearest hawker centre 
mrt_nearest_distance|int64||distance (in metres) to the nearest MRT station
mrt_name|object||name of the nearest MRT station
bus_interchange|int64||boolean value if the nearest MRT station is also a bus interchange
mrt_interchange|int64||boolean value if the nearest MRT station is a train interchange station
mrt_latitude|float64||latitude (in decimal degrees) of the the nearest MRT station
mrt_longitude|float64||longitude (in decimal degrees) of the nearest MRT station
bus_stop_nearest_distance|int64||distance (in metres) to the nearest bus stop
bus_stop_latitude|float64||latitude (in decimal degrees) of the the nearest bus stop
bus_stop_longitude|float64||longitude (in decimal degrees) of the nearest bus stop
pri_sch_nearest_distance|int64||distance (in metres) to the nearest primary school
pri_sch_name|object||name of the nearest primary school
vacancy|int64||number of vacancies in the nearest primary school
pri_sch_affiliation|int64||boolean value if the nearest primary school has a secondary school affiliation
pri_sch_latitude|float64||latitude (in decimal degrees) of the the nearest primary school
pri_sch_longitude|float||longitude (in decimal degrees) of the nearest primary school
sec_sch_nearest_dist|int64||distance (in metres) to the nearest secondary school
sec_sch_name|object||name of the nearest secondary school
cutoff_point|int64||PSLE cutoff point of the nearest secondary school
affiliation|int64||boolean value if the nearest secondary school has an primary school affiliation
sec_sch_latitude|float64||latitude (in decimal degrees) of the the nearest secondary school
sec_sch_longitude|float64||longitude (in decimal degrees) of the nearest secondary school


### Exploratory Data Analysis

1. Based on the data, we can conclude that central area resale price is considered to be the most expensive as it is in the prime area of Singapore. It is followed by bukit timah where most of the private housing are located.
2. Based on the reg plot above, there seems not to have much correlationship with resale price except for floor_area_sqft. This is naturally so as real estate prices are based on floor_area.
3. There is a trend on the increase of resale prices throughout the different towns in singapore. The highest increase is in fact bukit timah. The first reason behind rising property prices in the last two years, is that central banks have reduced interest rates in a bid to stimulate the economy and prevent an economic recession during a drawn-out pandemic.
4. Based on the number of transaction, there is increase of activities from 2013 to 2020. However, there is a massive dip in 2021. This was due to covid-19 where foreigners usually have rental have all move back to their home countries. Another possible reason was as the world or Singapore have yet to know what is happening in the future, people are holding back on purchasing homes.
5. Based on the above KDE model, we can assume that there is a high demand of 1-room and 2-room flats.
6. There seems to have a trend that the resale prices are the highest in the west and northern part of singapore. This was also due to the high price/sqft that may have contribute to higher resale price.
7. Based on the above scatterplot, I wanted to see if there is any relationship between resale prices and area in the mrt. We can see that there are not many points available, however, we can see that the central area and certain west side, the price are pretty high.

### Recomendation and Conclusion

###### Conclusion
The average price prediction is at 68,000 SGD Based on the notes, the best model is usually the model with the lowest RMSE which turns out to be the Ridge model. The features we used was set at 30 features with alpha = 1. As the median is at 48,000 SGD , the difference between both prediction and median is not far which is a good indictor that it is not overfitting.
Based on the lasso model using K-best feature selection of 30 to predict the price of HDB resale flat units was at 69K SGD with a R2 score of 77%. This is a slightly smaller number as compared to the other 2 models.
Ridge model trades variance for bias. It is usually better than OLS when there are a large number of variables included because it has a penalty term to reduce overfitting and improve generalization to the testing set. However, based on the kaggle set of my submission at 90K points. It shows a slightly overfitting model which makes makes my model perform poorly. This can be due to certain factors in my modelling which means ther is room for improvement.
Comparsion between lasso and ridge, there are many factors to decide which model to use as Lasso can set some coefficients to zero, thus performing variable selection, while ridge regression cannot. Lasso tends to do well if there are a small number of significant parameters and the others are close to zero (ergo: when only a few predictors actually influence the response) while Ridge works well if there are many large parameters of about the same value (ergo: when most predictors impact the response) which in this case ridge is a better model.

###### Recomendation

As this modelling is only at 1 iteration hence improvement could be made with multiple attempt to improve the model. Also, as there is a chance of overfitting which could be cause by the model complexity is high, so it learns the noise within the training data hence overfitting can be look into. We can also look into polynominal features to help us better train our model. 

### Citations

Source 1: https://www.kaggle.com

