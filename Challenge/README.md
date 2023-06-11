# Credit Risk Classification Application

## Overview of the Analysis

The analyst was tasked with running an analysis on credit risk using different techniques to train and evaluate models with unbalanced classes. Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. Using a dataset of historical lending activity from a peer-to-peer lending services company, the analyst built a model that can identify the creditworthiness of borrowers.

The model relied heavily on the imbalanced-learn and the sci-kit learn libraries to compare quantitative values of two versions of the dataset: the original set, and the resampled set (using RandomOverSampler).  For both cases, the analyst got the count of the target classes using the value_counts function, trained a logistic regression classifier, calculated the balanced accuracy score, generated a confusion matrix, and generated a classification report to provide a comparison.

## Results

The analyst created (2) separate models to evaluate the creditworthiness of borrowers.  The results of those models are shown below:

* Machine Learning Model 1: Logistic Regression of Orginal Data

    ![OG_Regression.PNG]()

  * The first model was a logistic regression of the original dataset.  The classification report that was generated (above) shows the following results:
    1. Balanced Accuracy Score: 94.43%
    2. Precision: 100%/86% (0: healthy loan/1: high-risk load)
    3. Recall: 100%/89% (0: healthy loan/1: high-risk load)



* Machine Learning Model 2:  Logistic Regression of Resampled Data using RandomOverSampler 

    ![Resampled_Regression.PNG]()

  * The first model was a logistic regression of the resampled dataset using RandomOverSampler.  RandomOverSampler randomly selects instances of the minority class and adds them to the training set until we’ve balanced the majority and minority classes.  The classification report for the regression (above) shows the following results:
    1. Balanced Accuracy Score: 99.39%
    2. Precision: 100%/85% (0: healthy loan/1: high-risk load)
    3. Recall: 99%/99% (0: healthy loan/1: high-risk load)


## Summary

From the results, the analyst determined that Model 2 (resampled logistic regression) performs best at predicting healthy vs. high-risk loans.  The second model had a balanced accuracy score ~5% higher than that of the first (99.39% vs. 94.43%).  Model 2 had a the same level of precision when predicting the healthy loans (100% for both), but was very slightly outperformed by model 1 when predicting the precision of the high risk loan (86% vs. 85%).  When evaluating the recall, Model 2 slightly underperformed at the predicting the healthy loans when compared to Model 1 (99% vs. 100%), but outperformed Model 1 when predicting the high-risk loans (99% vs. 89%). 

The analyst recommends using the second model to evaluate the creditworthiness of borrowers as it outperforms the first model in most metrics.  Where it underperforms against Model 1, it only does so slightly and the difference is practically neglible.  Model 2 also has a 10% difference in recall when compared to Model 1, meaning that it is 10% more likely to predict loan as high risk.  The cost of default associated with approving high risk loans far outweights the loss of potential profit associated with not approving healthy loans, so being more sensitive to high-risk loans provides less risk of approving a high risk canditate. 