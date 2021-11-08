# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Afshin Kalantari

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
#### First no negative values were being accpeted by Kaggle so all the negative numbers needed to be replaced by 0 for the scores to be calculated. 
#### Also by mistake I submitted scores without datatime column which was errored out on Kaggle. The test needed to have the datatime column and score for the kaggle to accept them. 

### What was the top ranked model that performed?
#### Top ranked models were consistently those WeightedEnsamble models that was created from other models, including XGB and GBM.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
#### Initial EDA showed that all the fields seems to be important in predicting the bike deand counts. More specifically, holiday and workingday indicator variables seemed to be important. Also, humidity and windspeed also have skewed distributions that could have predictor power in final demand counts. On the other hand the datatime have clear uneven distribution that suggests having more grannual features of datatime coulmn could play an important role in our prediction task. So datetime column was furthermore splitted into year, month, day, and hour so It could be used as separate features. 

### How much better did your model preform after adding additional features and why do you think that is?
#### The performance of the model was significantly imporoved after separating datatime values. The test score droped by around 34% from 1.39 to .55. The reason for this performance boost could be attributed to the importance of time of the day, day of month on the demand for bikes. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
#### Including and running different models did not have as great of boost in performance compared to added features. Different hyperparamter tunning for different models was tried, including AutoGluon default presets, none of them had as great as adding new features on the final score. For Example, tunning hyperparamters of XGBoost model improved the performance just slightly. 

### If you were given more time with this dataset, where do you think you would spend more time?
#### I would have spent more time in Feature Engineering and giving more time to the AutoGluon AutoML to run for best models based on the added features. I would have also tried some of the default HPO settings that are available in AutoGluon to optimize furthermore. I would't have spend anytime to do mannual hyperparamters checking. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|?|?|?|?|
|add_features|?|?|?|?|
|hpo|?|?|?|?|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
#### The goal of this project was to predict bike sharing demand from sets of fields, including datetime, temparature, humidity, and other important fields. From EDA it was noticed that datetime is an important feature so it was splitted into separated columns for more granuality of the datetime of the data. This had a great impact on the prediction of the demand. Running different models through hyperparamter tunning seemed XGBoost and GBM showed a promissing performance compared to other models. However, it should be noted that if more than 10 minutes was to run the models Neural network potentially could have outperformed these models. 
