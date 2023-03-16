### About the project
This project is about applying the concept on webscraping, APIs and Natural Language Processing (LNP).
We will be scraping data from Reddit by using Pushshift API, afterwhich applying NLP to model to classify a random post it comes from.

### Problem Statement

Stocks and real estate investing are both popular investment options for people to grow their their wealth over time.
Stocks: When people invest in stocks, they're buying a small piece of ownership in a publicly traded company. The goal is to buy stocks at a low price and sell them at a higher price later on, making a profit. However, stocks can be volatile and unpredictable, with prices fluctuating based on factors like company performance, market conditions, and global events.

Real estate investing: This involves buying and managing properties with the goal of earning a profit through rental income, property appreciation, or both. Real estate can be a great long-term investment, but it also requires a significant upfront investment, ongoing maintenance costs, and a knowledge of the local real estate market.

As a data analyst for Kabble Securities, I was tasked to develop a machine learning model that can identify key words related to stocks and real estate investing based on user inputs. The challenge is to accurately predict which investments are likely to perform well in the future based on the discussions and patterns observed. The ultimate goal is to provide the company's clients with data-driven insights that will help them make informed investment decisions. The success of this project will depend on the ability of the machine learning model to accurately identify important signals from the noise of online discussions, and the validity of the underlying assumptions used in the model.

### Pushshift API

The scraping data will from `real estate investing` and `stocks` subreddit.


### Part I
Part 1 of Project shows the method for scraping data from Reddit and doing some data cleaning before exporting the dataset to csv file. 


### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|Int||Subreddit Post which included `stocks` and `real estate investing`|

### Accuracy and Precision 
The goal of the project is to be able to train and test a model for accuracy and precision over efficient as we would want the model to accurate pick up key words to help us classify which post does it belong to. For the model to be considered successful, the criteria for accuracy and precision will need to be target of 90% and above for the test score. 



### Exploratory Data Analysis
1. Histogram for Post length for Real estate investing and Stocks  has a negative (left) skew which signify that I have a higher frequency of longer posts than shorter ones. In the context of real estate investing, it can be an indication that users are providing detailed and in-depth information for the topic which helps when training of models. 
2. The top word that shows up in the Real estate investing post is 'property'
3. The top word that shows up in the Stock post is 'company'

### Final Result 

|Model|Method|Train Score|Test Score|Precision(Stocks)|Precision(Real Estate)
|---|---|---|---|---|---|
|Logistic Regression|BOW|0.999|0.9622|0.96|0.96|
|Multinominal Naive Bayes|BOW|0.9755|0.9464|0.97|0.93|
|Bernoulli Naive Bayes|BOW|0.9415|0.8946|0.97|0.83|
|Random Forest|BOW|0.9999|0.9651|0.95|0.98|
|<b>Logistic Regression|<b>TF-IDF|<b>0.9989|<b>0.9662|<b>0.96|<b>0.98|
|Multinominal Naive Bayes|TF-IDF|0.9836|0.9645|0.97|0.96|
|Bernoulli Naive Bayes|TF-IDF|0.9852|0.9566|0.96|0.96|
|Random Forest|TF-IDF|0.9999|0.9594|0.94|0.98|
|Logistic Regression|n-gram(2,2)|0.9997|0.9211|0.90|0.95|
|Multinominal Naive Bayes|n-gram(2,2)|0.9997|0.9278|0.94|0.91|
|Bernoulli Naive Bayes|n-gram(2,2)|0.9927|0.9228|0.93|0.91|

Logistic Regression (TF-IDF) show the best accuracy at 0.9662 out of all the models


### Conclusion, Limitation and Recommendation

#### Conclusion

Overall, we have built and tested multiple classifier that meets the expectiong of Accuracy and Precision with most of the models achiving more than 90%. The best model is the logistic Regression TF-IDF. One of the reason is the TF-IDF is a popular feature that is known for its ability to capture the importance of words in a document. Another reason is that for our problem statement, we were only using 2 scraped posts which logistic regression works well with binary classification.

However, although random forest classifier is considered to be one of the better classifiers, we can see based on our data that it didn't perform well as compared to logistic regression. One of the few reason could be there is small dataset where logistic regression may be a better choice than random forest. Random forest can be prone to overfitting when trained on small datasets, while logistic regression tends to be more stable and reliable in this scenario.

Also logistic regression is generally more interpretable than random forest, as it provides coefficients that show how each feature is associated with the target variable. If interpretability is important for your problem, logistic regression may be a better choice.
Beside the modeling, i realised that there are some main key words that helps to distingush the post. Words like property and rental for real estate and loan, shares or company trading help to distingush.
These words actually helps to improve the machine algothims and to better serve our push for data driven investments insights.


#### Limitation

There are many limitation to this scope of project. One of them is the collection of datas. As the data comes from a social media posts, people tends to not write in proper or complete english or words. This actually will impact the quality of training of our models.

#### Recommendation

Recommendation includes feature engineering: The features used in a classifier can have a significant impact on its performance. Feature engineering involves selecting or transforming features to improve the quality of the input data. This could involve scaling, normalization, or dimensionality reduction techniques, depending on the nature of the data.

Hyperparameter tuning: Many classifiers have hyperparameters that can be tuned to improve their performance. Hyperparameters control the behavior of the algorithm, and tweaking them can often lead to better results. Hyperparameter tuning can be performed using techniques such as grid search, random search, or Bayesian optimization.

Ensemble methods: Ensemble methods involve combining the predictions of multiple classifiers to improve overall performance. Techniques such as bagging, boosting, and stacking can be used to create powerful ensemble models that can often outperform individual classifiers.

