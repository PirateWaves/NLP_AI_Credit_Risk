# Unit 11—Risky Business

![Credit Risk](Images/credit-risk.jpg)

## Background

Auto loans, mortgages, student loans, debt consolidation ... these are just a few examples of credit and loans that people are seeking online. Peer-to-peer lending services such as LendingClub or Prosper allow investors to loan other people money without the use of a bank. However, investors always want to mitigate risk, so you have been asked by a client to help them use machine learning techniques to predict credit risk.

In this assignment, you will build and evaluate several machine-learning models to predict credit risk using free data from LendingClub. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so you will need to employ different techniques for training and evaluating models with imbalanced classes. You will use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

### Files

[Resampling Starter Notebook](Starter_Code/credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](Starter_Code/credit_risk_ensemble.ipynb)

[Lending Club Loans Data](Instructions/Resources/LoanStats_2019Q1.csv.zip)

- - -

### Instructions

#### Resampling

You will use the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

You will:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.
2. Undersample the data using the `Cluster Centroids` algorithm.
3. Over- and under-sample using a combination `SMOTEENN` algorithm.

For each of the above, you will need to:

1. Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.
2. Calculate the `balanced accuracy score` from `sklearn.metrics`.
3. Calculate the `confusion matrix` from `sklearn.metrics`.
4. Print the `imbalanced classification report` from `imblearn.metrics`.

Use the above to answer the following:

> Which model had the best balanced accuracy score?
>
> Which model had the best recall score?
>
> Which model had the best geometric mean score?

Answer:
Balanced accuracy is defined as the average of the proportion corrects of each class individually. The model that has the best-balanced accuracy score is the combination Sampling Model. The Combination Sampling model has a balanced accuracy score of .68 compared to the scores of the under-sampling model with a score of .52, the SMOTE oversampling model with a score of .62, and the Naïve Random Oversampling Model with a score of .65. Recall score is defined as the fraction of the total amount of relevant instances that were actually retrieved. 

The model that has the best recall score is the SMOTE Oversampling model with an average F1 score of .79. This is compared to the Naïve Random Oversampling model with a score of .75, the Under Sampling Model with a score .56, and the Combination sampling model with a score of .68. 

The model that has the best geometric mean score is the Combination Sampling Model.

The Native Oversampling model has an average geo score of .68. This is compared to the Smote Oversampling with an average geo score of .62, the Undersampling Model with a score of .56, and Naive Oversampling Model with a score of .65.

#### Ensemble Learning

In this section, you will train and compare two different ensemble classifiers to predict loan risk and evaluate each model. You will use the `balanced random forest classifier` and the `easy ensemble AdaBoost classifier`.

Be sure to complete the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.
2. Calculate the balanced accuracy score from `sklearn.metrics`.
3. Print the confusion matrix from `sklearn.metrics`.
4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.
5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.

Use the above to answer the following:

> Which model had the best balanced accuracy score?
>
> Which model had the best recall score?
>
> Which model had the best geometric mean score?
>
> What are the top three features?

Answer:
The model with the best balanced accuracy score is the Easy Ensemble AdaBoost Classifier with a balanced accuracy score of .93, compared to the Balanced Random Forest Classifier with a balanced accuracy score of .75. 

The model with the best recall score is the Easy Ensemble AdaBoost Classifier with a average f1 score of .97 compared to the Balanced Random Forest Classifier with an average f1 score of .94. 

The model with the best Geometric Mean score is the Easy Ensemble AdaBoost Classifier with an average geo score of .93 compared to the Balanced random Forest Classifier with an average geo score of .78. The top three features are total_rec_prncp, total_pymnt_inv, total_pymt.

- - -

### Hints and Considerations

Use the quarterly data from the LendingClub data that is provided in the `Resources` folder. Keep the file in the zipped format and use the starter code to read the file.

Refer to the [imbalanced-learn](https://imbalanced-learn.readthedocs.io/en/stable/) and [scikit-learn](https://scikit-learn.org/stable/) official documentation for help with training the models. Remember that these models all use the model->fit->predict API.

For the ensemble learners, use 100 estimators for both models.

- - -

### Submission

* Create Jupyter notebooks for the homework and host the notebooks on GitHub.
* Include a markdown that summarizes your homework and include this report in your GitHub repository.
* Submit the link to your GitHub project to Bootcamp Spot.



© 2019 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
