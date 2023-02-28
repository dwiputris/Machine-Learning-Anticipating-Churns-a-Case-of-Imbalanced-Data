# Anticipating Churns: A Case of Imbalanced Data
With imbalanced observed data, a search for the best model is conducted. The bank is seeing its customers leave. Wondering if there are patterns to their decision to exit, the bank wishes to anticipate for this trend. When the positive class is the minority in an imbalanced dataset, a model need to be trained for robustness.

Customers of Bank Beta is starting to leave. Their number is decreasing from month to month.

Management of the bank realizes that the cost is lower in retaining its existing customers than to attaining new customers.

In this project, a model will be built to predict if a customer is leaving the bank or not.

A dataset is given on the historical behavior of the bank's clients, along with their contract termination.

The goal is to have highest F1 score possible, with its minimum on 0.59 with the testing dataset.

Other validation metric, AUC-ROC score, will also be measured, and then compared to the F1 score.

The project of building machine learning for Bank Beta is started by observing data, some exploratory data analysis, and continued by feature engineering.

Missing values are handled, OHE is applied, and standard scaler is applied.

There are three algorithm tested: LightGBM, RandomForest, and LogisticRegression.

In building with LightGBM, missing values are handled by the machine, and imbalance dataset is left as is.

The F1 score is 0.59 and AUC-ROC score is 0.85. That means this model meets the required minimum F1 score Bank Beta.

Next, another models are built with alogirthm Random Forest. One is applied with Upsampling method. And the other, downsampling method.

It shows that both upsampling method and downsampling method when training the models increase their performance significantly, as measured by their F1 score.

However as the final test of the models show F1 score of 0.57, the models do not meet the required minimum F1 score Bank Beta.

Lastly, another model is built using regression algorithm, that is LogisticRegression. Hyperparameters class_weigh set as balanced due to the imbalance dataset.

Final testing of the model shows that it has F1 score of 0.46 and AUC-ROC of 0.73. This also does not meet the required minimum F1 score Bank Beta.

Each of the three models assigns weight/coefficient to predictors differently.

Conclusion to this project is to use the model with algorithm LightGBM. The LGBM model assigns below predictors as the most significant variables when predicting the exit customers:

1. Balance that they have

2. Their age

3. Their estimated salary

The LGBM model works with imbalanced dataset. The Positive class being minority, the LGBM model shows a low precision metric for Positive class (as low as 0.48). However it manages to have a well Recall score (as high as 0.77). As for Bank Beta what important is anticipating the exit trends (Positive class), then the model is sufficient in meeting their goals.

Other interesting findings in building a model for this project are:

1. Both method of Upsampling and Downsampling does increase a performance of the model trained (as measured with F1 Score), especially when the observed data have imbalance target class.

2. Precision score of the Positive class in models trained with upsampled or downsampled dataset is significantly lower than ones with imbalanced train dataset dominated by Negative class. While the Recall score is significantly higher. Those are what contribute to the increase on F1 Score of Positive Class when the models are trained using upsampled or downsampled datasets.

3. Two models might have similarly high AUC-ROC Score although one's F1 Score of positive class might be way more superior than the other's. Hence when the purpose is to build a model that is able to capture as many Positive class as possible, AUC-ROC score alone is not sufficient to be metric of its performance. F1 score is important.

4. In the case of an imbalanced dataset, accuracy is not a metric to be referred to when measuring the model's performance, as it is easy to achieve high accuracy score just by make prediction by the majority class. F1 Score that relies on both precision and recall will be a lot better compass showing the how robust the model is. Further, when predicting one class is the most important end of building a model, F2 or more can be used, to put emphasize on Recall.
