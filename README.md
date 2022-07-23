# Credit_Risk_Analysis

## Analysis Overview
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.\
We adopted the following procedure:
- oversample the data using the **RandomOverSampler** and **SMOTE** algorithms.
- Undersample the data using the **ClusterCentroids** algorithm.
- Use a combinatorial approach of over- and undersampling using the **SMOTEENN** algorithm.
- Compare two machine learning models that reduce bias, **BalancedRandomForestClassifier** and **EasyEnsembleClassifier**.

We will evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

## Resources
- Data Source: LoanStats_2019Q1.csv
- Software: Python 3.7.9, Anaconda Navigator 1.9.12, Conda 4.8.4, Jupyter Notebook 6.0.3

## Results (Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports)


### SMOTE model
<p align="center">
![image](https://github.com/morriscomia/Credit_Risk/blob/main/Resources/SMOTE.png)
</p>
The balanced accuracy score is 65%.<br>The high_risk precision is about 1% only with 63% sensitivity which makes a F1 of 2% only.<br>Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66%.
<br><br>



### BalancedRandomForestClassifier model
<p align="center">
![image](https://github.com/morriscomia/Credit_Risk/blob/main/Resources/BalancedRandomForestClassifier.png)
</p>
The balanced accuracy score improved to about 79%.<br>The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.
<br><br>

### EasyEnsembleClassifier model
<p align="center">
 ![image](https://github.com/morriscomia/Credit_Risk/blob/main/Resources/Easy%20Ensemble%20AdaBoost%20Classifier.png)
</p>
Now, the balanced accuracy score is high to about 93%.<br>The high_risk precision is still low at 8% only with 91% sensitivity which makes a F1 of only 16%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 93% with 100% presicion.
<br><br>

## Summary
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.\
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.\
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.\
For those reasons I would not recommend the bank to use any of these models to predict credit risk.
