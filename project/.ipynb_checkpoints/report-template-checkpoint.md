# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE: Abdulaziz Ahmed Hawaej

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: Add your explanation:

     -Checking if they are all greater than zero or if there any negative values to set them to zero as it's not accepted by kaggle compittion submission.

### What was the top ranked model that performed?
TODO: Add your explanation:

      -WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Add your explanation:

      1-Made histogram visualization for all features.
      2-Made some Feature Engineering as following: 
          -making pandas dataframe allowable for parsing of datetime type, so that parsing year, month, day, and hour.
          -changing some features type from numerical to categorical like weather and season.
          -normalizing most features counts and values.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation:

      -It was significantly great as the submissions error score changed from 1.83128 to 0.62912.
      -I think that is because the data become more robust in training and evaluating process as it became easier for the model to identify the types of data, their correlation and effect on accuracy and error optimizing for the model.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation:

      -Scored a submission result of 0.48476 which is better from the laset score before HPO which was0.62912

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation

     -I would spend more time with in feature engineering as it needs more sophisticated features manipulations and statistics.
### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|WeightedEnsemble_L3|WeightedEnsemble_L2|LightGBM_BAG_L2|score|
|--|--|--|--|--|
|initial|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': True,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|1.83128|
|add_features|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': True,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|0.62912|
|hpo|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': False,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|{'use_orig_features': True,'max_base_models': 25,'max_base_models_per_type': 5,'save_bag_folds': True}|0.48476|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](model_test_score.png)

## Summary
TODO: Add your explanation:

    1-Fisrt, I imported the required libraries and dataset for data manipulation and investigate the nature of the features columns and target which is 'count' columns data, with making the dataframes datetime parsing for future parsing, then made the regression fit with TabularPredictor of autofluon AWS autoML framework getting the best fitted model with `WeightedEnsemble_L3` scoring a rmse of -55.109925 and a kaggle score of 1.83128.
    2-Then, trying for enhancing performance of the error score and kaggle score, made some feature engineering on the train and test features data like parsing datetime column into month, day and hour, changing some features types into categorical ones. Then made the model fit getting the best model of `WeightedEnsemble_L3` with an error score of -30.472512 and kaggle score of 0.62912, so that made significant improvement on the score.
    3-Finally, with fine tuing some models hyperparameters like NN_Torch, GBM, and XGB, with their hyperparameters associted each for specific, then scoring a new good kaggle score of 0.48476, ensuring that the HPO step make some improvement.
